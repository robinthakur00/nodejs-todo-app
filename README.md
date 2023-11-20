# NodeJS Todo App

This repository contains a simple NodeJS Todo App application for managing todo items.

## Overview

This NodeJS Todo App provides basic functionality to create, read, update, and delete todo items.

## Prerequisites

- Node.js (v14.x or higher)
- npm (Node package manager)
- AWS Account

## Setup

1. Clone the repository:

    ```bash
    git clone https://github.com/robinthakur00/nodejs-todo-app.git
    ```

2. Install dependencies:

    ```bash
    npm install
    ```

3. Start the application:

    ```bash
    npm start
    ```

4. Access the app in a web browser at `http://localhost:8000/`


## Usage

- Modify the application logic in `app.js` to extend or customize functionality.
- Update the HTML views in the `views/` directory for UI changes.
- Use additional npm packages or libraries as needed.

## Deploying to AWS with Jenkins Pipeline

Automate deployment using Jenkins Pipeline on AWS:

1. **Set up Jenkins:**
    - Install Jenkins on an AWS EC2 instance.
    - Configure Jenkins with necessary plugins (e.g., Git, AWS).

2. **Create Jenkins Pipeline:**
    - Create a Jenkins job with a Jenkinsfile written in Groovy.
    - Jenkinsfile includes stages for:
        - Fetch the code from Git.
        - Creating a Docker image.
        - Pushing the image to Docker Hub.
        - Deploy the application using Docker Compose

3. **AWS Configuration:**
    - Configure AWS IAM roles for Jenkins to access AWS services.
    - Set up security groups, IAM roles, and permissions for EC2 instances.
    - Configure necessary networking settings to access the application.

4. **Execute Pipeline:**
    - Run the Jenkins Pipeline job to trigger the deployment process.
    - Jenkins Pipeline automates building, pushing Docker images, and deploying the app on AWS.

## Contributing

Contributions are welcome! Fork the repository, make changes, and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

