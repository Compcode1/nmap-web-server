Nmap Web Server Detection & Monitoring**

This project successfully demonstrated **network scanning, web server enumeration, and security analysis** using **Nmap** and a **Python-based HTTP server**. Through a structured series of steps, we explored how Nmap detects network services, tracks changes, and identifies potential security misconfigurations.

---

## **🔍 Key Findings & Takeaways**

### **✅ 1. Nmap for Network Scanning & Service Detection**
- **Baseline scan:** Before starting the web server, we used `nmap -sV` to establish which network services were already running.
- **Detecting an active web server:** After launching a Python HTTP server, we confirmed its presence on **port 8000** using Nmap.
- **Tracking changes:** When we later changed the port to **8080**, Nmap scans revealed how service detection is affected by port modifications.

### **✅ 2. Web Content Enumeration & Security Risks**
- **Used `http-enum` to identify exposed files and directories.**
- **Verified that files and directories were publicly accessible** if no access restrictions were in place.
- **Key finding:** The web server initially exposed unintended directories due to improper configuration. This was later corrected by explicitly setting a restricted directory (`~/WebServerTest`).

### **✅ 3. Modifying the Web Server & Observing Impact**
- **Port modification:** We changed the web server port from **8000 to 8080** and observed how it affected visibility in Nmap scans.
- **Root directory modification:** Initially, the server **unintentionally served the entire home directory**, exposing personal files.
- **Security fix:** We **explicitly set a dedicated directory (`~/WebServerTest`)** to prevent unintended exposure. Nmap scans confirmed that previously exposed directories were no longer visible.

### **✅ 4. Stopping the Web Server & Validating Removal**
- **Killed the running web server process.**
- **Confirmed with Nmap that port 8080 was now closed**, proving the server was no longer active.

---

## **🎯 Lessons Learned**
- **Nmap is a powerful tool** for detecting open ports, running services, and identifying potential misconfigurations.
- **Improperly configured web servers can expose unintended files**, making security scanning essential.
- **Restricting the web server’s root directory** is a simple but critical security measure.
- **Monitoring open ports over time** helps track potential unauthorized changes or exposures.

This project provided a hands-on experience in **real-world network security monitoring**, demonstrating how even a simple web server can introduce security risks if not properly configured.
