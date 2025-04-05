# 🖧 Simple TCP Server in Go

Welcome to the **Simple TCP Server**, a lightweight and concurrent TCP server built with Go!  
It listens for incoming connections, receives messages from clients, and logs them along with the sender's IP address. Perfect for learning or lightweight communication between systems.

---

## ✨ Features

✅ Accepts multiple simultaneous TCP client connections  
✅ Reads incoming messages and prints them with sender info  
✅ Responds to clients with `"Message received"`  
✅ Uses goroutines for efficient concurrency  
✅ Buffered message channel to prevent blocking

---

## ⚙️ Requirements

- ✅ [Go 1.18+](https://golang.org/dl/) installed  
- ✅ Terminal or shell access (Linux, macOS, or Windows)

---

## 🚀 Getting Started

### 🧾 Step 1: Clone the Repository or Copy the Code

```bash
git clone https://github.com/your-username/go-tcp-server.git
cd go-tcp-server
```

Or create a file manually:

```bash
touch main.go
```
Paste the server code into `main.go`.

---

### 🛠️ Step 2: Run the Server

```bash
go run main.go
```

You should see:
```
Listening on :3000
```

🔁 To build a binary:
```bash
go build -o tcp-server main.go
./tcp-server
```

---

## 🧪 Test the Server

Open a separate terminal and connect using `nc` or `telnet`.

### 🧰 Using Netcat (`nc`)

```bash
nc localhost 3000
```

### 🧰 Using Telnet

```bash
telnet localhost 3000
```

Type a message and hit Enter. The server will:

📩 Respond with:  
```
Message received
```

🖨️ Print to the console:  
```
Received message (127.0.0.1:PORT): Your message here
```

---

## 💬 Example Messages

```txt
Hello, server!
{"type": "ping", "status": "ok"}
This is a multiline
test message!
🚀 Go is awesome!
```

---

## ⚙️ Configuration

To change the port the server listens on, update this line in `main.go`:

```go
server := NewServer(":3000")
```

Change `":3000"` to any other port like `":4000"`.

---

## 🔧 Ideas for Improvements

🧠 Want to make this server even better? Here are some suggestions:

- 🔌 Graceful shutdown with `os.Signal`
- 🛡️ Client IP filtering or authentication
- 📝 Structured logging using `logrus` or `zap`
- 📤 Broadcast messages to all connected clients (chat server style!)
- 📊 Metrics or logging to file
- ⏱️ Add read/write timeouts for better resilience

---

## 🧪 Testing Multiple Clients

Open several terminals and run:

```bash
nc localhost 3000
```

Each connection can send messages independently!

---

## 📁 File Structure

```
.
├── main.go       # TCP server implementation
├── README.md     # Project documentation
```

---