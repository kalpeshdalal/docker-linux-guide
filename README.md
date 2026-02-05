
# WSL Installation & Database Setup Guide



## WSL Installation

1. Install WSL  
   ```bash
   wsl --install
   ```
2. Restart Computer
3. Enter the Linux Environment  
   ```bash
   wsl
   ```
4. Update the package list  
   ```bash
   sudo apt update
   ```
5. Install Docker  
   ```bash
   sudo apt install docker.io -y
   ```
6. Start the Docker engine  
   ```bash
   sudo service docker start
   ```
7. Stop Docker service  
   ```bash
   sudo service docker stop
   ```
8. Kill the Linux subsystem and free resources (PowerShell)  
   ```powershell
   wsl --shutdown
   ```

---

## Set-up Databases

### PostgreSQL
Run the following command:
```bash
sudo docker run --name my-postgres -e POSTGRES_PASSWORD=admin -p 5432:5432 -d postgres
```

- **Username:** postgres  
- **Password:** admin  

---

### MongoDB
Run the following command:
```bash
sudo docker run --name my-mongo -d -p 27017:27017 -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=admin mongo
```

- **Username:** admin  
- **Password:** admin  

---

## Usage Steps

- Start Ubuntu (PowerShell):  
  ```powershell
  wsl
  ```
  **Password:** `KalpeshDalal@1008`

- Exit Ubuntu:  
  ```bash
  exit
  ```

- Start Docker engine:  
  ```bash
  sudo service docker start
  ```

- List all Docker running services:  
  ```bash
  sudo docker ps -a
  ```

- Start PostgreSQL:  
  ```bash
  sudo docker start my-postgres
  ```

- Start MongoDB:  
  ```bash
  sudo docker start my-mongo
  ```

- Stop specific service (MongoDB):  
  ```bash
  sudo docker stop my-mongo
  ```

- Stop all services:  
  ```bash
  sudo docker stop $(sudo docker ps -q)
  ```

---

## Maintenance Commands

- Remove Docker container (MongoDB):  
  ```bash
  sudo docker rm -f my-mongo
  ```

- Check live resource usage:  
  ```bash
  sudo docker stats
  ```

