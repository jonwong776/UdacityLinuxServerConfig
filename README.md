# Linux Server Configuration Project

The Udacity Linux Server Configuration Project for the Full Stack Web Developer Nanodegree. This project involved configuring an Amazon Lightsail Ubuntu server from scratch, hardening the security through best practices taught on the Udacity site, and then configuration an Apache web server that serves the Udacity Item Catalog project website. The website utilizes a PostgreSQL DB and acts as a catalog system where a user can browse various item categories and items and if logged in via Google, can also edit, add, and delete items. 

## Summary of Configuration Changes

OS Security Related:
1. Updated all installed packages
2. Changed SSH port on both Ubuntu settings and the AWS Lightsail network settings to 2200
3. Created new user, "grader"
4. Generated SSH key pair for "grader" user and installed key on server
5. Restricted .ssh directory (700 permissions) and authorized_keys file (644 permissions)
6. Provided "grader" user sudo access
7. Forced key-pair authentication by turning off password authentication.
8. Configured UFW to deny all incoming connections except SSH, HTTP, and NTP
9. Remote login for root was disabled
10. Configured local timezone to UTC

PostgreSQL Security Related:
1. Created DB user "catalog"
2. Restricted "catalog" user permissions to only in accordance with rule of least priviledge
- Only "Create" at DB level
- Only "Select", "Update", "Insert", "Delete" functions at table level
3. Restricted access to not allow remote connections

Apache Related:
1. Created new WSGI file and Apache configuration file. 

## List of Software Installed

1. PostgreSQL
2. Python 3
3. Apache2
4. Python 3 mod-wsgi Package
5. Git
6. Python pip

## Acknowledgements

- Credit to Digital Ocean for Flask-WSGI guidance and my Udacity mentor for the suggestion. 

## Connecting to Server

1. Using your preferred SSH client, connect using the following information:
  - IP Address: 34.237.144.169
  - Port: 2200
  - Username: grader
  - Password SSH Key: See "Notes to Reviewer" for key
  
## Visiting Web Application

1. To visit the web application, visit http://34.237.144.169.xip.io/
