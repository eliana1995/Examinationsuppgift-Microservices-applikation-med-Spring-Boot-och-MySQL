Jag har skapat en distribuerad applikation baserad på mikrotjänstarkitektur med två Spring Boot-applikationer: UserMicro och OrderMicro. Båda applikationerna är deployade på AWS och kommunicerar med varandra via REST API.

Databas:
Jag har skapat två separata MySQL-databaser på AWS:

user_service_db: Används av UserMicro-applikationen för att lagra användardata.

order_service_db: Används av OrderMicro-applikationen för att lagra orderinformation.

Applikationer:
UserMicro: En Spring Boot-mikrotjänst som hanterar användardata. Den är konfigurerad att köras på port 8081 och tillhandahåller REST API:er för att skapa och hämta användare.

OrderMicro: En Spring Boot-mikrotjänst som hanterar orderinformation. Den kommunicerar med UserMicro via REST API för att hämta användardata, såsom användar-ID, som behövs för att skapa en order.

Körning av applikationerna:
Både UserMicro och OrderMicro körs på AWS, och jag har konfigurerat dem att kommunicera med varandra via deras respektive REST API:er. Jag har även säkerställt att applikationerna kan nå sina databaser på AWS för att läsa och skriva data.
![1](https://![Screenshot 2025-03-28 184350](https://github.com/user-attachments/assets/e8a3298f-1a3a-4062-8c9a-630c06e958c0)
github.com/user-attachments/assets/0aa22ffb-08ba-4752-b844-88809cfb765f)

Kommunikation mellan tjänster:
OrderMicro anropar UserMicro via REST API när den behöver hämta användardata.
![3](https://![Screenshot 2025-03-28 184440](https://github.com/user-attachments/assets/41871882-56ad-4d4e-8b08-8a420f95f011)
github.com/user-attachments/assets/b72a8963-2306-4c5a-8def-04c13962fb82)

UserMicro svarar med den begärda informationen, som sedan används av OrderMicro för att skapa och hantera order.
