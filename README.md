# 1. Update (correct first step)

Before running your script, do:

```
sudo apt update
```

#  Step 2: Check Python Installation

Kali usually has Python pre-installed:

```
python3--version
```

If not installed:

```
sudo apt install python3-y
```

---

#  Step 3: Create Project Folder

```
mkdir page_finder
cd page_finder
```
##  Step 4: Create Python file

```
nano page_finder.py
```
##  Step 5: Paste this script

```
importrequests

# Common pages list
paths= [
"admin",
"admin/login",
"login",
"dashboard",
"user",
"admin.php",
"login.php",
"cpanel",
"admin/dashboard"
]

# Take input from user
url=input("Enter website URL (e.g. https://example.com): ").strip()

# Remove trailing slash
ifurl.endswith("/"):
url=url[:-1]

print("\n[+] Scanning for pages...\n")

forpathinpaths:
full_url=f"{url}/{path}"
try:
response=requests.get(full_url,timeout=5)

ifresponse.status_code==200:
print(f"[FOUND]{full_url}")
else:
print(f"[NOT FOUND]{full_url}")

exceptrequests.exceptions.RequestException:
print(f"[ERROR]{full_url}")
```
##  Step 6: Save and exit

- Press `CTRL + X`
- Press `Y`
- Press `Enter`
 
##  Step 7: Run the tool

```
python3 page_finder.py
```
##  Example Output

```
Enter website URL: https://test.com

[+] Scanning for pages...

[FOUND] https://test.com/admin
[NOT FOUND] https://test.com/login
```
