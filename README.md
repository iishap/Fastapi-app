

# 🚀 FastAPI Trading Orders API  

A simple FastAPI-based REST API that allows users to submit and retrieve trade orders. It supports WebSocket for real-time updates and is containerized using Docker. The application uses PostgreSQL as the database and is deployed on AWS EC2.  

## 📌 Features  

- **REST API:**  
  - `POST /orders/` → Submit a trade order  
  - `GET /orders/` → Fetch all submitted orders  
- **Database:** PostgreSQL (configured via Docker Compose)  
- **WebSocket Support:** Real-time updates on trade orders  
- **Dockerized:** Deployable as a containerized service  
- **AWS Deployment:** Hosted on EC2 with Docker  

## 🏗️ Tech Stack  

- **Backend:** FastAPI  
- **Database:** PostgreSQL  
- **Containerization:** Docker, Docker Compose  
- **Deployment:** AWS EC2  


## 🛠️ Installation & Setup  

### 1️⃣ Clone the Repository  

```bash
git clone https://github.com/iishap/Fastapi-app.git
cd Fastapi-app
```

### 2️⃣ Set Up Environment Variables  

Create a `.env` file in the project root and define the required variables:

```env
DATABASE_URL=postgresql://postgres:password@db:5432/trading_db
```

## 🐳 Running the Application with Docker  

### 1️⃣ Build & Start Containers  

```bash
docker-compose up --build -d
```

### 2️⃣ API Endpoints  

Once running, access the API at:  

📌 **Swagger UI:** [`http://localhost:8000/docs`](http://localhost:8000/docs)  
📌 **Redoc UI:** [`http://localhost:8000/redoc`](http://localhost:8000/redoc)  


## 🚀 Deployment on AWS  

### 1️⃣ Launch an EC2 Instance (Ubuntu)  
- Create an **AWS EC2 instance**  
- SSH into the instance:

```bash
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

### 2️⃣ Install Docker  

```bash
sudo apt update && sudo apt install -y docker.io docker-compose
```

### 3️⃣ Clone the Repo & Run Containers  

```bash
git clone https://github.com/iishap/Fastapi-app.git
cd Fastapi-app
docker-compose up --build -d
```

### 4️⃣ Access the API  

Use `http://your-ec2-public-ip:8000/docs` to check if the API is running.  


## 🔄 CI/CD (Optional)  

To automate deployment, set up **GitHub Actions** to build and push the Docker image to AWS.  


## 📜 API Reference  

### ➤ **POST /orders/**  

**Request Body:**
```json
{
  "symbol": "BTCUSDT",
  "price": 45000.50,
  "quantity": 2,
  "order_type": "buy"
}
```

**Response:**
```json
{
  "id": 1,
  "symbol": "BTCUSDT",
  "price": 45000.5,
  "quantity": 2,
  "order_type": "buy"
}
```


### ➤ **GET /orders/**  

Returns all submitted orders.  

### ➤ **WebSocket Connection**  

Connect to WebSocket at:  
`ws://your-ec2-public-ip:8000/ws`  

Send and receive real-time order updates.  

## 🎯 Future Improvements  

- Add authentication (JWT)  
- Implement CI/CD pipeline  
- Improve WebSocket functionality  

