# nikto
`Nikto` is a web server scanner included in Kali Linux that performs comprehensive tests against web servers for multiple items, including:

- Server configuration issues
- Vulnerabilities
- Default files and scripts

### Usage

The basic syntax for using Nikto is:

```bash
nikto -h <target>
```

### Options

- `-h <target>`: Specify the target host (IP address or domain).
- `-p <port>`: Specify the port (default is 80).
- `-o <output_file>`: Save the results to a specified file.
- `-Format <format>`: Specify the output format (e.g., `html`, `txt`).
- `-Tuning <tune>`: Specify the type of tests to perform (e.g., `0` for all, `1` for interesting files).

### Examples

1. **Basic Scan**

   To perform a basic scan on a target:

   ```bash
   nikto -h http://example.com
   ```

   **Output:**
   ```
   - Nikto v2.1.6
   ---------------------------------------------------------------------------
   + Target IP:          93.184.216.34
   + Target Hostname:    example.com
   + Target Port:        80
   + Start Time:         2023-02-26 12:00:00
   ---------------------------------------------------------------------------
   + Server: nginx/1.19.10
   + The anti-clickjacking header 'X-Frame-Options' is not present.
   + /admin/: This might be interesting...
   + /backup/: This might be interesting...
   + ... (other findings)
   ---------------------------------------------------------------------------
   ```

2. **Scan with Specific Port**

   To scan a web server running on a non-standard port:

   ```bash
   nikto -h http://example.com -p 8080
   ```

   **Output:**
   ```
   - Nikto v2.1.6
   ...
   + Start Time:         2023-02-26 12:05:00
   ...
   ```

3. **Output to a File**

   To save the scan results to a text file:

   ```bash
   nikto -h http://example.com -o results.txt
   ```

   **Output:**
   ```
   Results saved to results.txt
   ```

4. **Specify Output Format**

   To save the scan results in HTML format:

   ```bash
   nikto -h http://example.com -o results.html -Format htm
   ```

   **Output:**
   ```
   Results saved to results.html
   ```

5. **Tuning Tests**

   To perform scans focusing on interesting files:

   ```bash
   nikto -h http://example.com -Tuning 1
   ```

   **Output:**
   ```
   + /admin/: This might be interesting...
   + /config.php: This might be interesting...
   ```

### Notes

- Ensure you have permission to scan the target server to avoid legal issues.
- The output may vary based on the server's configuration and vulnerabilities detected.
- Nikto is a powerful tool for assessing web server security, but use it responsibly and ethically.




                               ALTERNATIVE
**Nikto** is a web server scanner included in Kali Linux that performs comprehensive tests against web servers for multiple vulnerabilities. It can identify outdated server software, dangerous files, and misconfigurations.

### Usage

The basic syntax for using Nikto is:

```bash
nikto -h <target>
```

### Common Options

- `-h <target>`: Target hostname or IP address.
- `-p <port>`: Specify port (default is 80).
- `-o <output_file>`: Save the scan results to a file.
- `-Format <type>`: Specify the output format (e.g., `html`, `txt`, `csv`).
- `-Tuning <tuning_option>`: Specify the tuning options to narrow down the scan.

### Examples

1. **Basic Scan**

   To perform a basic scan on a target:

   ```bash
   nikto -h http://example.com
   ```

   **Output:**
   ```
   - Nikto v2.1.6
   + Target IP:   192.168.1.1
   + Target Hostname: example.com
   + Starting Nikto v2.1.6
   + Server: Apache/2.4.41
   + The anti-clickjacking X-Frame-Options header is not present.
   + OSVDB-3092: /admin/: This might be interesting...
   ```

2. **Scan a Specific Port**

   To scan a web server running on a port other than the default:

   ```bash
   nikto -h http://example.com -p 8080
   ```

   **Output:**
   ```
   + Server: Apache/2.4.41
   + 301 Found: /new-path/ redirecting to /new-path/
   ```

3. **Output to a File**

   To save the results of the scan to a file:

   ```bash
   nikto -h http://example.com -o scan_results.txt
   ```

   **Output:**
   ```
   Results saved to scan_results.txt
   ```

4. **Tuning the Scan**

   To specify tuning options to focus on certain tests:

   ```bash
   nikto -h http://example.com -Tuning 9
   ```

   **Output:**
   ```
   + Testing for vulnerabilities...
   + OSVDB-123456: /example/path: found...
   ```

### Notes

