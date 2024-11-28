# 

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 18.2.11.

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The application will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via a platform of your choice. To use this command, you need to first add a package that implements end-to-end testing capabilities.

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI Overview and Command Reference](https://angular.dev/tools/cli) page.


## Project Notes


# Configuring a New Angular Project with Angular CLI

# 1. Install Angular CLI (if not already installed)
npm install -g @angular/cli

# 2. Create a New Angular Project
ng new project-name

# 3. Options During Project Creation
# - Choose routing (Yes/No) based on project requirements.
# - Select the preferred stylesheet format (CSS, SCSS, Sass, or Less).

# 4. Navigate to the Project Directory
cd project-name

# 5. Serve the Application Locally
ng serve
# Default URL: http://localhost:4200

# 6. Add Routing to the Project (if not added initially)
ng generate module app-routing --flat --module=app

# 7. Add a Component
ng generate component component-name

# 8. Add a Service
ng generate service service-name

# 9. Add External Dependencies
# Install required packages using npm or yarn.
npm install package-name
# Example: npm install @angular/material

# 10. Configure Proxy for API Calls (Optional)
# Create a proxy.conf.json file:
{
  "/api": {
    "target": "http://backend-url",
    "secure": false,
    "changeOrigin": true
  }
}
# Update angular.json to use the proxy:
# "serve": {
#   "options": {
#     "proxyConfig": "proxy.conf.json"
#   }
# }
# Serve the app using the proxy:
ng serve

# 11. Configure Environment Files
# Edit src/environments/environment.ts for development configurations.
# Edit src/environments/environment.prod.ts for production configurations.

# 12. Build the Project
ng build --configuration=production
# Output: /dist/project-name

# 13. Lint the Code
ng lint

# 14. Run Tests
ng test        # Run unit tests.
ng e2e         # Run end-to-end tests.

# 15. Add Strict Mode (Optional for Enhanced TypeScript Configuration)
ng new project-name --strict
# Adds stricter TypeScript checks and better code quality.

# 16. Use Angular CLI Help for More Options
ng help



# Managing Multiple Projects in a Single Angular Workspace

# 1. Create a Workspace Without an Application
ng new workspace-name --no-create-application

# 2. Add a New Application
ng generate application app-name
# Creates the application in projects/app-name.
# Applications are independent and can have their own configurations.

# 3. Add a New Library
ng generate library lib-name
# Creates the library in projects/lib-name.
# Libraries can be shared across applications in the workspace.

# 4. Serve an Application
ng serve --project app-name
# Serves the specified application.

# 5. Build an Application or Library
ng build --project project-name
# Replace project-name with the application or library name.

# 6. Add Routing to an Application
ng generate module app-routing --project app-name --flat --module=app
# Adds routing for the specified application.

# 7. Add Components, Services, or Modules
ng generate component component-name --project app-name
ng generate service service-name --project app-name
ng generate module module-name --project app-name
# Generates components, services, or modules inside the specified application.

# 8. Configuration
# All projects are configured in the angular.json file under the "projects" section.
# Each project has its own build, serve, and test configurations.

# 9. Use a Library in an Application
# Import the library module into the consuming application's module:
import { LibModule } from 'lib-name';
@NgModule({
  imports: [LibModule]
})
export class AppModule { }

# 10. Helpful Commands
# List all projects in the workspace:
ng config projects

# Run unit tests for a specific project:
ng test --project project-name

# Lint a specific project:
ng lint --project project-name


# Difference Between Angular Application and Library

# 1. Purpose
# Application: A runnable Angular project meant to be deployed and accessed by end-users.
# Library: A reusable set of components, services, or modules meant to be shared across applications.

# 2. Location in Workspace
# Application: Created in the `projects/app-name` directory.
# Library: Created in the `projects/lib-name` directory.

# 3. Execution
# Application: Can be served and run directly using `ng serve`.
# Library: Cannot be served directly. It needs to be imported and used in an application.

# 4. Build Output
# Application: Produces a full deployable build in the `/dist/app-name` folder.
# Library: Produces a packageable build in the `/dist/lib-name` folder, which can be published to npm or used locally.

# 5. Dependencies
# Application: Can include libraries and other external packages to build the UI or functionality.
# Library: Should avoid application-specific dependencies and focus on general-purpose reusable logic.

# 6. Usage
# Application: Designed for end-users (e.g., a web app, admin panel, etc.).
# Library: Designed for developers to use as part of multiple applications.

# 7. Commands to Generate
# Application:
ng generate application app-name

# Library:
ng generate library lib-name


# Step-by-Step Guide to Host an Angular Project on GitHub Pages

# 1. Build the Angular Project for Production
ng build --output-path=dist --base-href /repository-name/
# Replace "repository-name" with your GitHub repository name.
# Example: ng build --output-path=dist --base-href /my-angular-project/

# 2. Install Angular CLI GitHub Pages Tool (if not installed)
npm install -g angular-cli-ghpages

# Key Details:
Command: ngh
# Stands for NG (Angular) and GH (GitHub Pages).
Purpose: Simplifies the process of building your Angular app and publishing it to a gh-pages branch on GitHub.

# 3. Deploy the Project to GitHub Pages
ngh --dir=dist
# This deploys the `dist` folder to the `gh-pages` branch of your GitHub repository.

# 4. Verify Deployment
# - Go to your GitHub repository.
# - Navigate to "Settings" > "Pages."
# - Ensure the source branch is set to `gh-pages`.
# - Your project should be available at: https://your-username.github.io/repository-name/

# 5. Push Changes to Main Branch (Optional)
git add .
git commit -m "Deployed Angular project to GitHub Pages"
git push origin main

# 6. Re-Deploy After Making Changes
# - Make updates to your Angular project.
# - Rebuild the project:
ng build --output-path=dist --base-href /repository-name/
# - Re-deploy using Angular CLI GitHub Pages:
ngh --dir=dist

# Notes:
# - Ensure your GitHub repository is already initialized and has a remote origin set.
# - If using a custom domain, configure a `CNAME` file in your GitHub Pages settings.

# if error on deploy
# error -
ngh --dir=dist/angular-events
# index.html could not be copied to 404.html. Proceeding without it.
# Diagnostic info: ENOENT: no such file or directory, lstat 'D:\web\learning\angular\dist\angular-events\index.html'
# To fix this issue, explicitly specify the correct directory when running the ngh command:
ngh --dir=dist/angular-events/browser
# following command to rebuild your Angular project, ensuring it outputs the expected files:
ng build angular-events --configuration production --base-href /angular-events/
# Clean the Cache and Retry: If the issue persists, try cleaning up and reinitializing the GitHub Pages deployment:

ngh --dir=dist/angular-events/browser --no-silent
## Test the Deployed Application
https://droidnitish.github.io/angular/angular-event
