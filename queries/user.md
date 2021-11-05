# User Cypher Queries

To search for accounts containing `test` in the `Display Name` property:

```txt
MATCH (u:User) WHERE toLower(u.displayname) CONTAINS "test" RETURN u
```

To search for **enabled** accounts that do not require authentication:

```txt
MATCH (u:User) WHERE u.passwordnotreqd = true AND u.enabled = true RETURN u
```
