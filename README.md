# WSO2-WPA-Enterprise-Authentication-Assignment




## Proposed Solution :

### Using Google Authenticator and Password based authentication with FreeRadius (Password+2FACode)

## Plan :

### The plan here is to first configure freeradius with basic password authentication. Only users with role Radius will be able to access the network. All the user information will be stored in the WSO2 Identity Server and FreeRadius will access them using the LDAP module. After verifiying the basic password based authentication works I will go forward the implement MFA. As FreeRadius supports PAM (Pluggable Authentication Module) I will integrate the Google Authenticator PAM module with FreeRadius. This module allows FreeRadius to talk with Google Authenticator. I will be referring the guide written by Lakindu Jayasena (Lecturer who conducted this lecture; https://sysopstechnix.com/enable-2fa-on-freeradius-with-openldap-users/)  

## Network Diagram

![Network Diagram (1)](https://user-images.githubusercontent.com/75664650/129245960-6a1edbe6-294d-4a75-89e2-288f7380e4a9.png)



## Challegnges and how I overcame them :

### At the begining the configurations were bit confusing and I was getting ton of errors. But after few tries and thorughly going through the configurations it gave me a good idea on how everything works and was able to configure eveything accordingly with no issues. 

## Learning outcome of this lecture:

### I learned how WPA Enterprise Authentication works, the funtionality of FreeRadius and how to configure them with 802.1x authentcation. By completing the assingnment it gave me  the idea on how to configure Google Authenticator with FreeRadius with MFA. 

