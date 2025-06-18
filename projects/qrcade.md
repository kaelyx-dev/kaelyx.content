{{
project 
name=QRCade 
desc="QRCade was a Masters Thesis project used for identifying the gamifications of QR Codes for Mobile Exergaming. This project attempts to mimic the design-space of laser tag without the dedicated hardware, using a phones and a webserve to play"
techstack=Typescript,NodeJS,ExpressJS,SQLite,Sequelize,React,Vite,Tailwind
projectlink=https://github.com/kaelyx-dev/qrcade
}}

QRCade uses a Simple REST Api to track players scanning QRCodes, each QRCode encodes an endpoint + a slug holding the user's ID, the server will then check if the player who scanned "shot" the other player "hit" is in the same lobby, and depending on gamemode, same team. Tracking scores of individual players and teams.

This project was created to help answer a research question as part of a Masters Thesis for a MSc Advanced Computer Science Masters Degree. This project aimed to help explore physicality to mobile exercise games by explorng how people can interact with QRCodes and the plausible design-space surrounding the gamification of QRCodes for Mobile Exercise Games.

To anyone interested, this project scored a high First classification (89/100) and completed the Masters Degree at a Distinction Level.

This project was then later showcased as part of the University's Computer Science Exhibition as Schools as an example of what is possible.
