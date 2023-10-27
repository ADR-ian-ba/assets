# Installation guide WearHouse

![Alt Text](https://github.com/ADR-ian-ba/assets/blob/main/Logo-removebg-preview.png?raw=true)

This is a installation guide for the project WearHouse, plese follow through and if there is any issue, please do contact me, my contact is available at the [End Of The Page](#contact)

This readme is also available on :
https://github.com/ADR-ian-ba/assets/blob/main/README.md

## sqlserver

#### server
![Alt Text](https://github.com/ADR-ian-ba/assets/blob/main/ss1.png?raw=true)

===========================================================

<br/>
when creating a new server for the website, i use the name .\sqlexpress 

![Alt Text](https://github.com/ADR-ian-ba/assets/blob/main/ss2.png?raw=true)

<br/>

#### table
this web uses 2 table, consisting of Users and Category

![Alt Text](https://github.com/ADR-ian-ba/assets/blob/main/ss3.png?raw=true)

the query used to create the script is as  follows 

CREATE TABLE Users (
    id INT PRIMARY KEY IDENTITY(1,1), 
    name VARCHAR(255), 
    email VARCHAR(255), 
    password VARCHAR(255)
);


CREATE TABLE Category (
    category_id INT PRIMARY KEY IDENTITY(1,1),
    user_id INT,
    category_name VARCHAR(255),
    FOREIGN KEY (user_id) REFERENCES [Users] (id)
);

#### important !!!

the password will be hashed, so it is reccomended to just register using the front end to minimize the error potential

<br/>

for the  category however, if you create 1 user, the query for inserting data wll be



INSERT INTO Category (user_id, category_name)
VALUES
    (1, 'Book'),
    (1, 'Plate'),
    (1, 'Clothing'),
    (1, 'Electronics'),
    (1, 'Furniture');

note:(you can modify number 1 to be id of user in your database)

<br/>

#### dependency installation
###### api
when opening the file, please install the required dependency first

```bash
#navigate to api directory
./desktop/wearhousejs/wearhouseapi

#install required dependencymanually usi
dotnet restore

#run the api
dotnet run watch
```
after installing the required dependency and setting up the data base, the next and most important thing to do is to pray so the api works on "your" machine and not only on "my" machine 😅😅😂😂.

###### client
similar for api, the client uses react and have its own required dependency

```bash
#navigate to client directory
./desktop/wearhousejs/wearhouseclient

#install dependency
npm i  #can also use npm install

#run the client
npm run dev
```

<br/>

<a id="contact"></a>
### Contact
Thank you for following this installation guide. I hope you find it helpful in setting up the system. If you encounter any issues or have questions, please don't hesitate to reach out to me for assistance or a live demo.

this readme is also available on :
https://github.com/ADR-ian-ba/assets/blob/main/README.md

phone : (+62) 896-881-99309

email : [adrianpurnama209@gmail.com](mailto:adrianpurnama209@gmail.com)

instagram : instagram.com/adr_iyan_

personal website :
https://colorgen.onrender.com/
https://adr-ian-ba.github.io/ADR-ian/

consider trying my NPM Package
https://www.npmjs.com/package/easy-palette



### Best regards Adrian and happy coding! 🎉🎉












