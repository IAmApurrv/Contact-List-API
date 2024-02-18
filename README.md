# Contact-LIST-API


<h3>To create a new contact :</h3> <h1>POST http://localhost:3000/contacts</h1>
<h3>To fetch contact by id :</h3> <h1>GET http://localhost:3000/contacts/:id</h1>
<h3>To fetch all contacts :</h3> <h1>GET http://localhost:3000/contacts</h1>
<h3>To update a contact by id :</h3> <h1>PUT http://localhost:3000/contacts/:id</h1>
<h3>To delete a contact by id :</h3> <h1>DELETE http://localhost:3000/contacts/:id</h1>
<h3>To search contact :</h3> <h1>PATCH http://localhost:3000/contacts/search?term=query</h1>
<h3>To export all contacts to CSV :</h3> <h1>GET http://localhost:3000/contacts/export/csv</h1>


<h3>Body JSON --></h3>

{
  "name": "Apurrv",
  "mobileNumbers": ["9359507849". "942379647"],
  "imageUrl": "profile.jpg"
}



To run the provided code, you need the following dependencies :

npm install express

npm install mysql

npm install multer

npm install csv-writer



create database nodejs;

use nodejs;

create table contacts (
    id int auto_increment primary key,
    name varchar(255) not null,
    imageUrl varchar(255),
    created_at timestamp default current_timestamp
);

create table mobileNumbers (
    id int auto_increment primary key,
    contactId int,
    mobileNumber varchar(255) not null,
    unique (mobileNumber),
    foreign key (contactId) references contacts(id) ON DELETE CASCADE
);
#   C o n t a c t - L i s t - A P I  
 