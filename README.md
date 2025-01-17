# HackSys Advanced XSS Exploitation Tool

Welcome to the **HackSys Advanced XSS Exploitation Tool**! This tool is designed for advanced penetration testing, specifically for identifying and exploiting **Cross-Site Scripting (XSS)** vulnerabilities. With features such as asynchronous scanning, payload fuzzing, and customizable reporting, it's a powerful asset for security professionals.

## Features

- **Asynchronous Scanning**: Efficiently scan multiple URLs for XSS vulnerabilities.
- **Payload Fuzzing**: Use custom payloads to test for vulnerabilities.
- **Multi-threaded**: Perform concurrent scans to speed up the process.
- **Chrome WebDriver Integration**: Accurately fetch and analyze page content using Selenium and ChromeDriver.
- **Customizable Reporting**: Generate reports in **HTML**, **CSV**, and **PDF** formats.
- **Configurable**: Adjust settings with a configuration file and command-line arguments to tailor the tool to your needs.

## Installation

Follow the instructions below to install and configure the HackSys Advanced XSS Exploitation Tool on your machine:

### 1. Clone the Repository

Clone the repository to your local machine:

```bash
git clone https://github.com/your-repo/hacksys_xss.git
cd hacksys_xss
```

### 2. Set Up a Virtual Environment (Recommended)

Create and activate a Python virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Required Packages

Install the dependencies using `pip`:

```bash
pip install -r requirements.txt
```

Or, alternatively, manually install the required packages (run inside the virtual environment):

```bash
pip install aiohappyeyeballs==2.4.4
pip install aiohttp==3.11.11
pip install aiosignal==1.3.2
pip install attrs==24.3.0
pip install beautifulsoup4==4.12.2
pip install certifi==2024.12.14
pip install charset-normalizer==3.4.1
pip install chromedriver-autoinstaller==0.4.0
pip install fpdf==1.7.2
pip install frozenlist==1.5.0
pip install h11==0.14.0
pip install idna==3.10
pip install multidict==6.1.0
pip install outcome==1.3.0.post0
pip install propcache==0.2.1
pip install PySocks==1.7.1
pip install requests==2.28.2
pip install selenium==4.10.0
pip install sniffio==1.3.1
pip install sortedcontainers==2.4.0
pip install soupsieve==2.6
pip install termcolor==2.3.0
pip install trio==0.28.0
pip install trio-websocket==0.11.1
pip install urllib3==1.26.20
pip install wsproto==1.2.0
pip install yarl==1.18.3
```

### 4. Run the Tool

You are now ready to run the tool.

## Usage

Run the tool using the following command format:

```bash
python hacksys_xss.py -u <URL> -p <payloads_file> -o <output_file> --report <report_format> [options]
```

### Example Command

```bash
python hacksys_xss.py -u https://www.nepal.gov.np -p pollgots-xss.txt -o xssbug.txt -t 10 -v 3
```

This will scan `https://www.nepal.gov.np` using the payloads from `pollgots-xss.txt`, save the results to `xssbug.txt`, run with 10 threads, and set the verbosity level to 3.

## Command-Line Arguments

| Argument         | Description                                                                 | Default Value          |
|------------------|-----------------------------------------------------------------------------|------------------------|
| `-u, --url`      | Single URL to scan.                                                           |                        |
| `-l, --list`     | File containing a list of URLs to scan.                                       |                        |
| `-p, --payloads` | File containing a list of payloads to use for testing.                        |                        |
| `-o, --output`   | File to save results to.                                                     |                        |
| `-a, --user-agent`| User-Agent to use for requests.                                              | Mozilla/5.0            |
| `--headers`      | Additional headers to use for requests in key-value format, comma-separated. |                        |
| `--rate-limit`   | Rate limit for requests per second.                                          | 5                      |
| `-t, --threads`  | Number of concurrent threads for scanning.                                   | 5                      |
| `-v, --verbose`  | Verbosity level (0-5). Higher values provide more detailed output.           | 1                      |
| `--config`       | Configuration file in JSON format.                                           |                        |
| `--filter`       | Keyword filter for URLs (e.g., "admin", "login").                            |                        |
| `--report`       | Generate a report in a specified format (`html`, `csv`, `pdf`).               |                        |
| `-up, --update`  | Update the tool to the latest version.                                       |                        |

### Example Usage

#### Scan a Single URL

```bash
python hacksys_xss.py -u https://example.com -p payloads.txt -o output.txt
```

This will scan `https://example.com` for XSS vulnerabilities using the payloads from `payloads.txt`, and save the results to `output.txt`.

#### Scan a List of URLs

```bash
python hacksys_xss.py -l urls.txt -p payloads.txt -o output.txt
```

This will scan all URLs listed in `urls.txt` using the payloads from `payloads.txt`.

#### Generate an HTML Report

```bash
python hacksys_xss.py -u https://example.com -p payloads.txt -o output.txt --report html
```

This will scan `https://example.com` and generate an HTML report.

#### Increase Verbosity Level

```bash
python hacksys_xss.py -u https://example.com -p payloads.txt -o output.txt -v 3
```

This will run the scan with verbosity level 3 for more detailed output.

---
