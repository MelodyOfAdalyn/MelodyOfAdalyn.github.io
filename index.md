# Android Event App

## Introduction
Welcome to the Android App! The primary purpose of the app is to allow the user to monitor, add, or remove apps. Originally, it was created and mainly functioned as a display then an interactive piece. Now, the user is able to login into the app through Firebase and navigate the app in order to add or remove events froma list. Along with view account information within the settings page. 

## Table of Contents
- Instructions
- Databases
- Software Engineering
- Algorithms and Data Structures

## Instructions
- In order to navigate this app, the user must first register with the application before being able to reach the navigation pages. 
- The register page will ask for:
  - Full Name
  - Email
  - Password
- Submit this information in order to create an account. "Sign up" successful will appear and then you may log in and out of the app. 

### Databases
  The main database used within this app is Firebase. In this case, Firebase is being utilized in order to store user credentials. This allows the user to enter and exit the application along with restore credentials. 
  
# Register
  - User must enter the sign up page first in order to get full functionality of the application. 
  - Enter all credentials in order to gain access to the apps features

<p align="center">
  <img width="460" height="700" src="register.png">
</p>


  ```markdown
@Override
            public void onClick(View view) {
                //Extract com.example.apppageadjustment.ui.data
                String fullName = registerName.getText().toString();
                String emailAddress = registerEmail.getText().toString();
                String password = registerPassword.getText().toString();
                String password2 = registerPassword2.getText().toString();
                //Warn the user if the text fields are empty to fill out the following information
                if (fullName.isEmpty()) {
                    registerName.setError("Must Enter a name");
                    return;
                }
                if (emailAddress.isEmpty()) {
                    registerEmail.setError("Must Enter a Email");
                    return;
                }
                if (password.isEmpty()) {
                    registerPassword.setError("Must Enter a Password");
                    return;
                }
                if (password2.isEmpty()) {
                    registerPassword2.setError("Must Enter a Password again");
                    return;
                }

                //Password dont match currently
                if (!password.equals(password2)) {
                    registerPassword2.setError("Passwords do not match, try again");
                } else {
                    //passed, place toast message here to say it passed
                }

                fAuth.createUserWithEmailAndPassword(emailAddress,password).addOnSuccessListener(new OnSuccessListener<AuthResult>() {
                    @Override
                    public void onSuccess(AuthResult authResult) {
                    //Successful user is at the next page
                        signup();
                    }

```   
- Link to Login Code: [Register](AndroidEnhancement.zip), 
- Register.class: AndroidEnhancement.zip\AndroidEnhance\app\src\main\java\com\example\apppageadjustment\Register
- activity_login.XML: AndroidEnhancement.zip\AndroidEnhance\app\src\main\res\layout\activity_register.xml  
  

# Login 
 -Logging into the app allows the user to access the features of this app. This is tied into Firebase so all information entered will be stored within the database for future usage. This allows the user to log in and out of this app with the credentials that they had entered into the system. 
 -Original Code from Login Features without Firebase
 

 -Enhanced code from Login Feature with Firebase
<p align="center">
  <img width="460" height="700" src="loginpage.png">
</p>
 
```markdown
//User clicks the login_button in attempt to login to the application
        login_Button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                //extract and validate com.example.apppageadjustment.ui.data
               if(username.getText().toString().isEmpty()) {
                   username.setError("Please enter Email");
                   return;
               }
               if(password.getText().toString().isEmpty()) {
                   username.setError("Please enter password");
                   return;
               }
                //com.example.apppageadjustment.ui.data is valid
                //login user

                firebaseAuth.signInWithEmailAndPassword(username.getText()
                        .toString(),password.getText()
                        .toString())
                        .addOnSuccessListener(new OnSuccessListener<AuthResult>() {
                    @Override
                    public void onSuccess(AuthResult authResult) {
                        startActivity(new Intent(getApplicationContext(),Bot_Nav.class));

                    }
                }).addOnFailureListener(new OnFailureListener() {
                    @Override
                    public void onFailure(@NonNull Exception e) {
                        Toast.makeText(Login.this, e.getMessage(), Toast.LENGTH_SHORT).show();
                    }
                });
            }

        });
```
- Link to Login Code: [Login](AndroidEnhancement.zip), 
- Login.class: AndroidEnhancement.zip\AndroidEnhance\app\src\main\java\com\example\apppageadjustment\Login
- activity_login.XML: AndroidEnhancement.zip\AndroidEnhance\app\src\main\res\layout\activity_login.xml  

# Forgot Password
  - User forgot credentials to get into the application. Click the forgot password button. If the user email is a valid address then an email notification will be sent to the user to enter a new password. 



<p align="center">
  <img width="460" height="700" src="forgotpassword.png">
</p>
 
  ```markdown
private void forgotPassword() {
        View view = inflater.inflate(R.layout.activity_forgot_password,null);
        resetAlert.setTitle("Forgot Password?")
                .setMessage("Enter your email and a password request will be sent")
                .setPositiveButton("Request", new DialogInterface.OnClickListener() {
                    @Override
                    public void onClick(DialogInterface dialogInterface, int which) {
                        //Validate email address
                        EditText email = view.findViewById(R.id.email);
                        if(email.getText().toString().isEmpty()){
                            email.setError("Required field");
                            return;
                        }

                        firebaseAuth.sendPasswordResetEmail(email.getText().toString()).addOnSuccessListener(new OnSuccessListener<Void>() {
                            @Override
                            public void onSuccess(Void unused) {
                                Toast.makeText(Login.this, "Request Sent",Toast.LENGTH_SHORT).show();

                            }
                        }).addOnFailureListener(new OnFailureListener() {
                            @Override
                            public void onFailure(@NonNull Exception e) {
                                Toast.makeText(Login.this, e.getMessage(),Toast.LENGTH_SHORT).show();
                            }
                        });
                        //Send reset link

                    }
                }).setNegativeButton("Cancel",null)
                .setView(view)
                .create()
                .show();
```  
- Link to Forgot Password Code: [Forgot Password](AndroidEnhancement.zip), 
- Login.class: AndroidEnhancement.zip\AndroidEnhance\app\src\main\java\com\example\apppageadjustment\Login
- activity_forgot_password.XML: AndroidEnhancement.zip\AndroidEnhance\app\src\main\res\layout\activity_forgot_password.xml  




### Software Engineering

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```



### Algorithms and Data Structures
```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```


### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.

