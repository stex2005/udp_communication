# C++ UDP Communication Library

Lightweight C++ library for **real-time UDP communication** between processes, computers, or embedded systems. 
Designed for **robotic control**, **teleoperation**, and **distributed real-time systems** where deterministic and low-latency data exchange is critical.

---

## Features

- **Bidirectional UDP sockets** for send/receive operations 
- **Low-latency, non-blocking I/O** suitable for control loops 
- **Header-only architecture** for easy integration 
- **Cross-platform support** (Linux, WSL) 
- Optional **timestamping and packet rate monitoring** 
- Simple API designed for robotics and control applications 

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/stex2005/udp_communication.git
cd udp_communication
```

### 2. Build (example)

```bash
mkdir build && cd build
cmake ..
make
```

### 3. Run demo

```bash
./udp_example_server
./udp_example_client
```

---

## Example Usage

```cpp
#include "udp_comm.hpp"

int main() {
    UDPServer server(9000);
    UDPClient client("127.0.0.1", 9000);

    client.send("Hello from client!");
    std::string msg = server.receive();
    std::cout << "Server received: " << msg << std::endl;
}
```

---

## Integration

Add this repository as a submodule or include the header directly:

```bash
git submodule add https://github.com/stex2005/udp_communication.git external/udp_comm
```

Then include it in your project:

```cpp
#include "udp_comm.hpp"
```

---

## Applications

- Real-time control of robotic systems 
- Sensor and actuator data streaming 
- Teleoperation and haptic feedback pipelines 
- Multi-process or multi-computer communication 

---

## License

This project is released under the **Apache License 2.0**. 
Feel free to use and modify it for research or industrial applications.

---

> Developed by **[Stefano Dalla Gasperina](https://github.com/stex2005)** — Austin, TX
