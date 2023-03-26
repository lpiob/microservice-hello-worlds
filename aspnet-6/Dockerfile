FROM mcr.microsoft.com/dotnet/sdk:6.0-alpine AS build
WORKDIR /app

# copy everything else and build app
COPY src/ src/

RUN dotnet publish src/MyWebApp/MyWebApp.csproj -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:6.0-alpine AS runtime
WORKDIR /app

COPY --from=build /app/out /app
RUN ls -R /app/
 
ENV ASPNETCORE_URLS http://+:8080
ENTRYPOINT ["dotnet", "/app/MyWebApp.dll"]
