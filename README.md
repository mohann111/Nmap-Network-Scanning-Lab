# Nmap Network Scanning Project

This project demonstrates network scanning with Nmap on a local subnet, explains different types of Nmap scans, and showcases saving results as both text and HTML reports.

## Objective

Learn to discover open ports and running services on devices in your local network, analyze network exposure, and document the findings professionally for cybersecurity assessments.

## Project Structure

```
.
├── README.md
├── scan_results.txt       # Nmap text output
├── scan.xml               # Nmap XML output (used for HTML conversion)
├── scan.html              # Converted HTML report
├── screenshots/           # Terminal and result screenshots
```

## Types of Nmap Scans

| Scan Option | Scan Name           | Description                                                                       |
|-------------|---------------------|-----------------------------------------------------------------------------------|
| `-sS`       | SYN Scan (Stealth)  | Sends SYN packets, does not complete TCP handshake. Fast and stealthy; avoids basic logging. |
| `-sT`       | TCP Connect Scan    | Attempts a full TCP handshake for every port. Easier to detect; reliable when root access is unavailable. |
| `-sU`       | UDP Scan            | Probes UDP ports, detects UDP services. Slower; prone to false negatives due to UDP behavior. |
| `-sV`       | Service Version     | Identifies versions of services running on open ports.                             |
| `-O`        | OS Detection        | Identifies the operating system by analyzing network responses.                    |

Nmap scans can be tuned and combined for comprehensive network asset enumeration.

## How To Scan and Save Results

### Example: TCP SYN Scan

```sh
nmap -sS 192.168.100.0/24
```
Scans all devices on subnet 192.168.100.0/24 using a stealth SYN scan.

### Save Results as Text File

```sh
nmap -sS 192.168.100.0/24 -oN scan_results.txt
```
The `-oN` option stores readable output in `scan_results.txt` for easy review.

### Save Results as XML and Convert to HTML

```sh
nmap -sS 192.168.100.0/24 -oX scan.xml
xsltproc scan.xml -o scan.html
```
This saves the scan as `scan.xml`, then converts it to a formatted HTML file `scan.html` for browser viewing and report sharing.

## Screenshots Included

- Nmap command execution
- File explorer with saved scan results
- Viewing reports in text and HTML format

## Key Takeaways

- Nmap offers versatile options for port, service, and OS discovery in a network.
- Saving results in multiple formats helps with analysis, documentation, and presentation.
- Understanding scan types helps select the best method for stealth, coverage, and reliability.

## References

- [Nmap Port Scanning Techniques][9]
- [Nmap Scan Command Examples][6]
- [Official Nmap Documentation](https://nmap.org/book/man-port-scanning-techniques.html)[9]

***

