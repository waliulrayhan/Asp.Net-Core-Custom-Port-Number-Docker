<h1>Custom Port Number Docker ASP.NET Core</h1>

<p>This repository provides instructions and configurations to customize the port number for an ASP.NET Core application running in Docker using docker-compose.</p>

<h2>Setup Instructions</h2>

<ol>
    <li>
        <h3>Modify docker-compose.override.yml</h3>

        <p>Remove the <code>- ASPNETCORE_HTTPS_PORTS</code> entry and set your custom port number in the <code>ports</code> section. Replace <code>8081</code> with your desired port number:</p>

        <pre><code>ports:
  - "8081:8080"
</code></pre>
    </li>
    <li>
        <h3>Update ASP.NET Core Configuration</h3>

        <p>Update the port number in <code>WebApplication1/Properties/launchSettings.json</code>. Under the <code>Docker</code> configuration, set the <code>ASPNETCORE_HTTP_PORTS</code> environment variable to your custom port number (e.g., <code>8081</code>):</p>

        <pre><code>"Docker": {
      "commandName": "Docker",
      "launchBrowser": true,
      "launchUrl": "{Scheme}://{ServiceHost}:{ServicePort}",
      "environmentVariables": {
        "ASPNETCORE_HTTP_PORTS": "8081"
      }
    }
</code></pre>

        <p>Ensure that the port numbers specified in <code>docker-compose.override.yml</code> and <code>launchSettings.json</code> match.</p>
    </li>
</ol>

<h2>Usage</h2>

<p>Once the configurations are updated, build and run your ASP.NET Core application using Docker. Your application will now be accessible through the specified custom port number.</p>

</body>
</html>
