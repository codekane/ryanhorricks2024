---
title: "Anonidate"
description: "A full‑stack dating application built with React Native and Spring Boot, reviving a photo‑free, community‑driven approach to online connection."
summary: "Anonidate is a complete full‑stack prototype that reimagines anonymous dating through a modern technical lens. Built with React Native, Spring Boot, PostgreSQL, and WebSockets, it offers secure JWT authentication, location‑based discovery, and real‑time messaging—all without profile pictures."
slug: "anonidate"
date: "2025-09-14"
lastmod: "2026-09-17"
tags:
    - "React Native"
    - "Spring Boot"
    - "WebSockets"
    - "JWT"
    - "PostgreSQL"
---

**Project:** Anonidate  
**Role:** Lead Developer  

## Overview

**Anonidate** is a full-stack mobile application reviving the ethos of a 
beloved anonymous dating website from the early internet. In an era dominated 
by algorithmic swiping and visual first impressions, Anonidate strips away 
photos entirely — users connect through bios, interests, location, and the 
communities they frequent. Built with React Native and Spring Boot, the platform 
supports user registration, JWT-authenticated sessions, multi-step onboarding, 
location-based discovery, and real-time messaging via WebSockets. 


## Challenges and Objectives

- **Beyond the Meat Market:** No photos. With no image to judge, interest comes down to bio, interests, location, and shared communities.
- **Stateful Mobile Client:** Coordinate authentication, session, onboarding, and connection state across a navigation-heavy React Native app, where any one change risked re-rendering the whole tree.
- **Authenticated WebSockets:** Route real-time messaging through Spring Security, resolving early 400/unauthorized errors that stemmed from token handling on both sides.
- **Geospatial Discovery:** Return distance-filtered nearby-user queries from PostgresQL, filtered server-side against a schema still in motion.
- **Multi-Step Onboarding:** Design a nested flow that persists user input across steps, supports back-navigation, and resumes correctly after app restart.


## My Contributions

### 1. Design and Research
- Walked through the application flow for Tinder, Bumble, and Meetup, to gain an understanding of what the genre demands — profile, discovery, match, conversation.
- Rebuilt the profile around text: no images, with structured fields for bio, interests, location, and community affiliation.
- Designed discovery as distance-filtered and text-first, with no swiping mechanic.
- Iterated on UI direction with Claude, using screenshots of reference apps as an input.

### 2. Backend Architecture (Java/Spring Boot)

- **Authentication & Authorization:** Built a secure authentication layer using Spring Security and JWT, with refresh tokens to maintain sessions across app restarts. Unit and integration tests cover the security flows.
- **Database Migrations:** Adopted Flyway for versioned schema migrations, replacing the initial `data.sql` once it became clear the schema would keep evolving.
- **User & Profile Management:** Designed RESTful endpoints for registration, profile updates, and onboarding status tracking, with proper validation and structured error handling.
- **Location‑Based Queries:** Added geospatial filtering using PostgreSQL’s `earthdistance` extension to return nearby users based on the authenticated user’s coordinates.
- **Real‑Time Messaging:** Developed a relational model for conversations and messages, then integrated WebSocket (STOMP) endpoints for real-time delivery.

### 3. Mobile Application (React Native / Expo)

- **Authentication Flow:** Built a shared layout for login and registration, with keyboard handling to avoid UI displacement. Auth state managed through React Context so screens could read the session without prop drilling.
- **Multi‑Step Onboarding:** Designed a nested navigation flow with a progress indicator, collecting GPS location, birthdate, gender, name, and bio. Corrected an off-by-one date error caused by UTC conversion, and persisted each step to the backend so returning users can pick up where they left off.
- **Profile Management:** Enabled users to view and edit their own profiles, then extended the same screens to enable read‑only viewing of other users.
- **Discovery Screen:** Connected the nearby‑users endpoint to a list with distance indicators. Resolved re‑rendering bugs that had caused unintended navigation jumps.
- **Messaging Interface:** Implemented a WebSocket client with state management and logging, then moved the socket logic out of the chat screen into a shared service — preventing reconnects on every navigation.

### 4. Product Roadmap

- **Monetization:** The original Anonidate was free — a passion project from a bygone era of the internet. Rebuilding it forced me to ask a question: is this worth my time?
- **Events:** The most straightforward path to revenue was connecting people in other ways, unrelated to dating. Events would build upon the existing location feature, and provide great value.
- **Competition:** NomadTable already offered the exact service I'd imagined, and they had traction. The niche was filled, and no alternative surfaced.

## Outcomes and Results

- **Feature-Complete Prototype:** Every core system built and functional end-to-end.
- **Secure Session Layer:** JWT authentication with refresh tokens, tested against expiry and restart.
- **Resumable Onboarding:** A multi-step flow that persists input across steps, supports back-navigation, and restores state after an app restart.
- **Distance-Filtered Discovery:** Nearby-user queries via PostgreSQL's earthdistance, returning results by proximity
- **Real-Time Messaging:** WebSocket delivery with persistent conversation history, stable across navigation.

## Reflection

Anonidate began with a book I won at the ConnectIT conference in Ho Chi Minh City, Vietnam — *Spring Security in Action, Second Edition*.
I carried it with me over many months of travel, and finding myself a cripple in Penang, I decided to learn something.

