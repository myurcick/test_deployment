# Base image для запуску .NET 8
FROM mcr.microsoft.com/dotnet/aspnet:8.0 AS base
WORKDIR /app

# Cloud Run передає порт через змінну середовища PORT
ENV DOTNET_RUNNING_IN_CONTAINER=true \
    DOTNET_USE_POLLING_FILE_WATCHER=true \
    ASPNETCORE_URLS=http://+:8080

# Відкриваємо порт
EXPOSE 8080

# Копіюємо всі публішені файли
COPY . .
RUN mkdir -p /home/site/wwwroot/uploads
# Запускаємо додаток
ENTRYPOINT ["dotnet", "Backend.dll"]
