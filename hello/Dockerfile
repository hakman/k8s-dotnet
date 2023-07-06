FROM --platform=${BUILDPLATFORM} mcr.microsoft.com/dotnet/sdk:7.0 as build
ARG TARGETARCH
WORKDIR /source
COPY appsettings.json Hello.cs Hello.csproj ./
RUN  dotnet publish -c release -o /app -r linux-${TARGETARCH} --self-contained false

FROM --platform=linux/${TARGETARCH} mcr.microsoft.com/dotnet/aspnet:7.0
WORKDIR /app
COPY --from=build /app .
ENTRYPOINT ["dotnet", "Hello.dll"]
