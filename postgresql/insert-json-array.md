The following code should in theory work according to  the manual (although it doesn't explicitly say so)

Table definition: 
` chat_id serial primary key, last_update timestamp, messages JSON[] ` 

sql command:  
`insert into chats (messages) values ('{{"sender":"pablo","body":"they are on to us"}}');`

*does not work*

but this works:

`insert into chats 
  (messages) 
values 
  (array['{"sender":"pablo","body":"they are on to us"}']::json[]);`
