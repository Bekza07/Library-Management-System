# Library-Management-System

Students: Lebeko Surprise Shai 226059354
          Ayanda Lettie Mabaso 225213635
          Basetsana Khensani Madiba 226000377
          Naledi Maria Mahlatji 225272619
          Njabulo Hlelolwenkosi Mtshali 226027946
          Lindokuhle Shaun Ngwenyama 226011282
          Makhadzi Beyonce Ludere Mulaudzi 225276701
          Mbanjwa Luvuno 240182200    

Module: Information Systems 1.2

Create Table CLIENT (
Client_ID INT,
First_Name VARCHAR2 (50),
Last_Name VARCHAR2(50),
Phone_No VARCHAR2 (50),
Address VARCHAR2(50),
CONSTRAINT PK_CLIENT PRIMARY KEY (Client_ID)

);

INSERT INTO CLIENT  (
Client_ID, First_Name,Last_Name,Phone_No,Address)
VALUES (7269,'Leo', 'Brown','0651169781','VanderbijlPark');

INSERT INTO CLIENT  (
Client_ID, First_Name,Last_Name,Phone_No,Address)
VALUES (5432,'Mpho','Thabethe','0798068981','Evaton');

INSERT INTO CLIENT  (
Client_ID,First_Name,Last_Name,Phone_No,Address)
VALUES (9171,'Andile','Magwaza','0739002280''VanderbijljPark');

INSERT INTO CLIENT  (
Client_ID,First_Name,Last_Name,Phone_No,Address)
VALUES (7145,'Sanele','Mthethwa','0789351234''Sebokeng');

INSERT INTO CLIENT  (
Client_ID,First_Name,Last_Name,Phone_No,Address)
VALUES (4589,'Anele','Mbanjwa','0691230945''Krugersdorp');

CREATE TABLE LIBRARY(
LIBRARY_ID INT,
Name VARCHAR2(100),
Address VARCHAR2(100),
Phone_Number VARCHAR2(50),
CONSTRAINT PK_LIBRARY PRIMARY KEY (LIBRARY_ID)
);


INSERT INTO LIBRARY(
LIBRARY_ID,Name,Address,Phone_Number)
VALUES(2011,'The Book Garden','Brakpan','0114567891')
;

INSERT INTO LIBRARY(
LIBRARY_ID,Name,Address,Phone_Number)
VALUES(1924,'VUT Library','Vaal University','0213452956')
;

INSERT INTO LIBRARY(
LIBRARY_ID,Name,Address,Phone_Number)
VALUES(2423,'Sebokeng Library','Sebokeng','0112349876')
;

INSERT INTO LIBRARY(
LIBRARY_ID,Name,Address,Phone_Number)
VALUES(2112,'Books For All','Vereeniging','0129823480')
;

INSERT INTO LIBRARY(
LIBRARY_ID,Name,Address,Phone_Number)
VALUES(1905,'Just Books','Krugersdorp','0119126732')
;

CREATE TABLE BOOK (
Book_ID INT,
Title VARCHAR2(100),
ISBN INT, 
Publisher VARCHAR2(100),
Edition VARCHAR2(100),
No_Pages INT,
Price Decimal (5,2),
CONSTRAINT PK_BOOK PRIMARY KEY (Book_ID),
CONSTRAINT FK_BOOK_LIBRARY FOREIGN KEY (Library_ID)
REFERENCES LIBRARY (Library_ID),
);

