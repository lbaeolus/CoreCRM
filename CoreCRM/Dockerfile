FROM microsoft/dotnet:latest

RUN apt-get update && apt-get -y install sqlite3 libsqlite3-dev

COPY . /app

WORKDIR /app/CoreCRM

RUN ["dotnet", "restore"]

RUN ["dotnet", "build"]

RUN ["dotnet", "ef", "database", "update"]

EXPOSE 5000/tcp

ENTRYPOINT ["dotnet", "run", "--server.urls", "http://0.0.0.0:5000"]
