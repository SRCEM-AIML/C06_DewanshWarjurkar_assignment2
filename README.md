Student Project – Multi-App Django Application
This is a Django-based multi-app project containerized with Docker and deployed using a Jenkins CI/CD pipeline.

Technologies Used

Framework: Django (no database)

Containerization: Docker

CI/CD Automation: Jenkins

Deployment: Docker Hub

📁 Project Structure

StudentProject/ ← Django project root
├── app1/ ← App containing homepage
├── app2/ ← App containing sample content
├── templates/ ← Global HTML templates
Dockerfile ← Instructions to containerize the app
Jenkinsfile ← Jenkins pipeline definition

Run Using Docker

To build and run the Docker container locally:

docker build -t dewanstudent/studentproject .
docker run -p 9090:9090 dewanstudent/studentproject

Open your browser and visit: http://127.0.0.1:9090/

Pull from Docker Hub

Instead of building manually, you can use the prebuilt image:

docker pull dewanstudent/studentproject:latest
docker run -p 9090:9090 dewanstudent/studentproject

The app will be available at: http://127.0.0.1:9090/

Jenkins CI/CD Pipeline

This project includes a Jenkinsfile for automating the following:

Pull the latest code from GitHub

Build a Docker image

Push the image to Docker Hub

The pipeline is triggered automatically upon each GitHub commit.

Important Links

GitHub Repository: https://github.com/SRCEM-AIML/C06_DewanshWarjurkar_assignment2

Docker Hub Image: https://hub.docker.com/r/dewanstudent/studentproject

✅ Summary

This project demonstrates a production-style DevOps pipeline using:

Django (multi-app)

Docker containerization

Jenkins CI/CD pipeline

Docker Hub deployment
