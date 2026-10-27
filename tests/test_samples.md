# Test Results
Python version used: 3.14  |   Operating system: Windows 11  |   Date: 2026-10-27
| # | Input | Expected result | Actual result | Pass/Fail |
|---|-------|-----------------|---------------|-----------|
| 1 | https://www.example.com/login | No listed warning signs | No listed warning signs found. This does NOT prove safety. | PASS |
| 2 | http://192.0.2.10/account | IP address + HTTP | Uses an IP address instead of a familiar domain. Uses HTTP. HTTPS alone does not prove trust. | PASS |
| 3 | http://example.com@sample.invalid/login | @ symbol + HTTP | Contains an @ symbol; inspect carefully. Uses HTTP. HTTPS alone does not prove trust. | PASS |
| 4 | https://a.b.c.d.e.example.invalid/path | Many hostname segments | Contains many hostname segments/subdomains. | PASS |
| 5 | https://xn--example.invalid/ | Punycode-style hostname | Contains a punycode-style hostname. | PASS |

Notes:
I learned that these six checks are clues, not proof. A link with zero clues can still be dangerous, and a link with clues can be harmless. I was also reminded that typing a hostname without a scheme (for example www.example.com) is treated as HTTP, which is why the HTTP warning appears even for a familiar-looking name. The most important takeaway is to keep stating clearly that "no warning signs found" does not mean "safe".
