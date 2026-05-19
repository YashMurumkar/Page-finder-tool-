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
