#STAGE-1

A. Flow

step 1: User login
step 2: the credentials are checked and fetched from the db
step 3: if the credentials are correct then it is notified as a notification
step 4: if the credentials ar wrong then rediect to the login page with time limits for trial (3 - 4 times) & if exceeds then make the login block for 12 seconds and try again
step 5: Display the notification
step 6: mark as read / Delete
step 7: updated
step 8: end

B. Get Notification

endpoint: 
          GET /notifications

header:
         http,
         Authorisation, 
         Auth/Token Type: Bearer Token,
         Access Token (lengthy)

request (JSON)

{
    "notification": [
        "ID": 1,
         "message": "login successfull"
    ]
}

response (JSON)

{
    "loginID": "",
    "message": "login successfull"
}

#STAGE-2

I would suggest mongodb atlas so that the system is deployed and users can manage the relational and complex datas in efficient manner and Persistent also. It has free tier also, even used by small and big scale organisation.It main focus on NOSQL we can store the datas either in json format or api links.

But for queries if we go for sql DB like MYSQL Workbench, we have create a separate table mannually for users, notifications, and so on. so i suggest NOSQL(Atlas)

DB Schema

Table name: USER_Table

Column  | Type
 id     | INT
Name    | VARCHAR(50)
E-mail  | VARCHAR(100)

Table name: Notifications_Table

Column  | Type
 id     | INT
User id | INT
Name    | VARCHAR(50)
E-mail  | VARCHAR(100)
is_read | BOOLEAN
time    | TIMESTAMP


If the data volume is increased then the data traffic and slow processing of datas are occured to avoid it we have to use indexing methods to optimise the query processing, and using separate tables for each users (user, notification, uploads,... so on)

I would suggest NOSQL as they are relational db and efficient for online use also.