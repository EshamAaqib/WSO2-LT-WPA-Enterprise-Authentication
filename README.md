# WSO2-WPA-Enterprise-Authentication-Assignment
## LT-2021-047

## Config Files are uploaded to a Github Private Repo and can be accessed via - https://gitfront.io/r/eshamaaqib/1a9f22a1f90e648fd547b8a9012fbbb6e431f04c/WSO2-WPA-Enterprise-Authentication-Assignment/

### Config Files are upload to the FreeRadius Config folder

## Proposed Solution :

### Using Google Authenticator and Password based authentication with FreeRadius (Password+2FACode)

## Plan :

### The plan here is to first configure freeradius with basic password authentication. Only users with role Radius will be able to access the network. All the user information will be stored in the WSO2 Identity Server and FreeRadius will access them using the LDAP module. After verifiying the basic password based authentication works I will go forward and implement MFA. As FreeRadius supports PAM (Pluggable Authentication Module) I will integrate the Google Authenticator PAM module with FreeRadius. This module allows FreeRadius to talk with Google Authenticator. I will be referring the guide written by Lakindu Jayasena (Lecturer who conducted this lecture; https://sysopstechnix.com/enable-2fa-on-freeradius-with-openldap-users/)  

## Network Diagram

![Network Diagram](https://user-images.githubusercontent.com/75664650/129246268-9b817bdf-fa92-4925-97f4-6bab83bac4ba.png)


## Challegnges and how I overcame them :

### At the begining the configurations were bit confusing and I was getting ton of errors. But after few tries and thorughly going through the configurations it gave me a good idea on how everything works and was able to configure eveything accordingly with no issues. 

## Learning outcome of this lecture:

### I learned how WPA Enterprise Authentication works, the funtionality of FreeRadius and how to configure them with 802.1x authentcation. By completing the assingnment it gave me  the idea on how to configure Google Authenticator with FreeRadius with MFA. 

## Screenshots :

### Assigning user eshamaaqib to role Radius (Only users assinged to the role radius has access to the network)

![Screenshot from 2021-08-12 12-39-36](https://user-images.githubusercontent.com/75664650/129246997-dce0dbc0-c82c-458a-9e33-f8cc114f0184.png)

### Adding an email address (eshamaaqib@lt-2021-047.ml) to user profile eshamaaqib. So I can use that as a username on FreeRadius

![Screenshot from 2021-08-12 12-39-43](https://user-images.githubusercontent.com/75664650/129247115-45116092-dbb4-4a7e-ae39-3125f249213d.png)

### Installing FreeRadius on the server

![Screenshot from 2021-08-12 12-46-43](https://user-images.githubusercontent.com/75664650/129247221-30b7f64b-d0e7-414c-9dde-f9c3c60b5120.png)

### Installing FreeRadius on the Client

![Screenshot from 2021-08-12 13-24-09](https://user-images.githubusercontent.com/75664650/129247302-92928504-cf99-41b5-a1d5-b3fb053e8668.png)

### Installing Google Authenticator PAM Module

![image](https://user-images.githubusercontent.com/75664650/129248585-8543c405-b7da-4d0a-a0b9-89427d73419d.png)

### Verifying whether basic password authentication works on FreeRadius (eshamaaqib belongs to the radius group and admin does not)

![Screenshot from 2021-08-12 13-03-22](https://user-images.githubusercontent.com/75664650/129247619-7371915b-9576-46e4-bf55-5ac2fbd7d335.png)

### Generating the QR code for Google Authenticator (user = eshamaaqib)

![Screenshot from 2021-08-12 13-09-20](https://user-images.githubusercontent.com/75664650/129247719-a05f6c43-33bd-4bd0-b1f5-2a0bbb135a1a.png)

### Verifiyng whether basic authentication+ MFA authentication works after configuring eveything

![Screenshot from 2021-08-12 13-14-42](https://user-images.githubusercontent.com/75664650/129247916-d9b449a1-ae28-4055-a392-ccfcbfe49008.png)

### In this screenshot there are 3 results. The first one I have entered a wrong 2FA code which then the access has been rejected. The second one I have entered the coorect one and access has been granted. The third one access has been rejected as admin does not belong the the group radius.

![Screenshot from 2021-08-12 13-25-36](https://user-images.githubusercontent.com/75664650/129248002-a2590bf1-93ad-451b-aa39-631c8f0aa9e4.png)
