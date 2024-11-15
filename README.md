# bricolo

```bricolo``` is a streamlined development tool that enhances your PHP projects by automating common tasks like launching a PHP server, live-reloading with browser sync, and automatically compiling Sass and TypeScript. With a single command, you can set up a fully integrated development environment for both front-end and back-end workflows.

### Features

- Launch a PHP server with automatic configuration.

- Live-build and compile Sass and Typescript on file changes.

- Instant browser reloading with hot reloading support.

- Simple setup with one command.


<details open="open">
    <summary>Table of Contents</summary>
    <ul>
        <li><a href="#installation">Installation</a></li>
        <li><a href="#configuration">Configuration</a></li>
        <li><a href="#usage">Usage</a></li>
        <li><a href="#contact">Contact 📧</a></li>
    </ul>
</details>

## Installation

To install ```bricolo```, use npm:

```bash
npm install bricolo@latest
``` 

Ensure that you have the following dependencies installed:

- Node.js (v12 or higher)
- PHP (for the built-in server)

Sass and TypeScript are automatically handled, so you don’t need to worry if they aren’t pre-installed in your project.

## Configuration

```bricolo``` uses two configuration files: 

1. A default configuration located in the package's directory (```config.json```)

2. An optional user configuration that you can create at the root of your project (```bricoloconfig.json```), which can override the default settings.

### Default values

Here is the default configuration file ```config.json```

```json
{
    "phpServer": {
        "port": 8000,
        "command": "php -S localhost:{port} -t dist/"
    },
    "jsBuild": {
        "entry": "src/js/app.ts",
        "output": "dist/js/bundle.js"
    },
    "sassBuild": {
        "entry": "src/scss/styles.scss",
        "output": "dist/css/style.min.css"
    },
    "watch": {
        "directories": [
            "src/**/*"
        ]
    },
    "server": {
        "port": 8080
    }
}
```

### Configuration parameters

- **phpServer.port**: The port on which the PHP server will run.

- **phpServer.command**: The command to run the PHP server (support placeholder for the port).

- **jsBuild.entry**: Path to the TypeScript/JavaScript entry file for ```esbuild```.

- **jsBuild.output**: Path where the output JavaScript bundle will be generated.

- **jsBuild.output**: Path where the output JavaScript bundle will be generated.

- **sassBuild.entry**: Path to the Sass entry file.

- **sassBuild.output**: Path where the compiled CSS will be saved.

- **server.port**: The port for the live-reloading server (```browser-sync```).

- **watch.directories**: List of directories or files to watch for changes to trigger browser reload.

### Default structure

After installation, you can run the *initiate* script to create the default project structure at the root of your project. This script sets up a basic folder structure with default TypeScript and Sass files, like described in the default ```config.json``` file.

In order to run this script, please type: 

```bash
npx bricolo init
``` 

You'll be prompted: 

```bash
Would like to create the default structure? [no, yes]:  (no)
```

If you choose **Y**, the following structure will be created. 

```bash 
src/
    js/
        app.ts         # Default TypeScript file
    scss/
        styles.scss    # Default Sass file
dist/
    css/
    js/
    index.php
```

**Example Default files**

- app.ts:
```typescript
// Default TypeScript file
console.log("Hello, TypeScript!");
```

- styles.scss
```scss
// Default SASS file
body {
    background-color: #f0f0f0;
}
```

If you prefer to skip this step, simply respond N to the prompt, and you can always create the structure manually later. Just make sure your ```bricoloconfig.json``` matches the structure of your files.

## Usage

Once the package is installed and configured, we strongly recommand to add the following script in the ```package.json```: 

```bash
{
    "scripts": {
        "serve": "bricolo serve"
    }
}
```

Then just run the command ```npm run serve```. Alternatively, you can directly type ```npx bricolo serve``` in you terminal, without creating a script in you ```package.json```. This will: 

- Start a PHP server on the configured port.

- Automatically build and watch your Sass and TypeScript files.

- Refresh the browser in real-time when files are modified.

### Example Workflow

1. Edit your ```src/scss/styles.scss``` or ```src/js/app.ts```

2. Watch the changes live-build and reload in the browser.

3. Enjoy a smoother front-end/back-end development cycle.

## Contact

If you have any question about this package, how to install, to use or to improve, feel free to contact me:

Antoine Bollinger - [LinkedIn](https://www.linkedin.com/in/antoinebollinger/) - [antoine.bollinger@gmail.com](mailto:antoine.bollinger@gmail.com)

You can talk to me in 🇫🇷, 🇧🇷 or 🇬🇧.
