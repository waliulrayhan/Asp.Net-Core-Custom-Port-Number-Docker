Custom Port Number Docker ASP.NET Core
This repository provides instructions and configurations to customize the port number for an ASP.NET Core application running in Docker using docker-compose.

Setup Instructions
Follow these steps to customize the port number:

Modify docker-compose.override.yml

Remove the - ASPNETCORE_HTTPS_PORTS entry and set your custom port number in the ports section. Replace 8081 with your desired port number:

yaml
Copy code
ports:
  - "8081:8080"
Update ASP.NET Core Configuration

Update the port number in WebApplication1/Properties/launchSettings.json. Under the Docker configuration, set the ASPNETCORE_HTTP_PORTS environment variable to your custom port number (e.g., 8081):

json
Copy code
"Docker": {
      "commandName": "Docker",
      "launchBrowser": true,
      "launchUrl": "{Scheme}://{ServiceHost}:{ServicePort}",
      "environmentVariables": {
        "ASPNETCORE_HTTP_PORTS": "8081"
      }
    }
Ensure that the port numbers specified in docker-compose.override.yml and launchSettings.json match.

Usage
Once the configurations are updated, build and run your ASP.NET Core application using Docker. Your application will now be accessible through the specified custom port number.
