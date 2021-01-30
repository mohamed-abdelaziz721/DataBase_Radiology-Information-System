# RIS
## Table of Contents

* [About the Project](#about-the-project)
* [Toolbox](#toolbox)
* [Setting Up the Environment](#setting-up-the-environment)
* [Working Demo of the System](#working-demo-of-the-system)
* [Extra Information Missed in The Video](#extra-information-missed-in-the-video)
* [Our Team](#our-team)
* [Acknowledgements](#acknowledgements)
* [About](#about)

## About The Project
This is a Radiology Information System MVP project implementing the core concepts of Database Engineering.
User Authentication was used to manage different users. Admin can add new doctors, Technicians, Receptionists to the system and view the work history of each employee. Receptionists can add new or existing patients and assigning their case to a specific doctor and technician with the ability to view previous patient visits and whose patient report was finished . Technician can upload Scans. Doctors then can write the report and the patient will be notified and can view the scan report in his profile.  

## Toolbox

* HTML
* CSS
* JavaScript
* JQuery
* Bootstrap
* Flask
    * Flask WTF
    * Flask SQLAlchemy
    * Flask Mail
    * Flask Bcrypt
    * Flask LoginManger

## Setting Up the Environment
1. Clone the repo
    - HTTPS
        ```sh
        git clone https://github.com/RamadanIbrahem98/HIS.git
        ```
    - SSH
        ```sh
        git clone git@github.com:RamadanIbrahem98/HIS.git
        ```
1. Create a Virtual Environment (Optional)
    ```sh
    python -m venv .RIS
    ```
1. Activate the virtual environment 
    - using CMD
        ```sh
        .\.RIS\Scripts\activate
        ```
    - using PowerShell
        ```sh
        .\.RIS\Scripts\Activate.ps1
        ```
    - using Bash
        ```sh
        source .RIS/bin/activate
        ```

1. Install the requirements and dependancies
    ```sh
    pip install -r requirements.txt
    ```
1. Set Up the Environment Variables in the **HIS/\_\_init\_\_.py** file with your own.
    * SECRET_KEY: Is a random secret key used to log sessions.
    * SQLALCHEMY_DATABASE_URI: Is the URI of your database
    * MAIL_USERNAME: Your gmail account.
    * MAIL_PASSWORD: This is an app password assigend from google. you can get one from [Here!](https://security.google.com/settings/security/apppasswords)

1. Add an Admin to the System. write in teh python shell in the **app.py** folder
    ```sh
        from RIS import bcrypt, db
        from RIS.models import User
        hashed_password = bcrypt.generate_password_hash('your password here').decode('utf-8')
        user = User(username='Admin user name', email='anything@A.com', password=hashed_password)
        db.session.add(user)
        db.session.commit()
    ```

1. Run the application
    ```sh
    python app.py
    ```
1. View the application on localhost
    ```
    http://localhost:5000/
    ```
## Working Demo of the System

You can find a video demo here

```
https://youtu.be/JKOfDyNr8GI
```

## Extra Information Missed in The Video

* The Credentials.txt file contains useres with their credentials
* Receptionist can access the history of all of the patients in the system

## Our Team

* Ramadan Ibrahem - [![linkedin-shield]](https://www.linkedin.com/in/ramadanibrahem/)
* Muhammad Seyam - [![linkedin-shield]](https://www.linkedin.com/in/mohamed-seyam-91b3b81b7/)
* Mohamad Ahmed Abdelaziz  - [![linkedin-shield]](https://www.linkedin.com/in/mohamed-ahmed-abdelaziz)
* Moamen Gamal - [![linkedin-shield]](https://www.linkedin.com/in/moamen-gamal-5aa12117a/)
* Haithem Emad - [![linkedin-shield]](https://www.linkedin.com/in/haitham-emad-5145b3177/)
* Qurban Ali - [![linkedin-shield]](https://linkedin.com/#)

## Acknowledgements

*We want to thank*
* [StackOverflow Community](https://stackoverflow.com)
* [Front-End Template Creators](https://www.free-css.com/free-css-templates/page257/evolo)
* [Cory M. Schafer](https://www.youtube.com/user/schafer5)

## About
This project is a part of the SBE306 course (Computer Systems 3) in the [Systems and Biomedical Engineering Department - Cairo University](http://bmes.cufe.edu.eg/)\
Dr.Ahmed Kandil\
TA. Ayman Anwar


[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
