<h1 align="center">Custom-Port-Number-Docker-ASP.NET-Core</h1>
<p align="center">A sample project that shows how to run an ASP.NET Core web application on a custom port using Docker.</p>

<h2>Prerequisites</h2>
<ul>
  <li><a href="https://dotnet.microsoft.com/download">.NET 8.0 SDK</a></li>
  <li><a href="https://www.docker.com/get-started">Docker Desktop</a></li>
</ul>

<h2>How to run</h2>
<ol>
  <li>Clone this repository</li>
  <li>Open the solution in Visual Studio Code or your preferred IDE</li>
  <li>Modify the <code>docker-compose.override.yml</code> file and remove the <code>ASPNETCORE_HTTPS_PORTS</code> environment variable</li>
  <li>Modify the <code>ports</code> section and specify your custom port number, for example <code>8081:8080</code></li>
  <li>Modify the <code>WebApplication1/Properties/launchSettings.json</code> file and remove the <code>ASPNETCORE_HTTPS_PORTS</code> environment variable</br>
  Modify the <code>ASPNETCORE_HTTP_PORTS</code> environment variable and set it to your custom port number, for example <code>8081</code></li>
  <li>Ensure that the port numbers specified in <code>docker-compose.override.yml</code> and <code>launchSettings.json</code> match.</li>
  <li>Right-click on the <code>docker-compose</code> project and select <code>Build</code></li>
  <li>Right-click on the <code>docker-compose</code> project and select <code>Run</code></li>
  <li>Open your browser and navigate to <code>http://localhost:8081</code> (or your custom port number)</li>
</ol>

<h2>License</h2>
<p>This project is licensed under the MIT License - see the <a href="LICENSE">LICENSE</a> file for details</p>
