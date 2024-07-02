# React Project Deployment to GitHub Pages

This guide will help you publish your React project to GitHub Pages.
# Vite React App

This project is a React application built with Vite. It demonstrates how to deploy a Vite React app to GitHub Pages.

## Prerequisites

- Node.js installed on your machine
- A GitHub account

## Steps to Deploy

1. **Set up your project for deployment:**

    Ensure your `package.json` is configured correctly. Add the `homepage` field to specify the URL of your GitHub Pages site:
    ```json
    {
      "name": "your-project-name",
      "version": "0.1.0",
      "private": true,
      "homepage": "https://yourusername.github.io/your-repo-name",
      ...
    }
    ```

2. **Install gh-pages package:**

    You need the `gh-pages` package to deploy your application. Install it using npm or yarn:
    ```sh
    npm install --save-dev gh-pages
    ```
    or
    ```sh
    yarn add --dev gh-pages
    ```

3. **Update your build and deploy scripts:**

    Modify the `scripts` section in your `package.json` to include the deploy script:
    ```json
    "scripts": {
      "build": "vite build",
      "predeploy": "npm run build",
      "deploy": "gh-pages -d dist",
      ...
    }
    ```

4. **Configure Vite for GitHub Pages:**

    Ensure your `vite.config.js` (or `vite.config.ts` if using TypeScript) is configured to use the correct base path. Add or update the `base` property:
    ```javascript
    import { defineConfig } from 'vite';
    import react from '@vitejs/plugin-react';

    export default defineConfig({
      plugins: [react()],
      base: '/your-repo-name/', // This is the base URL of your GitHub Pages site
    });
    ```

5. **Build and Deploy:**

    Now you can build and deploy your application with the following command:
    ```sh
    npm run deploy
    ```

 
