# Staging Application

This is the staging environment for the application.

## Setup

1. Install dependencies:
   ```bash
   npm install --production
   ```

2. Start the application:
   ```bash
   npm start
   ```

## Environment Variables

- `PORT`: Server port (default: 3000)

## Endpoints

- `/` - Main application
- `/health` - Health check endpoint

## Deployment

This application is automatically deployed via GitHub Actions when changes are pushed to the `staging` branch.