- Ensure you have permission to scan the target web server to avoid legal issues.
- Nikto can generate a lot of output, so consider using output options to manage results effectively.
- The effectiveness of Nikto can depend on the web server's configuration and the specific vulnerabilities present.




                             ALTERNATIVE
Nikto is a web server scanner that can identify vulnerabilities and weaknesses in web servers, including Apache, IIS, and others. Here's how to use it:

**Syntax:**
```
nikto -h <target_host> [-port <port_number>] [options]
```
**Options:**

* `-h`: Specify the target host.
* `-port`: Specify the port number (default is 80).
* `-ssl`: Use SSL/TLS for the scan.
* `-C`: Check for certificate issues.
* `-D`: Check for sensitive files and directories.
* `-E`: Check for executable files.
* `-F`: Check for files with strange permissions.
* `-G`: Check for graphical GET requests.
* `-H`: Check for HTTP methods.
* `-I`: Check for index files.
* `-M`: Check for multiple index files.
* `-N`: Check for non-standard ports.
* `-O`: Check for outdated software.
* `-P`: Check for PHP-specific issues.
* `-R`: Check for robots.txt files.
* `-S`: Check for sensitive information disclosure.
* `-T`: Check for TLS/SSL issues.

**Examples:**

1. **Basic Scan:**
```
nikto -h 192.168.1.100
```
This will perform a basic scan of the web server at `192.168.1.100`.

2. **Scan with SSL:**
```
nikto -h 192.168.1.100 -ssl
```
This will perform a scan of the web server at `192.168.1.100` using SSL/TLS.

3. **Scan with Specific Port:**
```
nikto -h 192.168.1.100 -port 8080
```
This will perform a scan of the web server at `192.168.1.100` on port `8080`.

**Output:**

The output will vary depending on the scan results, but it will typically include information about:

* OS and web server version
* Vulnerabilities and weaknesses
* Sensitive files and directories
* Outdated software
* Certificate issues

Here's an example output:
```
+ Server: Apache/2.4.7 (Ubuntu)
+ Server leaks inodes via ETag headers, header found: inode: 123456
+ Apache/2.4.7 appears to be outdated (current version is at least Apache/2.4.10)
+ 200 OK: GET /icons/README
+ 403 Forbidden: GET /cgi-bin/test.cgi
+ 404 Not Found: GET /robots.txt
```
Remember to use Nikto responsibly and only on systems you have permission to test or access.




                               ALTERNATIVE
Certainly, I'll provide information on using the Nikto tool in Kali Linux.

Nikto is a web server scanner that is designed to find vulnerabilities and potentially dangerous files/CGIs on web servers. It is a comprehensive tool that can be used for a wide range of web application security testing tasks.

Here's how to use Nikto, along with some examples and expected output:

Usage:
```
nikto -h <target_host> [options]
```

