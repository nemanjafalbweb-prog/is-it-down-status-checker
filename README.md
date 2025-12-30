# is-it-down-status-checker
# Is It Down – Website Status & Outage Checks

Website: https://isyourwebsitedownrightnow.com/

This repository provides simple, practical examples for checking whether a website is actually down or if the issue is caused by local access problems such as DNS, ISP blocking, firewall rules, or routing issues.

## What this repository covers

- Checking website availability using HTTP status codes
- Measuring response time and timeouts
- Differentiating real outages from access or network issues
- Basic DNS resolution checks
- Best practices for troubleshooting website reachability

## Example: Simple HTTP status check (PHP)

```php
$ch = curl_init("https://example.com");
curl_setopt($ch, CURLOPT_NOBODY, true);
curl_setopt($ch, CURLOPT_TIMEOUT, 5);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

curl_exec($ch);
$status = curl_getinfo($ch, CURLINFO_HTTP_CODE);
curl_close($ch);

echo "HTTP Status: " . $status;
