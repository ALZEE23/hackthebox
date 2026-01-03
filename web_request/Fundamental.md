# Web Request

## HyperText Transfer Protocol (HTTP)

![alt text](/images/flow.png)

HTTP communication consists of a client and a server, where the client requests the server for a resource. The server processes the requests and returns the requested resource. The default port for HTTP communication is port 80, though this can be changed to any other port, depending on the web server configuration. The same requests are utilized when we use the internet to visit different websites. We enter a Fully Qualified Domain Name (FQDN) as a Uniform Resource Locator (URL) to reach the desired website, like www.hackthebox.com.

![alt text](/images/url.png)

## URL Components

| Component    | Example              | Description                                                                                                                                                                      |
| ------------ | -------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Scheme       | `http://` `https://` | This is used to identify the protocol being accessed by the client, and ends with a colon and a double slash (`://`)                                                             |
| User Info    | `admin:password@`    | This is an optional component that contains the credentials (separated by a colon `:`) used to authenticate to the host, and is separated from the host with an at sign (`@`)    |
| Host         | `inlanefreight.com`  | The host signifies the resource location. This can be a hostname or an IP address                                                                                                |
| Port         | `:80`                | The Port is separated from the Host by a colon (`:`). If no port is specified, http schemes default to port 80 and https default to port 443                                     |
| Path         | `/dashboard.php`     | This points to the resource being accessed, which can be a file or a folder. If there is no path specified, the server returns the default index (e.g. index.html)               |
| Query String | `?login=true`        | The query string starts with a question mark (`?`), and consists of a parameter (e.g. login) and a value (e.g. true). Multiple parameters can be separated by an ampersand (`&`) |
| Fragments    | `#status`            | Fragments are processed by the browsers on the client-side to locate sections within the primary resource (e.g. a header or section on the page)                                 |

> **Note:** Understanding URL components is essential for web security and request handling. Each component plays a crucial role in how browsers and servers communicate.