INSERT INTO BOOK (
Book_ID,Title,ISBN,Publisher,Edition,No_Pages,Price,LIBRARY_ID
VALUES (2714,'SQL','2449','V.Zulu','1st',100,250.00,'1924');

INSERT INTO BOOK (
Book_ID,Title,ISBN,Publisher,Edition,No_Pages,Price,LIBRARY_ID
VALUES (2651,'Food For Life','1246','A.Lennnox','2nd',70,150.00,'2423');

INSERT INTO BOOK (
Book_ID,Title,ISBN,Publisher,Edition,No_Pages,Price,LIBRARY_ID
VALUES (25789,'Sergio The Lover','23698','S.Mtshali','2nd',100,250.00,'2011');

INSERT INTO BOOK (
Book_ID,Title,ISBN,Publisher,Edition,No_Pages,Price,LIBRARY_ID
VALUES (3672,'Love Conquers All','7512','L.Harvard','3rd',90,200.00,'2112');

INSERT INTO BOOK (
Book_ID,Title,ISBN,Publisher,Edition,No_Pages,Price,LIBRARY_ID
VALUES (20132,'IT Law','1290','B.Phikwayo','1st',340,300.00,'1905');


CREATE TABLE AUTHOR (
        Author_ID INT PRIMARY KEY,
        First_Name VARCHAR2(100),
        Last_Name VARCHAR(100)
     );

INSERT INTO AUTHOR (
        Author_ID,First_Name,Last_Name )
        VALUES (2468, 'Shaun' , 'Ndlovu'

     );

INSERT INTO AUTHOR (
        Author_ID,First_Name,Last_Name )
        VALUES (2364, 'Victoria' , 'Zulu'

     );

INSERT INTO AUTHOR (
        Author_ID,First_Name,Last_Name )
        VALUES (1292, 'Anne' , 'Lennox'

     );

INSERT INTO AUTHOR (
        Author_ID,First_Name,Last_Name )
        VALUES (3519, 'Quinton' , 'Jones'

     );

INSERT INTO AUTHOR (
        Author_ID,First_Name,Last_Name )
        VALUES (1992, 'John' , 'Stones'

     );

CREATE TABLE BOOKAUTHOR(
Book_AuthorID INT,
Author_ID INT,
Book_ID INT,
CONSTRAINT PK_BOOKAUTHOR PRIMARY KEY (Book_AuthorID),
CONSTRAINT FK_BOOKAUTHOR_AUTHOR FOREIGN KEY (Author_ID)
REFERENCES AUTHOR (Author_ID),
CONSTRAINT FK_BOOKAUTHOR_BOOK FOREIGN KEY (Book_ID)
REFERENCES BOOK (Book_ID)
);

INSERT INTO BOOKAUTHOR(

Book_AuthorID,Author_ID,Book_ID)
VALUES ( 09877,2468,25789
);

INSERT INTO BOOKAUTHOR(

Book_AuthorID,Author_ID,Book_ID)
VALUES ( 23984,2364,2714
);

INSERT INTO BOOKAUTHOR(

Book_AuthorID,Author_ID,Book_ID)
VALUES ( 10097,3519,2651
);

INSERT INTO BOOKAUTHOR(

Book_AuthorID,Author_ID,Book_ID)
VALUES ( 55328,1292,3672
);

INSERT INTO BOOKAUTHOR(

Book_AuthorID,Author_ID,Book_ID)
VALUES ( 38484,1992,20132
);

CREATE TABLE RESERVATION (
Reservation_ID INT,
Reservation_Date DATE,
Quantity INT,
Client_ID INT,
Library_ID INT,
CONSTRAINT PK_RESERVATION PRIMARY KEY (Reservation_ID),
CONSTRAINT FK_RESERVATION_CLIENT FOREIGN KEY (Client_ID)
REFERENCES CLIENT (Client_ID),
CONSTRAINT FK_LIBRARY FOREIGN KEY (Library_ID)
REFERENCES LIBRARY (Library_ID)

);

INSERT INTO  RESERVATION (
    Reservation_ID,Reservation_Date,Quantity, Client_ID, Library_ID)
VALUES (0018,DATE '2026-10-12', 1,7269,2011

);

INSERT INTO  RESERVATION (
    Reservation_ID,Reservation_Date,Quantity, Client_ID, Library_ID)
VALUES (0019,DATE '2026-10-19', 1,5432,1924

);

INSERT INTO  RESERVATION (
    Reservation_ID,Reservation_Date,Quantity, Client_ID, Library_ID)
VALUES (0020,DATE '2026-10-20', 1,9171,2423

);

INSERT INTO  RESERVATION (
    Reservation_ID,Reservation_Date,Quantity, Client_ID, Library_ID)
VALUES (0021,DATE '2026-10-25', 1,7145,2112

);

INSERT INTO  RESERVATION (
    Reservation_ID,Reservation_Date,Quantity, Client_ID, Library_ID)
VALUES (0022,DATE '2026-10-25', 1,4589,1905

);

Create Table STAFF  (
Staff_ID INT,
Name VARCHAR2 (50),
Email VARCHAR2 (50),
CONSTRAINT PK_STAFF PRIMARY KEY (Staff_ID)
CONSTRAINT FK_STAFF_LIBRARY FOREIGN KEY (LIBRARY_ID)
REFERENCES LIBRARY (LIBRARY_ID)

);

INSERT INTO STAFF  (
Staff_ID,Name,Email,LIBRARY_ID)
VALUES  (5671,'Basetsana','basi@gmail.com',2011);

INSERT INTO STAFF  (
Staff_ID,Name,Email,LIBRARY_ID)
VALUES  (5811,'Ayanda','aya@gmail.com',2423);

INSERT INTO STAFF  (
Staff_ID,Name,Email,LIBRARY_ID)
VALUES  (2392,'Mulaudzi','mulaudzi@gmail.com',1924);

INSERT INTO STAFF  (
Staff_ID,Name,Email,LIBRARY_ID)
VALUES  (3894,'George','geo34@gmail.com',2112);

INSERT INTO STAFF  (
Staff_ID,Name,Email,LIBRARY_ID)
VALUES  (5858,'Tshepo','tshepo23@gmail.com',1905);








