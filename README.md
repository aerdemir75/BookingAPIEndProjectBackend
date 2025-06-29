Eindproject: Bookings API
Overzicht
Dit project is het slotstuk van de Back-End cursus bij Winc Academy. Het bouwt een API voor een denkbeeldig boekingsplatform, waarmee gebruikers, huizen, boekingen en reviews beheerd kunnen worden.

Technieken die gebruikt zijn: Node.js, Express, Prisma met SQLite, authenticatie via JWT en foutregistratie met Sentry.

Starten met het project
Stappen om alles werkend te krijgen:

Clone deze repo naar je lokale machine.

Open de projectmap en installeer de benodigde pakketten met:

bash
Copy
npm install
npm install zod
Maak een .env bestand aan in de hoofdmap met deze variabelen:

ini
Copy
DATABASE_URL="file:./dev.db"
AUTH_SECRET_KEY=<vul hier een geheime sleutel in>
SENTRY_DSN=<je Sentry DSN of leeg laten>
Voer de database migratie uit en zet voorbeelddata erin met:

bash
Copy
npx prisma migrate dev --name init
npx prisma db seed
Start de server met:

bash
Copy
npm run dev
Wat kan deze API?
Beveiliging met JSON Web Tokens

CRUD-functies voor gebruikers, verhuurders, woningen, boekingen, voorzieningen en beoordelingen

Filters toepassen via URL-parameters (bijvoorbeeld zoeken op gebruikersnaam of locatie)

Valideren van inputdata met Zod om fouten te voorkomen

Ophalen van gerelateerde data via Prisma include

Afhandeling van fouten met duidelijke meldingen en logging in Sentry

Er zit standaard data in om te testen, via een seed-script

Testen
Automatische tests draaien:

Zorg dat de server actief is (npm run dev).

In Postman moet je omgeving ingesteld zijn op http://localhost:3000.

Voer uit:

bash
Copy
npm run test-positive  # Positieve tests
npm run test-negative  # Negatieve tests
Deze tests staan in de map /postman en gebruiken de omgevingsbestanden uit /postman/environments.

Let op: sommige tests verwijderen data, dus na testen server opnieuw starten.

Prisma Studio
Tijdens ontwikkeling kun je Prisma Studio openen om je database visueel te beheren:

bash
Copy
npx prisma studio
Gebruik dit alleen tijdens het ontwikkelen, want je wijzigt direct data.

Gebruikte tools & technologieën
Node.js & Express

Prisma ORM met SQLite

JWT voor authenticatie

Zod voor data validatie

Sentry voor foutmonitoring

Postman & Newman voor testen

Over Arif Erdemir
Dit eindproject is gemaakt door Arif Erdemir als onderdeel van zijn opleiding bij Winc Academy.