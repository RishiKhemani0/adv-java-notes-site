---
{"dg-publish":true,"permalink":"/data-access-objects-dao/","dg-note-properties":{}}
---

## Definition
- The DAO is a special class created for each table
- This class is used to interact with that table
- All SQL queries are only written inside that Class
- It returns Java objects, not `ResultSet` but objects of [[Model Classes\|Model Classes]]
- It usually follows standard names like `save()`, `findAll()`, `update()`, `delete()`

| Without DAO         | With DAO              |
| ------------------- | --------------------- |
| main() calls        | less main() calls     |
| `PreparedStatement` | dao.save(tx)          |
| `ResultSet`         | dao.findAll(user)     |
| SQL Strings         | `dao.delete`(user)    |
| con.close()         | SQL Hidden inside DAO |

## Problems with Normal Approach
- SQL Strings duplicated in 5 Places
- Change column name, fix everywhere
- main() is 300 lines of mixed logic + SQL
- No way to refuse "fetch user by id" elsewhere
## What We actually need
- SQL Lives in one place per table
- main() calls clean methods, not SQL
- Change SQL in one class, everything works


