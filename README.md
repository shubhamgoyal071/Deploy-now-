<img width="1559" alt="Screenshot 2024-07-14 at 6 18 46 PM" src="https://github.com/user-attachments/assets/28e843b2-73cf-437b-ac2a-0234b8249c84">

# DeployNow

**DeployNow** is a lightweight prototype of a serverless deployment platform. It enables users to deploy applications directly from a GitHub repository. The platform automates the entire process, including cloning the repository, building the application inside a Docker container, storing the build artifacts in AWS S3, and serving the deployed application via a custom domain.

Users can monitor the build process in real-time through WebSocket communication.

> Note: This is a prototype and not intended for production use. Future enhancements are required for authentication, scaling, and robust security.

## Key Features

- Deploy applications via GitHub repository URL
- Build applications using Docker containers
- Store and serve build artifacts from AWS S3
- Map custom domains using a reverse proxy
- Stream real-time build logs using WebSockets and Redis Pub/Sub
- Container orchestration via AWS ECS and image hosting via AWS ECR

## Tech Stack

- **Frontend**: Next.js
- **Backend**: Node.js with Express.js
- **Containerization**: Docker
- **Cloud Storage**: AWS S3
- **Container Orchestration**: AWS ECS, AWS ECR
- **Real-Time Messaging**: Redis Pub/Sub
- **WebSockets**: Socket.IO

## Workflow

1. User submits a GitHub repository URL through the frontend.
2. The backend clones the repository and initiates a Docker build.
3. Upon successful build, the generated artifacts are uploaded to AWS S3.
4. A reverse proxy maps the custom domain to the corresponding application in S3.
5. Build logs are streamed in real-time using Redis Pub/Sub and delivered to the frontend via Socket.IO.

## License

This project is licensed under the Apache 2.0 License.
