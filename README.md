# folkatech-backend

path /users are all protected using auth

to get token for auth, access /auth/login and use 
    username: firaaaa
    password : totoro 
returned token can be used inside bearer token and all path under /users can now be accessed

if for some reason it doesn't give back a token, then you can register from /auth/register and input your own username and password in body, then go back to /auth/login to get the token

/users to view all users in database 

/users/:identityNumber to view users by selected identityNumber 

/users/new to create a new user. validation includes : min & max length for each characters. accountNumber and identityNumber must be numbers only. email must be a valid email address. 

/users/edit/:identityNumber to edit user by selected identityNumber. returns the newly edited user 

/users/delete/:identityNumber to delete selected user. returns the remaining users

redis implemented with every changes (adding new user, editing a user, and deleting a user) triggers an update in cache to make sure cached version is always up to date with the database.


