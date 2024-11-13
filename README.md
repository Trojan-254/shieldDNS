# ShieldNet DNS Server

![Rust](https://github.com/EmilHernvall/hermes/workflows/Rust/badge.svg)

ShieldNet is a highly efficient, secure, and feature-rich DNS server built with **safe Rust**. Whether you're a developer managing a complex local network, a system administrator overseeing multiple zones, or a security-conscious individual wanting more control over your DNS queries, ShieldNet provides a comprehensive solution. It stands out due to its performance, configurability, and the underlying robustness of Rust, making it an ideal choice for anyone needing a custom DNS solution.

## Key Features

### **High Performance with Safe Rust**
Built using **Rust**, ShieldNet leverages the language’s memory safety and performance characteristics to deliver a fast and secure DNS server. Rust’s strong typing, concurrency support, and zero-cost abstractions ensure that the server runs efficiently, even under high loads, with minimal risk of runtime errors.

### **Recursive Resolution with Root Server Support**
ShieldNet excels in its ability to resolve DNS queries recursively using the Internet's root servers directly. This ensures that you don’t have to rely on third-party DNS providers, reducing the risk of DNS manipulation or privacy issues. The recursive resolution mechanism is optimized for speed and accuracy, providing quick lookups while maintaining full DNS integrity.

### **DNS Forwarding Mode**
In addition to recursive resolution, ShieldNet can operate in **forwarding mode**, passing DNS queries to a specified DNS server of your choice. This flexibility allows you to integrate it with other DNS services, create a hybrid DNS setup, or forward queries to specialized DNS providers that offer additional features like filtering or enhanced security.

### **Authoritative DNS Server**
ShieldNet allows you to define your own **authoritative DNS zones**, enabling you to manage your DNS records and offer authoritative answers for custom domains. This feature is crucial for anyone running their own domain infrastructure or private network and looking for complete control over DNS resolution.

### **Compact API for Zone and Cache Management**
ShieldNet offers a **compact and efficient API** that allows you to manage DNS zones and caching behavior seamlessly. The API supports both **JSON** and **HTML** formats, ensuring easy integration with existing systems or simple human-readable outputs for administrative purposes. Whether you're automating DNS record management or querying cache statistics, the API makes it all possible with minimal overhead.

### **Comprehensive Caching System**
One of the most important aspects of any DNS server is its ability to **cache** records efficiently. ShieldNet has been designed with a **highly optimized cache system** that reduces the need for repeated DNS lookups, improving response time and reducing network traffic. The cache can be easily monitored and cleared through the API, giving you full control over how DNS data is stored and reused.

### **Easy to Configure and Operate**
ShieldNet is designed for ease of use, with simple **command-line options** for configuration. Whether you're setting it up for the first time or managing an ongoing DNS infrastructure, the configuration process is straightforward and intuitive. Detailed logging and error reporting also help users diagnose issues quickly, providing transparency into the system’s behavior.

### **Security-Focused Design**
Security is paramount in the design of ShieldNet. By resolving queries recursively from trusted root servers, it minimizes exposure to potential attacks from compromised DNS servers. Additionally, the server supports DNSSEC (DNS Security Extensions), ensuring that DNS data remains authentic and unaltered during transmission. ShieldNet is built with security in mind from the ground up, making it a reliable choice for securing your network traffic.

## Command-Line Options

Here are the available command-line options for configuring ShieldNet:
```
Usage: shieldnet [options]

Options:
    -h, --help            Display this help message
    -a, --authority       Disable recursive lookups and serve only local zones
    -f, --forward SERVER  Forward DNS queries to the specified DNS server
    -p, --port PORT       Listen on the specified port (default: 5380)
```


## API Endpoints

By default, the API runs on **port 5380** and provides an intuitive interface for managing DNS data. It supports both **JSON** and **HTML** formats, allowing you to choose the best format for your use case.

### Available Endpoints:

- **/cache**: Displays the current cache entries along with statistics. This endpoint provides detailed insights into cache performance, including the number of hits, misses, and expired entries.
- **/authority**: Lists the current authoritative zones managed by the server. This endpoint gives an overview of all domains that the server is authoritative for.
- **/authority/[zone]**: Lists all the DNS records (A, MX, CNAME, etc.) within a specific zone. This provides a full breakdown of the records associated with a domain.

The API supports both **GET** and **POST** methods for data retrieval and modification. POST requests can be made with either **form data** or **JSON objects**, making it versatile for different use cases.

## Contributing

We welcome **comments**, **contributions**, and **pull requests** to help improve ShieldNet. If you have suggestions for new features, optimizations, or bug fixes, feel free to submit them. Together, we can make ShieldNet the best custom DNS solution available.

---

**Author:** [Samwuel Simiyu](mailto:simiyu.tech)
