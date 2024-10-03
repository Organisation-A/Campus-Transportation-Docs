# About 📄

## Table of Contents
- [Key Features ](#keyfeatures)
- [Tools](#tools)
- [Diagrams](#Diagrams)
- [Implementations](#implementations)
- [Meetings](#meetings)
- [Reports](#reports)


## Key Features 
- **Bike, Scooter, and Skateboard Rentals**: Rental service for bikes, scooters, and
skateboards to enhance campus mobility
- **Transportation Schedules**: Display a weekly schedule of the bus leaving and coming to campus.
- **Interactive Maps**: Navigate the Map
- **Real-Time GPS Tracking**: : Track real-time location of campus shuttles, buses, and
other transportation services
- **Accessibility Routes**:  Provide routes that accommodate individuals with disabilities.
- **Rental Stations**: Locate and check availability of rental stations across campus.

## Feature list
A feature list in app documentation is a detailed outline of the key functionalities or capabilities of an application. It provides a clear, structured summary of what the app can do, serving as a quick reference for developers, users, or stakeholders to understand the main offerings of the app. Each feature may include a brief description of its purpose and how it benefits the user.
###  User Login and Password Management
Users can log in by entering their credentials, including email and password. The password must meet certain requirements, such as a minimum length and the inclusion of special characters. If a user forgets their password, they can use the "Forgot Password" feature to reset it, and a confirmation email will be sent to them for verification.

- **User benefit** : Provides secure access to accounts with password validation for enhanced security. The "Forgot Password" feature ensures users can regain access to their accounts if needed.

- **Dependecies** : Requires a valid email address for account creation and password reset functionality. Email service must be configured to send confirmation emails.

- **Status** : Available and fully functional.

### Singup Page
New users can create an account by providing the following information:Username,Email address, and a password.
- **User benefit** : Email verification ensures that only valid accounts are created,Strong password requirements help enhance account security..
- **Dependecies** : A valid email address is required for signup and email verification.
- **Status** : Available and fully functional.

### Sidemenu
The side menu provides easy navigation to the following sections of the app:
- **Home Page**
- **Profile Page**
- **Bus Schedule Page**
- **Rentals Page**
- **Logout Page**

- **User benefit** : Convenient navigation to essential app features,Simplifies returning to the homepage or securely logging out from the app.
- **Dependecies** : The profile, bus schedule, and rentals pages require users to be logged in.
- **Status** : Available and fully functional.

### Search Bar
Allows users to look up for locations around campus.
#### Filtered search list
Users are able to search up locations around campus and get help from the filtered list they won't have to type up the whole name of the location.
#### Results 
The search result consist of the picture of the list and description.


- **User benefit** : it is faster for users to lookup places, users get to have a picture of what the place they're looking for looks like.
- **Dependecies** :  Requires internet access for search queries.
- **Status** : Available and fully functional.

### Map
The Maps feature integrates Google Maps into the app, allowing users to explore various locations and landmarks related to rentals.
#### Locations - Popup Information
When you interact with the landmarks or locations on the map, you get a mini-popup about the location
#### Rentals landmarks
We added bicycle,car,skateboard landmarks on the map to show available rentals. when you interact with the landmarks, you can see if you have to dropoff there or it's too far from your current location.
#### Dark/Light mode feature
you can change the map from light mode and back to dark mode.


- **User benefit** : Easy navigation and exploration of rental landmarks through an interactive map,Informative popups enhance the user experience by providing relevant details about each location.
- **Dependecies** : Requires an active internet connection for Google Maps to function properly,Google Maps API must be integrated and configured within the ap
- **Status** : The Maps feature is fully implemented and operational, providing users with a seamless experience in exploring rental landmarks.
### Profile page
The Profile Page provides users with a personalized overview of their account information, change password feature, including their username, email, kudubucks balance, and current rental details.

- **User benefit** : Provides a quick and easy way for users to view their account details and current rentals,Enhances user engagement by displaying kudubucks,
- **Dependecies** : Requires user authentication to access profile information,Rental data must be linked to the user’s account for accurate display.
- **Status** : The Profile Page is fully functional and provides a comprehensive overview of user information.

### Home Page
The Map Card feature enhances user interaction with the map by providing options to customize the map's theme and view directions based on their preferred mode of transportation.

- **User benefit** : Personalizes the map experience, catering to individual user preferences for theme and navigation style.
- **Dependecies** : Requires integration with mapping services (e.g., Google Maps API) to implement theme changes and generate accurate directions based on user selection,An active internet connection is necessary for real-time map updates and navigation features.
- **Status** : The Map Card feature is fully implemented and operational, offering users a versatile and customizable mapping experience.

### Transport Schedule page

### Rentals Page

### Logout Page

## Tools
- **Jira**: For planning.
- **Frontend**: React js,CSS.
- **Backend**: Express Js,Node Js, Azure, Vercel.
- **Communication**: Discord,Whatsapp,Emails
- **Authentication**: Firebase
- **Database**: Firebase Firestore
- **Figma**: Designing the UI and Protoype

## Diagrams

### user story🐾

### Deployment Diagram

![Alt Text](./Images/DeployDiag.png)

### Component Diagram

![Alt Text](./Images/CompDiag.png)

### Wireframe

![Alt Text](./Images/w1.png)
![Alt Text](./Images/w2.png)
![Alt Text](./Images/w3.png)
![Alt Text](./Images/w4.png)

### Initial Mockups
![alt text](./Images/ObaksUi.png)

### Official Mockups & Mobile view

![alt text](./Images/official1.png)
![alt text](./Images/offial2.png)

#### Mobile view

![alt text](./Images/mobileui.png)


### Protoype

![alt text](./Images/protoype.png)
If you want to interact with the prototype
**Figma Link**: https://www.figma.com/proto/ZuXHB5KS0UVghmuc7LD21M/Campus-Transportation?node-id=65-193&node-type=canvas&t=xv0NqEbJMG7L7af0-0&scaling=contain&content-scaling=fixed&page-id=0%3A1&starting-point-node-id=65%3A193&show-proto-sidebar=1

## Implementations

### Changes requested by our supervisor
- **Add some validation on the login/signup**: At the beginning of our app the user just had to put in their detail in this an email and password but after our meeting with our supervisor on the 5th of september, He suggested thAvailable and fully functional.at we coudld have some validation for our password, like having special characters in our pasword also the having a specific length for the password. On top that we added a toast that pops everytime the user's password doesn't satisfy the requirements.
- **Add a hello {username} feature**: Every user has their name and email stored in the database such everytime when they log in to our system, on the profile page their usename printed out.Like the image below.
![alt text](./Images/profileUI.png)
- **Add a profile page**: The image above is the implemented profile page on our system, shows you booked vehicles, it has it's own kudubucks system.
- **Add a change password feature on the Profile page**: Below is an image that kind of shows how a user can change their password on the profile page, they click the "change password link" and a pop up will show up, and they can either cancel or change their password.
- **Add Renting stations on the map**: We decided to add a bicycle landmark to every rental station on main campus.
- **Add pickup and dropoff stations**:🐾
- **Add more implementations luca required**:🐾
### Changes we discussed 
- **Change the theme of the app**: Now we added a feature for light/dark mode 
- **Add accessible routes on the map**:🐾
### Changes after integrating with other APIs
See "Link to implementations in the API specification"🐾

## Meetings

### Meetings Calendar

<iframe src="https://calendar.google.com/calendar/embed?src=91c70e37bf75f308d704076c16705683a16d3bfd0d0e8f4c76d1c2406452c19b%40group.calendar.google.com&ctz=Africa%2FJohannesburg" style="border: 0" width="800" height="600" frameborder="0" scrolling="no"></iframe>

### Future plans
As seen from the Calendar we have been tracking when to have out meetings and we do we need to plan our upcoming implementations for our app

### Timeline
For proof of meeting please checkout our drive "campus transportation>Meetings" :https://drive.google.com/drive/u/0/folders/1zxj784kdAtxYXiMoWFnsLQTfLaxCZ4dK
#### Scrum 1 🎯
#### 12 August 2024 
- Dicussion: Tools, setting up our environment and getting started
- Attendees: Uhone, Kgolagano, Lethabo, Obakeng, Gael, Wendy
#### 14 August 2024
- Dicussion: Designing Wireframe and assigning roles
- Attendees: Uhone, Kgolagano, Lethabo, Obakeng, Gael, Wendy
#### 17 August 2024
- Dicussion: UI designs and database schema,API
- Attendees: Uhone, Kgolagano, Lethabo, Obakeng, Gael, Wendy
#### 18 August 2024
- Dicussion: UI design and Prototype
- Attendees: Uhone, Lethabo, Gael, Wendy
#### 20 August 2024 Milestone 1 🏆
#### Scrum 2 🎯
#### 24 August 2024
- Dicussion: Milestone Overview
- Attendees: Uhone, Kgolagano, Lethabo, Obakeng, Gael, Wendy
#### 28 August 2024
#### 29 August 2024
- Dicussion: Client Meeting, adding more features like having a login,signup page
- Attendees: Uhone, Kgolagano, Lethabo, Obakeng, Gael, Wendy, Luca
#### 12 August 2024
#### 12 August 2024
#### 12 August 2024
#### 12 August 2024

### User Feedback 🐾

### User Guide 🐾

## Reports
🐾
- On the 12th of August we had issues with trying to deploy the "Hello-world" page
- We had problems with communicating with Campus safety group a their apis required ids which we didn't get
- Events group did not provide their APIs instead they gave us their API documentation
- We had problems trying to deploy using AZURE so we tried out vercel
- Our app takes an hour to deploy
- We ran out of credits on firestore so we had to upgrade.