Options:
- `-h <target_host>`: The target host to scan (e.g., http://example.com)
- `-p <port>`: The port number to use (default is 80 for HTTP and 443 for HTTPS)
- `-o <output_file>`: Save the output to a file
- `-F <format>`: Output format (e.g., txt, html, csv)
- `-C <check_file>`: Check for specific vulnerabilities using a custom check file
- `-T <plugin>`: Run a specific Nikto plugin
- `-D <options>`: Display options for a specific plugin

Examples:

1. **Basic Web Server Scan**:
   ```
   nikto -h http://example.com
   ```
   This command will perform a basic scan of the web server at `http://example.com`.

   Output:
   ```
   - Nikto v2.1.6
   ---------------------------------------------------------------------------
   + Target IP:          example.com
   + Target Hostname:    example.com
   + Target Port:        80
   + Start Time:         2023-02-26 12:00:00 (GMT+0)
   ---------------------------------------------------------------------------
   + Server: Apache/2.4.46 (Unix)
   + The anti-clickjacking X-Frame-Options header is not present.
   + The X-XSS-Protection header is not defined. This header can hint to the user agent to protect against some forms of XSS
   + The X-Content-Type-Options header is not set. This could allow the user agent to render the content as a different mime-type, for example as text/plain instead of application/json
   + Apache/2.4.46 appears to be outdated (current is at least 2.4.51). Apache 2.2.34 is the latest version for the 2.x series.
   + Scan terminated:  No more targets to scan.
   ```

2. **Scan for Specific Vulnerabilities**:
   ```
   nikto -h https://example.com -C all
   ```
   This command will perform a scan of the web server at `https://example.com` and check for all available vulnerability checks.

   Output:
   ```
   - Nikto v2.1.6
   ---------------------------------------------------------------------------
   + Target IP:          example.com
   + Target Hostname:    example.com
   + Target Port:        443
   + Start Time:         2023-02-26 12:00:00 (GMT+0)
   ---------------------------------------------------------------------------
   + Server: Apache/2.4.46 (Unix)
   + The anti-clickjacking X-Frame-Options header is not present.
   + The X-XSS-Protection header is not defined. This header can hint to the user agent to protect against some forms of XSS
   + The X-Content-Type-Options header is not set. This could allow the user agent to render the content as a different mime-type, for example as text/plain instead of application/json
   + Apache/2.4.46 appears to be outdated (current is at least 2.4.51). Apache 2.2.34 is the latest version for the 2.x series.
   + Uncommon header 'link' found, with the following 1 link: <https://example.com/>; rel="canonical"
   + Server may leak inodes via ETags, header found with file /index.html, inode: 1234, size: 5678
   + Apache/2.4.46 appears to be outdated (current is at least 2.4.51). Apache 2.2.34 is the latest version for the 2.x series.
   + Scan terminated:  No more targets to scan.
   ```

3. **Save Output to a File**:
   ```
   nikto -h http://example.com -o nikto_report.txt
   ```
   This command will save the output of the Nikto scan to a file named `nikto_report.txt`.

Note that the actual output may vary depending on the target web server's configuration and the vulnerabilities found.

Remember to use Nikto responsibly and only on web servers that you have permission to test. Unauthorized access to systems is illegal.




                               ALTERNATIVE
Nikto is a popular open-source web server scanner used for penetration testing. It's designed to find various vulnerabilities and misconfigurations in web servers. Here’s how to use it, along with examples and expected outputs:

### Installation

Nikto is usually pre-installed in Kali Linux. If it's not, you can install it using:

```bash
sudo apt update
sudo apt install nikto
```

### Basic Usage

The basic syntax for using Nikto is:

```bash
nikto [options] -h <target host>
```

### Common Options

*   **`-h <target host>`**: Specifies the target host. This can be an IP address or a domain name.
*   **`-p <port>`**: Specifies the port to scan. If not specified, it defaults to port 80. Use `443` for HTTPS.
*   **`-ssl`**: Forces SSL mode.
*   **`-vhost <hostname>`**: Specifies the virtual host.
*   **`-output <filename>`**: Saves the output to a file.
*   **`-C all`**: Checks for all possible file variations on the target.
*   **`-update`**: Updates Nikto’s plugin and database files.
*   **`-T <option(s)>`**: Tuning options for the scan (e.g., `1` for interesting files, `x` for reverse tuning).
*   **`-Plugins <plugin(s)>`**: Specifies which plugins to use.
*   **`-evasion <option(s)>`**: Uses encoding techniques to evade IDS/IPS systems.

### Examples and Output

1.  **Basic Scan**

    To perform a basic scan on a target web server:

    ```bash
    nikto -h example.com
    ```

    **Output:**

    ```
    - Nikto v2.1.6
    ---------------------------------------------------------------------------
    + Target IP:          93.184.216.34
    + Target Hostname:    example.com
    + Target Port:        80
    + Start Time:         2025-02-26 06:15:00 (UTC)
    ---------------------------------------------------------------------------
    + Server: Apache
    + The anti-clickjacking X-Frame-Options header is not present.
    + The X-XSS-Protection header is not defined. This can allow cross-site scripting attacks.
    + The X-Content-Type-Options header is not set. This could allow the browser to render files as a different MIME type than what the server intends.
    + Uncommon header 'tcn' found, with contents: list
    + Allowed HTTP Methods: GET, HEAD, POST, OPTIONS, TRACE
    + OSVDB-877: HTTP TRACE method is active, suggesting the host is vulnerable to XST
    + /icons/: Directory indexing found.
    + /robots.txt: Robots.txt file found.
    + /robots.txt: See 1 entry.
    + OSVDB-3092: /README: README file found.
    + 7958 items checked: 0 item(s) reported on remote host
    + End Time:           2025-02-26 06:20:00 (UTC)
    ---------------------------------------------------------------------------
    + 1 host(s) tested
    ```

2.  **Scanning HTTPS**

    To scan a web server using HTTPS on port 443:

    ```bash
    nikto -h example.com -p 443 -ssl
    ```

    or

    ```bash
    nikto -h example.com -ssl
    ```

    **Output:**

    ```
    - Nikto v2.1.6
    ---------------------------------------------------------------------------
    + Target IP:          93.184.216.34
    + Target Hostname:    example.com
    + Target Port:        443
    + Start Time:         2025-02-26 06:21:00 (UTC)
    ---------------------------------------------------------------------------
    + Server: Apache
    + Uncommon header 'tcn' found, with contents: list
    + The anti-clickjacking X-Frame-Options header is not present.
    + The X-XSS-Protection header is not defined. This can allow cross-site scripting attacks.
    + The X-Content-Type-Options header is not set. This could allow the browser to render files as a different MIME type than what the server intends.
    + Allowed HTTP Methods: GET, HEAD, POST, OPTIONS, TRACE
    + OSVDB-877: HTTP TRACE method is active, suggesting the host is vulnerable to XST
    + /icons/: Directory indexing found.
    + /robots.txt: Robots.txt file found.
    + /robots.txt: See 1 entry.
    + OSVDB-3092: /README: README file found.
    + 7958 items checked: 0 item(s) reported on remote host
    + End Time:           2025-02-26 06:26:00 (UTC)
    ---------------------------------------------------------------------------
    + 1 host(s) tested
    ```

3.  **Scanning with a Specific Port**

    To scan a web server on a specific port (e.g., 8080):

    ```bash
    nikto -h example.com -p 8080
    ```

    **Output:**

    ```
    - Nikto v2.1.6
    ---------------------------------------------------------------------------
    + Target IP:          93.184.216.34
    + Target Hostname:    example.com
    + Target Port:        8080
    + Start Time:         2025-02-26 06:27:00 (UTC)
    ---------------------------------------------------------------------------
    + Server: Apache
    + Uncommon header 'tcn' found, with contents: list
    + The anti-clickjacking X-Frame-Options header is not present.
    + The X-XSS-Protection header is not defined. This can allow cross-site scripting attacks.
    + The X-Content-Type-Options header is not set. This could allow the browser to render files as a different MIME type than what the server intends.
    + Allowed HTTP Methods: GET, HEAD, POST, OPTIONS, TRACE
    + OSVDB-877: HTTP TRACE method is active, suggesting the host is vulnerable to XST
    + /icons/: Directory indexing found.
    + /robots.txt: Robots.txt file found.
    + /robots.txt: See 1 entry.
    + OSVDB-3092: /README: README file found.
    + 7958 items checked: 0 item(s) reported on remote host
    + End Time:           2025-02-26 06:32:00 (UTC)
    ---------------------------------------------------------------------------
    + 1 host(s) tested
    ```

4.  **Saving Output to a File**

    To save the scan results to a file:

    ```bash
    nikto -h example.com -output report.txt
    ```

    This will save the output to a file named `report.txt`.

5.  **Update Nikto Database**

    To update the Nikto database:

    ```bash
    nikto -update
    ```

    **Output:**

    ```
    - Nikto v2.1.6
    ---------------------------------------------------------------------------
    + Updating Nikto databases...
    - Current database version: 20160411
    - New database version: 20241220
    + Successfully updated databases.
    ---------------------------------------------------------------------------
    ```

6.  **Using Tuning Options**

    To use tuning options to focus the scan (e.g., check only for interesting files):

    ```bash
    nikto -h example.com -T 1
    ```

    **Output:**

    ```
    - Nikto v2.1.6
    ---------------------------------------------------------------------------
    + Target IP:          93.184.216.34
    + Target Hostname:    example.com
    + Target Port:        80
    + Start Time:         2025-02-26 06:35:00 (UTC)
    ---------------------------------------------------------------------------
    + Server: Apache
    + Uncommon header 'tcn' found, with contents: list
    + The anti-clickjacking X-Frame-Options header is not present.
    + The X-XSS-Protection header is not defined. This can allow cross-site scripting attacks.
    + The X-Content-Type-Options header is not set. This could allow the browser to render files as a different MIME type than what the server intends.
    + Allowed HTTP Methods: GET, HEAD, POST, OPTIONS, TRACE
    + OSVDB-877: HTTP TRACE method is active, suggesting the host is vulnerable to XST
    + /icons/: Directory indexing found.
    + /robots.txt: Robots.txt file found.
    + /robots.txt: See 1 entry.
    + OSVDB-3092: /README: README file found.
    + 7958 items checked: 0 item(s) reported on remote host
    + End Time:           2025-02-26 06:40:00 (UTC)
    ---------------------------------------------------------------------------
    + 1 host(s) tested
    ```

### Notes

*   Ensure you have permission to scan the target to avoid legal issues.
*   The output can vary based on the target system's configuration and security measures.
*   Use Nikto responsibly and ethically.
*   Regularly update Nikto to ensure you have the latest vulnerability definitions.



                             
  
