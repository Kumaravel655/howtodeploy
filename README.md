# React Project Deployment to GitHub Pages

This guide will help you publish your React project to GitHub Pages.

## Step 1: Ensure Your Project is Ready for Deployment

1. **Create a Production Build**: Ensure that your project is built for production.
    ```sh
    npm run build
    ```
    This command generates a `build` directory with the production-ready version of your React app.

## Step 2: Add `gh-pages` Package

1. **Install `gh-pages` Package**: Install the `gh-pages` package as a dev dependency.
    ```sh
    npm install gh-pages --save-dev
    ```

## Step 3: Update `package.json`

1. **Add a `homepage` Field**: Add a `homepage` field in your `package.json` to specify the base URL for your project.
    ```json
    "homepage": "https://your-username.github.io/your-repo-name"
    ```
    Replace `your-username` with your GitHub username and `your-repo-name` with the name of your repository.

2. **Add Deployment Scripts**: Add `predeploy` and `deploy` scripts to your `package.json`.
    ```json
    "scripts": {
      "predeploy": "npm run build",
      "deploy": "gh-pages -d build",
      "start": "react-scripts start",
      "build": "react-scripts build",
      "test": "react-scripts test",
      "eject": "react-scripts eject"
    }
    ```

## Step 4: Deploy to GitHub Pages

1. **Run Deployment Script**: Use the following command to deploy your app to GitHub Pages.
    ```sh
    npm run deploy
    ```

## Example `package.json`

Here’s an example of how your `package.json` should look after these changes:

```json
{
  "name": "your-project-name",
  "version": "0.1.0",
  "private": true,
  "homepage": "https://your-username.github.io/your-repo-name",
  "dependencies": {
    "react": "^17.0.2",
    "react-dom": "^17.0.2",
    "react-scripts": "4.0.3"
  },
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "predeploy": "npm run build",
    "deploy": "gh-pages -d build"
  },
  "devDependencies": {
    "gh-pages": "^3.2.3"
  }
}
