# ELK Stack Setup Guide for Windows

This guide will walk you through setting up the ELK stack (Elasticsearch, Logstash, and Kibana) locally on your Windows PC using Docker.

## Prerequisites
- Docker Desktop or Rancher Desktop installed and running on your Windows machine.
- Docker Compose installed.

## Steps to Run the ELK Stack Locally

1. **Download the Repository Files**  
   Clone or download the repository containing the required files.

2. **Place Files in a Directory**  
   Create a directory on your local machine and place the following 4 files from the repository into that directory.

3. **Configure Environment Variables**  
   Open the `.env` file in a text editor and modify the following variables as needed:  
   - Set your passwords (e.g., Elasticsearch password, etc.)
   - Set the encryption key (required length 32)

4. **Start the ELK Stack**  
   Open the Command Prompt and navigate to the directory where you placed the files using the `cd` command:
   ```bash
     cd path\to\your\directory
   ```
   
6. **Run Docker Compose**  
   Once you're in the correct directory, run the following command to start the ELK stack:  
     docker-compose up -d
   
>   **WARNING**
>  If you're using Rancher Desktop, there might be an issue with the virtual memory allocation for Elasticsearch.
>   This can cause the Elasticsearch container to fail to start. To resolve this, follow these steps:
>      1. Open the Rancher Desktop terminal by running the command:
>       ```bash
>          rdctl shell
>       ```
>      2. In the Rancher terminal, run the following command to adjust the virtual memory limit:
>       ```bash
>         sudo sysctl -w vm.max_map_count=262144
>       ```

6. **Verify the ELK Stack is Running**  
   To verify that the containers are running correctly, use the following command:
   ```bash
     docker-compose ps
   ```

8. **Access the ELK Stack**  
   Once the stack is up and running, you can access Kibana via your web browser at the following URL:  
     http://localhost:5601
   
9. **Stop the ELK Stack**  
   To stop the running containers and shut down the ELK stack, run the following command:
   ```bash
     docker-compose down -v
   ```


