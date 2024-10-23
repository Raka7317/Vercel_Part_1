# Vercel Part 1
### Setup Guide

This Project contains following services and folders:

- `api-server`: HTTP API Server for REST API's
- `build-server`: Docker Image code which clones, builds and pushes the build to S3
- `s3-reverse-proxy`: Reverse Proxy the subdomains and domains to s3 bucket static assets

### Local Setup

1. Run `npm install` in all the 3 services i.e. `api-server`, `build-server` and `s3-reverse-proxy`
2. Docker build the `build-server` and push the image to AWS ECR.
3. Setup the `api-server` by providing all the required config such as TASK ARN and CLUSTER arn.
4. Run `node index.js` in `api-server` and `s3-reverse-proxy`

At this point following services would be up and running:

| S.No | Service            | PORT    |
| ---- | ------------------ | ------- |
| 1    | `api-server`       | `:9000` |
| 2    | `socket.io-server` | `:9002` |
| 3    | `s3-reverse-proxy` | `:8000` |

### Demo

[Watch The Demo Video](https://imgur.com/I6KgmNR)

### Architecture

![Vercel Clone Architecture](https://i.imgur.com/r7QUXqZ.png)

Here's a sample README for your Vercel clone project:

---

# Vercel Clone

## Overview

This project is a Vercel-like platform built using **System Design principles**, **AWS**, **Docker**, **Redis**, **S3**, and **Next.js**. It automates the process of deploying web applications by simply providing a GitHub repository URL. Once the URL is provided, the system fetches the project, builds it, and deploys it automatically to a cloud environment, streamlining the entire deployment process.

## Features

- **Automated Deployment**: Simplifies deployment by automatically building and deploying applications upon receiving a GitHub repository URL.
- **GitHub Integration**: Direct integration with GitHub to fetch and deploy projects from repositories.
- **Scalability**: Built with System Design principles to ensure that the platform can handle large-scale deployments efficiently.
- **AWS Infrastructure**: Uses various AWS services to manage the backend infrastructure.
- **Dockerized Builds**: Each project is containerized using Docker to provide a consistent build and runtime environment.
- **Redis Caching**: Utilizes Redis for caching and enhancing application performance.
- **S3 Storage**: All assets and deployment files are stored securely on AWS S3.
- **Next.js Framework**: Provides a modern, server-rendered frontend framework with React.

## Tech Stack

- **System Design**: Structured to be scalable and fault-tolerant.
- **AWS**: 
  - EC2 for hosting backend services.
  - S3 for asset and file storage.
  - Lambda for serverless functions.
- **Docker**: Containerizes each project for isolation and ease of deployment.
- **Redis**: Used for caching and improving overall system performance.
- **S3**: Manages storage for deployment assets.
- **Next.js**: Frontend framework built on top of React, providing server-side rendering and optimized performance.

## Setup and Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/vercel-clone.git
   cd vercel-clone
   ```

2. **Install Dependencies**:
   Install the required dependencies using npm or yarn.
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Set up Environment Variables**:
   Create a `.env` file in the root directory and add the necessary environment variables for AWS, Redis, and other services:
   ```bash
   AWS_ACCESS_KEY_ID=<your-access-key>
   AWS_SECRET_ACCESS_KEY=<your-secret-key>
   REDIS_URL=<your-redis-url>
   ```

4. **Run Docker**:
   Ensure Docker is installed and running. Build the Docker containers:
   ```bash
   docker-compose up --build
   ```

5. **Start the Application**:
   Start the application in development mode:
   ```bash
   npm run dev
   ```

   The application will be available at `http://localhost:3000`.

## How It Works

1. **Submit GitHub URL**: The user provides a GitHub repository URL via the platform's UI.
2. **Fetch & Build**: The system fetches the project, creates a Docker container, and builds the application using the provided configuration.
3. **Deployment**: Once the build is successful, the application is deployed to AWS infrastructure. Assets are stored in S3, and the system is ready to serve requests.
4. **Automated Scaling**: The platform automatically scales based on the traffic and requirements, ensuring high availability.

## Future Improvements

- **Custom Domain Support**: Allow users to deploy projects with custom domains.
- **More Cloud Providers**: Expand deployment options beyond AWS to other cloud providers like GCP and Azure.
- **Advanced Monitoring**: Implement detailed analytics and monitoring for each deployment.

## Contributing

Contributions are welcome! Feel free to submit pull requests or open issues for feature requests and bug fixes.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

This README should give users and developers a clear understanding of the project, its features, setup, and future goals. Let me know if you'd like to customize any part of it further!
