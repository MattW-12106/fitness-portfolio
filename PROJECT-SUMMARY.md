# **Fitness App Using Mediapipe - Holberton Portfolio Group Project**

This is the basic outline of our group portfolio project (yay!).
Before we begin let's have a look at some of the other ideas considered for the portfolio project:

## **Other Ideas | The Good, The Bad, The Ugly**

---
### **Crime Prevention Social App**
--- 


**Problem it solves/Purpose:**
A social app for Melbourne’s at‑risk public that enables users to share safety information, report incidents, receive real‑time alerts, and connect with community resources, while addressing privacy‑law compliance.

**Key Features:**
SOS alert, GPS sharing, police upload

**Strengths and Weaknesses:**
The app could be very good for people in a situation where they can't necessarily call emergency services due to having to be quiet/hide *but* GPS Sharing has some glaring privacy law issues and potential permission(s) issues.

**Target Audience:**
Melbourne public, at-risk users

---
### **Traveller Life Buddy**
---

**Problem it solves/Purpose:**
A companion app for solo travellers and backpackers, focusing on safety, compliance (GDPR/APP), and protection against bad actors.

**Key Features:**
Cross-path alerts, travel timeline, matching

**Strengths and Weaknesses:**
GDPR/APP compliance, bad actors

**Target Audience:**
Solo travellers, backpackers

---
### **AI Plant Care Companion**
---

**Problem it solves/Purpose:**
An AI companion designed to help plant owners and gift recipients care for their plants by providing personalized advice.

**Key Features:**
AI ID scan, health diagnostics, reminders

**Strengths and Weaknesses:**
False positives, lighting/camera quality

**Target Audience:**
Plant owners, gift recipients

---
### **Apartment Research Tool**
---

**Problem it solves/Purpose:**
Apartment hunters open dozens of tabs checking crime stats, violations, utilities, transit, 311 complaints across scattered government sites. Impossible to remember and compare multiple addresses before signing a lease.    This tool collapses all of that into one address search. Type in a rental address and get a single report pulling from 20+ government data sources, with red flag alerts for anything that should make you think twice before signing a lease.

**Key Features:**
Gov API aggregation, red flag alerts, compare

**Strengths and Weaknesses:**
No unified AU database, defamation risk

**Target Audience:**
Renters, interstate movers

---
### **AI Grocery Assistant**
---

**Problem it solves/Purpose:**
AI Grocery Assistant is a new, idea aimed at families and budget shoppers, seeking to help users manage grocery shopping efficiently

**Key Features:**
Inventory tracking, smart lists, price comparison

**Strengths and Weaknesses:**
It was clear that australians waste significant food and money on unused pantry products and combining both inventory tracking and shopping list. However, we found some limitations within the API available in Australia for the main grocery markets to track prices. The data entry being manual was a big issue as well as there is no way to track the pantry otherwise. 

**Target Audience:**
low-budget Families, budget shoppers, students

---
### **Purchasing Scam Detector**
---

**Problem it solves/Purpose:**
Detects purchasing scams for Amazon, Temu, and eBay shoppers, offering AI‑driven analysis to identify fraudulent listings, unreliable reviews, and potential bot activity.

**Key Features:**
Reverse image search, review sentiment scan

**Strengths and Weaknesses:**
Broad scope, AI reliability, botted reviews

**Target Audience:**
Amazon, Temu, eBay shoppers

---
### **Smart Personal Safety Companion**
---

**Problem it solves/Purpose:**
People in Melbourne feel unsafe walking alone, and help may not arrive immediately when something happens.

**Key Features:**
Dead Man Switch - User sets a timer, Quick SOS

**Strengths and Weaknesses:**
Background tracking reliability: Mobile OS (iOS/Android) may restrict background GPS updates or timers

**Target Audience:**
Parents, women, kids

## **So what are we doing and why?**
We are making a fitness app utilising Mediapipe. This app will focus on gameifying the act of working out, as some people find it hard to find the motivation to work out. How we will achieve this is by providing a library of games with mediapipe compatability to track the movements of your excersises to interact directly with the game(s). Users will create a profile which will track statistics such as XP, daily streaks and stats in regards to workout progress.

The goal of this web-application is to help people who find it hard to find motivation to go to the gym or keep fit. This can also be applied to those that have any form of neuro-divergency which rely more heavily on instant gratification to find motivation. The idea is that the outcome of this project will help retain a decent routine for keeping people more active.

Expanding on the features as stated previously; we will be implementing Mediapipe as our main driving force and this is what will be allowing you to interact directly with the game(s). Mediapipe is an AI-driven tracking software which maps your limbs using camera-detection to track your movements in a way which directly speaks to the code and by extension, any game we create/add to the web-app. To help keep your motivation and your progress on track, we will also be implementing an account system which tracks XP/Levels you get from playing the games, on top of daily streaks (similar to Duolingo) which will help boost your daily retention. Things that might be added later include: badges, achievements, co-op play with friends, leaderboards, etc. We're hoping that this creates an engaging environment where you want to keep playing. The app can be accessed by any machine with an internet connection and access to a camera (as a camera is essential for mediapipe to work of course).

For legal reasons, we'll be implementing only a small amount of games (as legally-distinct as possible) purely for the purposes of showcasing the technology behind our idea and how it can potentially be used in the future. We're hoping that by using this approach we can focus more on the implication of what positive impact an application like this can achieve, more than the actual games themselves; as typically with an app like this there would be updates and new games added to the 'library' over the course of the apps' lifespan.
