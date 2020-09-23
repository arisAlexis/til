If you want to have a table with auto-incremented serial id and a user that is granted access to the table then this is also needed  
`GRANT USAGE, SELECT ON ALL SEQUENCES IN SCHEMA public TO dev;`
