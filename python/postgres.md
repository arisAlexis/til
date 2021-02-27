Example for including a tuple in a where clause
```
base_tokens=('aa','bb')
sql = "SELECT * FROM pairs WHERE symbol0 NOT IN %s"
dict_cur.execute(sql,(base_tokens,))
```

Example for using a dict cursor

```
import psycopg2.extras
dict_cur = conn.cursor(cursor_factory=psycopg2.extras.DictCursor)
dict_cur.execute(sql,(base_tokens,))
pairs = dict_cur.fetchall()
all_pairs = list(map(lambda r:r['id'],pairs))
```
