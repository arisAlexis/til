using the pg-promise library (which itself uses the normal node-postgres library) you need to do this:

```javascript
db.query('update ${schema~}.chats set messages = array_prepend(${message}, messages) where chat_id = ${chatId}', {
        schema: 'your schema name',
        chatId: 'your chat id',
        message: {
            sender: 'set the sender here',
            tstamp: 'set the time you need',
            body: 'set the body as needed'
        }
    }
);
```
explanation:

the $schema~ protects the attacker from accessing another table name. all other strings are escaped.

note it is important **not to use the ES6 template string ``** because it conflicts with the templating system used here.
