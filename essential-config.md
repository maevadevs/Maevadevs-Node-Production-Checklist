# Essential Configurations

## Use Reverse Proxy

- Have Apache or Nginx as the proxy server that listen on port 80/443 and forward to the application to a specific port or route
- You can setup multiple Node application using this system
- When running reverse proxy, make sure only the reverse proxy Server can communicate to your app
- Restrict the SSH access to the specific network or VPN to prevent the outside access

## Use Cluster Mode

- To take advantage of multiple core, make use of clusters
- It is better to manage this using the `PM2` module

## Less CPU Intensive Tasks

- Node is great for I/O tasks but not for CPU intensive tasks
- If needed, deleguate those to  external resources and run asyn with Node

## No `eval`, `setTimeout`, `setInterval`

- Also, `setTimeout` and `setInterval` make use of `eval` in the background

## Use a Linter

- This helps catch a lot of bugs at coding time

## Use Testing

- Unit tests and Integration tests are simply best programming practices

## Never Use `sudo`

- Running `sudo node app.js` opens a lot of vulnerability at runtime
