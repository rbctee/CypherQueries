# User Cypher Queries

Search for accounts containing `admin` in the `Display Name` property:

```txt
MATCH (u:User) WHERE toLower(u.displayname) CONTAINS "admin" RETURN u
```

Search for **enabled** accounts that do not require authentication:

```txt
MATCH (u:User) WHERE u.passwordnotreqd = true AND u.enabled = true RETURN u
```

Search for **owned** admin users:

```txt
MATCH (u:User) WHERE u.owned = true AND u.enabled = true AND u.admincount = true RETURN n
```

Search for passwords in descriptions:

```txt
# manual
MATCH (u:User) RETURN u.description

# automatic
MATCH (u:User) WHERE (toLower(u.description) CONTAINS 'pwd' OR toLower(u.description) CONTAINS 'psw' OR toLower(u.description) CONTAINS 'password' OR toLower(u.description) CONTAINS 'pass') AND u.enabled = True RETURN u
```
