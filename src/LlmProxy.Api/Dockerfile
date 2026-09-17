FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src

COPY LlmProxy.slnx ./
COPY src/LlmProxy.Domain/LlmProxy.Domain.csproj src/LlmProxy.Domain/
COPY src/LlmProxy.Application/LlmProxy.Application.csproj src/LlmProxy.Application/
COPY src/LlmProxy.Infrastructure/LlmProxy.Infrastructure.csproj src/LlmProxy.Infrastructure/
COPY src/LlmProxy.Api/LlmProxy.Api.csproj src/LlmProxy.Api/
RUN dotnet restore src/LlmProxy.Api/LlmProxy.Api.csproj

COPY src/ src/
RUN dotnet publish src/LlmProxy.Api/LlmProxy.Api.csproj -c Release -o /app --no-restore

FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS runtime
WORKDIR /app
COPY --from=build /app .

ENV ASPNETCORE_URLS=http://+:8080
EXPOSE 8080

ENTRYPOINT ["dotnet", "LlmProxy.Api.dll"]
