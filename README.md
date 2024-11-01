```markdown
# Next.js Project with Docker Support

This project is a [Next.js](https://nextjs.org) application bootstrapped with [`create-next-app`](https://nextjs.org/docs/app/api-reference/cli/create-next-app).

## Getting Started

### Running in Development Mode

To start the development server, use one of the following commands:

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

### Running the Application with Docker

To run this Next.js application using Docker, follow these steps:

#### 1. **Build the Docker Image**

Make sure Docker is installed and running on your machine. Open your terminal in the project directory and run the following command to build the Docker image:

```bash
docker build -t nextjs-app .
```

This command creates a Docker image named `nextjs-app` based on the `Dockerfile` in the project directory.

#### 2. **Run the Docker Container**

After the image has been built, you can start a container to run the app. Use this command:

```bash
docker run -p 3000:3000 nextjs-app
```

This command runs the container and maps port `3000` in the container to port `3000` on your local machine. You can access the application by opening [http://localhost:3000](http://localhost:3000) in your web browser.

#### 3. **Additional Docker Commands**

- **To Stop the Running Container:**  
  Find the `CONTAINER ID` using:
  ```bash
  docker ps
  ```
  Then, stop it with:
  ```bash
  docker stop <container_id>
  ```

- **To Remove the Image:**  
  If you want to delete the Docker image after stopping the container, run:
  ```bash
  docker rmi nextjs-app
  ```

#### 4. **Environment Variables**

If your app uses environment variables, create a `.env` file in the project root and include any necessary environment variables. Make sure to add `.env` to `.dockerignore` to prevent it from being copied directly into the Docker image. Instead, you can pass environment variables at runtime:

```bash
docker run -p 3000:3000 --env-file .env nextjs-app
```

#### 5. **Building for Production**

For production, adjust the `Dockerfile` to optimize for a smaller image size or use multi-stage builds.

---

Your Next.js application is now fully dockerized, and you can use these instructions to run it in a containerized environment.
```
