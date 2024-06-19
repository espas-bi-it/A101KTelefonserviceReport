
# AK101 Telefonservice, Docker Build
Docker build for future CI/CD setups.


## Requirements

**Software:** Docker, PHP, Composer



## Installation

Clone this repo
```bash
git clone https://github.com/espas-bm-it/A101KTelefonserviceReport.git
```
Switch the directory
```bash
cd A101KTelefonserviceReport
```
Create empty .env file 

Afterward copy and paste the variables from here: https://t.ly/wGlVw
```bash
echo #ENV Variables > .env
```
In the .env file, change line 12 to the following:
```bash
DB_HOST=db
```
Build the docker image
```bash
docker build -t [name]/laravel:[Version] .
```
- example

    ```bash
    docker build -t php/laravel:0.1 .
    ```

Inside docker-compose.yml, change the following line to your name and version number

    php:
        image: [name]/laravel:[Version]
        ports:  
        - 8000:80
        environment:
        - PMA_HOST=db
        - PMA_PORT=3306

Start the container    
```bash
docker compose up
```

In Docker, under container, switch to the exec terminal
```
Containers -> [Running Container Name] -> [name]/laravel:[Version] -> Exec
```
Migrate the DB
```bash
php artisan migrate
```
Finish the setup with the follwing snippet
```bash
npm install && npm run dev
```
You can reach the homepage through the following link
```
http://localhost:8000/
```

## Known Bugs

- Migrate doesn't include the column "configs"
- DatePicker error when trying to display data because I haven't found a way to point to the internal storage for the TicketCollector.xml path
- When registering, it throws an laravel log error. Just return to http://localhost:8000/ and the account should be created


# call_report

![image](https://github.com/bmit-elc/call_report/assets/113030969/61b01a3f-f671-4c4a-99f7-9a0f11780dc8)


- "Call Report" zielt darauf die Erreichbarkeit des Unternehmens und die Qualität des ESPAS Telefonservices zu optimieren.
Dieser Auftrag hat mehrere wichtige Ziele:

- Eines der Hauptziele besteht darin, die Optimierung und Sicherstellung der Erreichbarkeit des Unternehmens bzw. des ESPAS Telefonservices sicherzustellen. Dabei liegt der Fokus auf der schnellen Identifizierung von Schwachstellen und Engpässen.

- Ein weiteres Ziel ist die Aufrechterhaltung und Verbesserung der Kundenzufriedenheit. Hierbei dienen die gesammelten Daten als Grundlage für Weiterbildungen, Schulungen und Investitionen im Bereich des Telefonservices.

- Ein weiterer Schwerpunkt liegt auf der übersichtlichen Aufbereitung und Auswertung der telefonischen Kommunikationsdaten in grafischer Form. Dies ermöglicht es, Statistiken mit einer Überkreuzauswahl, sowohl für alle Kunden als auch für spezifische Kunden und für unterschiedliche Zeiträume, abzurufen.

- Im Rahmen des "Lost Call" Aspekts des Projekts analysiere ich speziell, welche Anrufe im ESPAS-Telefonservice angenommen oder verpasst wurden, sowohl einzeln als auch in Kombination. Die Auswahl des Zeitraums erfolgt zeitraumspezifisch, entweder durch eine spezifische Datumsauswahl über einen Kalender oder durch die Verwendung von Dropdown-Optionen wie "heute", "Diese Woche", "Dieser Monat" oder "Dieses Jahr". Zudem besteht die Möglichkeit, diese Daten für alle Kunden oder kundenspezifisch basierend auf der zugewiesenen Durchwahlnummer zu analysieren.

- Neben dem "Lost Call" Aspekt befasst sich der Projekt mit der Erreichbarkeit und die Analyse des Verhältnises zwischen angenommenen und verpassten Anrufen, um den Service Level in Prozent zu ermitteln. Dabei ist insbesondere die Geschwindigkeit, mit der Anrufe entgegengenommen werden, von Bedeutung. Zusätzlich erfolgt eine Zeitstempelauswertung, um festzustellen, zu welchen Zeiten Anrufe verloren gingen oder angenommen wurden, und dies sowohl für angenommene als auch verpasste Anrufe.