A week and a half in, the exercises stopped being interesting. I needed to build something, and the idea came from a meme — a founder who'd 
taught himself ASP.NET by building PlentyOfFish, and made a fortune off it. It reminded me of Anonidate, the original site I sought to 
reproduce, and how it went dark sometime around 2015. A decade later, I decided to bring it back.

The original ran as a dating site for people from 4chan, SomethingAwful, Reddit... all of the old-internet staples. It didn't have any pictures, 
just your name, age, location, gender, bio, and the sites you liked to frequent. No ads, no premium tier, no business model. It worked anyway. 
I found love, made friends, and readily admit the substantial impact the availability of this service had on my life.

I set out to remake it, however I ran into a couple of very real hurdles. For starters, it was built for another time — a world where Facebook 
was still gaining traction, and it was niche internet communities that memes were transmitted through. Bringing it into the modern era, 
and hoping to expand the target market beyond its original limits, I looked at linkages to Facebook and Instagram — connecting people through 
shared groups and interests rather than a list of forums. It was an interesting idea. It doesn't work without a large enough user base and a 
compelling reason for them to join... which is what led me towards events.

This was a compelling direction, and I remember feeling genuinely excited. I was on to something, or at least that's what I thought, until 
I started to share it with the people around me, and one of them mentioned NomadTable. It embodied the best path towards monetization 
I could imagine for this project, and it had traction. The original never needed to make money. I did. Without at least a hope of it,
the project was dead.

I installed NomadTable to see what I'd lost to. It was well made. The events worked exactly the way I'd imagined mine would. And it turns 
out that I didn't even like it. It was very good at what it did, and it solved a very real problem... it just wasn't my problem. 
Had I kept to the original scope, then the problems would have been deployment and marketing. Instead, I decided I had to make money. 
I murdered the project in the process.

Capitalism is a sin.

## Technical Summary

- **Skills:** React Native (Expo), Java/Spring Boot, PostgreSQL, WebSocket (STOMP), JWT Authentication, Location Services
- **Tools & Libraries:**
  - *Backend:* Spring Boot 3, Spring Security, Spring Data JPA, PostgreSQL, Flyway, JJWT, WebSocket (STOMP), Gradle
  - *Mobile:* React Native (Expo), React Navigation, Axios, Context API, AsyncStorage, Expo Location, WebSocket API
- **Key Features:** Photo‑free user profiles, distance-filtered discovery, multi‑step onboarding, real‑time messaging, persistent sessions

## Gallery
{{<gallery>}}
<img src="Welcome Screen.png" class="grid-w50 md:grid-w33" alt="The home screen for the app." />
<img src="Nearby Users.png" class="grid-w50 md:grid-w33" alt="The nearby users screen, where you can see other users who have registered that are in the area, and see their age, gender, and summary." />
<img src="Profile Screen.png" class="grid-w50 md:grid-w33" alt="The user profile screen, where you can view your name, age, and gender, as well as edit your location, summary, and bio." />
<img src="Messages Screen.png" class="grid-w50 md:grid-w33" alt="The messages screen, where you can see all of the message threads you are a part of." />
<img src="Message Thread.png" class="grid-w50 md:grid-w33" alt="An example conversation, showing that the websocket messaging feature is fully operational." />
<img src="Ask Screen.png" class="grid-w50 md:grid-w33" alt="Placeholder screen that was intended to serve as the host for the events feature." />
<img src="Login Screen.png" class="grid-w50 md:grid-w33" alt="Login Screen, where users can sign in, or create an account." />
<img src="Registration Email.png" class="grid-w50 md:grid-w33" alt="Part of the registration flow, we provide users the ability to enter an email, as well as to go back to the sign in screen." />
<img src="Registration Create Password.png" class="grid-w50 md:grid-w33" alt="Part of the registration flow, the user is asked to enter a password, and a valid password combination, or else go back to the prior screen." />
<img src="Registration Name.png" class="grid-w50 md:grid-w33" alt="Part of the registration flow, the user is asked to provide their name." />
<img src="Onboarding Date of Birth.png" class="grid-w50 md:grid-w33" alt="Part of the onboarding flow, we are asking the users for their date of birth." />
<img src="Onboarding Date of Birth Selection.png" class="grid-w50 md:grid-w33" alt="Part of the onboarding flow, the user is selecting their date of birth using a modal." />
<img src="Onboarding Gender.png" class="grid-w50 md:grid-w33" alt="Part of the onboarding flow, we are asking the users for their gender, providing the options of male, female, non-binary, or the preference not to say." />
<img src="Onboarding Location.png" class="grid-w50 md:grid-w33" alt="Part of the onboarding flow, we detect the users location using the relevant privileges, and provide them with the option to edit manually." />
<img src="Onboarding Bio.png" class="grid-w50 md:grid-w33" alt="Part of the onboarding flow, we require the user to provide a summary, and provide the option of filling out their bio." />
<img src="Onboarding Confirmation.png" class="grid-w50 md:grid-w33" alt="Part of the onboarding flow, we present the user with the data collected thus farr, and give them the opportunity to jump back in the flow, and edit what they've provided, or else to complete their account setup." />
{{</gallery>}}
