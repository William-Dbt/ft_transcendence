# 🖱 42Paris Project | ft_transcendence

<img src="https://github.com/William-Dbt/ft_transcendence/blob/main/files/SCR_title.png">

## Objectives

This project is about creating a **website** that implements a **chat**, the mighty **pong game** and an **authentication** system with 42API.  

**Languages / Frameworks used:**  
- Backend: NestJS, PostgreSQL, Prisma  
- Frontend: Svelte, Tailwind CSS  

All the project have to be done with docker and docker-compose and the website must be a single-page application.  

**Authentication features:**  
- User must login using **OAuth** system of 42 Intranet. (You must be a 42 Student)  
- The user should use a personnal nickname and avatar that will be seen by all other users.  
- The user should be able to enable **two-factor authentication**. We use Google Authenticator for this project.  
- The user should be able to add other users as **friends** and see their status (Online, in Chat, in Game and disconnected).  
- User profile must display **user's stats** such as wins and loses, ladder level, achievements...  
- Each user must have Match History including 1v1 games, ladder and everything usefull. Everyone who's logged is able to consult it.  

**Pong features:**  
- User can play **live Pong game** versus another player directly on the website.  
- A **matchmaking system**: user can join a queue until they get automatically matched with someone else.  
- User can start a game in **Hard mode** (increase ball speed and descrease pallet size for each shot) or in **Normal mode** (the default one).  

When a user wins a match he earns a point. On the other hand, when he loses a match, he loses a point.

**Chat features:**
- User can **create** and **talk** in a channel.  
- User can be **owner** or **administrator** in the channel. The owner retrieves this status when creating the channel until they leave it. An owner can set a user as admin, an administrator (and the owner) can **kick**, **mute** or **mute** a user in the channel.  
- User can **send direct message** to someone else, a new **private conversation** will be created for both users.  
- One user can **block** another, at this moment the user will no longer see the blocked person's messages.  
- User can **invite** another user to play a Pong game.  

## Usage

`make` to start docker files with docker-compose.  
`fclean` to clean all containers stuff (images, networks...).  
`restart` to restart all containers.  
`logdatabase, logback and logfront` will respectively shows container of the database, the backend and the frontend logs. It is usefull when you can't have Docker Desktop (not installed on 42's computers).  

The **website** is accessible at the address http://localhost:3333/ once containers are up.  
You can access the **database** at http://localhost:5555/ (thanks **prisma studio**).  

You have to give a .env file in the **backend repository**. See an example below:
```
POSTGRES_USERNAME=postgres
POSTGRES_PASSWORD=123
POSTGRES_DB=nest
DATABASE_URL="postgresql://postgres:123@db:5432/nest?schema=public"

AT_SECRET=accessTokenSecret
RT_SECRET=refreshTokenSecret

REDIRECT_URI=http://localhost:3000/auth/local/handleCallback

AUTHORIZATION_ENDPOINT=https://api.intra.42.fr/oauth/authorize

CLIENT_ID=
CLIENT_SECRET=
SPEAKEASY_SECRET=transcendance

PUBLIC_API_URL="http://localhost:3000"
PUBLIC_FRONT_URL="http://localhost:3333"
```

The **CLIENT_ID** and the **CLIENT_SECRET** is only used to connect a user by the **42 OAuth system**. Take yours to try to system.  

## Collaborators

This project was carried out by 4 others people:  
[Xavier Le-baux](https://github.com/Xavier-LB "Xavier Le-baux")  
[Julia Batoro](https://github.com/Clivassy "Julia Batoro")  
[Yann Bellot](https://github.com/YannRepo "Yann Bellot")  
[Nicolas Mattera](https://github.com/niko-mttr "Nicolas Mattera")

## Screenshots

<img src="https://github.com/William-Dbt/ft_transcendence/blob/main/files/SCR_home.png">
<img src="https://github.com/William-Dbt/ft_transcendence/blob/main/files/SCR_pong.png">
<img src="https://github.com/William-Dbt/ft_transcendence/blob/main/files/SCR_signup.png">
<img src="https://github.com/William-Dbt/ft_transcendence/blob/main/files/SCR_profile.png">
<img src="https://github.com/William-Dbt/ft_transcendence/blob/main/files/SCR_chat.png">
<img src="https://github.com/William-Dbt/ft_transcendence/blob/main/files/SCR_channels.png">
