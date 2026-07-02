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