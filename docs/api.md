# API specification

> The Campus Transportation API provides a comprehensive solution for managing and optimizing transportation services across wits campus. This API allows developers to integrate key functionalities such as getting map data, route management, and bus schedule into campus-wide systems. It is designed to facilitate smooth operation of campus shuttles, improve student and staff transit experiences, and ensure effective communication of transportation information.

With this API doc, users can :

- Can have access to data about buildings,routes and amenities.
- Access Real-Time tracking for campus transportation facilities
- Get data on accessible routes and facilities.
- Have a view od the Trabsportation schedule and updates
- Get the best routes based on their current conditions
- Access to rental stations and a view of which vehicles are available.

## Map data API
<iframe src="./API/MapDataAPI.html" width="100%" height="800px"></iframe>

## Transportation Schedule API
*Put the swagger thing here🐾*
*fix the swagger ui stuff based on our actual APIs*

## Rental Service API
<iframe src="./API/RentalServiceAPI.html" width="100%" height="800px"></iframe>

## Internal and External APIs

### Backend

For the backend, we have made use of **Vercel** since it is an optimal technology, easy to use, and helps with separation of concerns. This is particularly useful because we want to prevent the entire system from failing if either the backend or frontend experiences an issue. By separating both ecosystems, management becomes much more efficient.

The main reason we chose Vercel is because it makes our APIs available to other teams, facilitating integration into their systems without relying on Azure deployment. Vercel is more user-friendly and has a gentler learning curve compared to Azure, which can often be more complex. Additionally, adding both the frontend and backend to Azure would increase the complexity of the project, which is not ideal.

### Frontend

For the frontend, we used **Azure** because it is a technology we are more familiar with. While we used Vercel for the backend, Azure is sufficient for deploying the frontend.

In this approach, we aimed to use familiar, new, and optimal technologies, taking into consideration the integration with other teams.

### APIs

As mentioned before, our APIs are deployed using **Vercel** for the backend. This allows us to have live links to integrate with other teams when necessary.

#### External API
- **/getLocations**: Used to retrieve campus buildings, and can be accessed through the following link:  
  `https://api-campus-transport.vercel.app/getLocations`

#### Internal APIs
- **GET** requests:
  - `/getRent`: Retrieves all items available for renting along with their details.  
    `https://api-campus-transport.vercel.app/getRent`
  - `/getSchedule`: Retrieves the bus schedule, specifically for buses arriving and departing from campus.  
    `https://api-campus-transport.vercel.app/getSchedule`

- **POST** requests:
  - `/rent/${UID}/${ritem}`: Adds a rented item to the user's collection, associating the user with the rented item.  
    `https://api-campus-transport.vercel.app/rent/${UID}/${ritem}`
  - `/cancel-rent/${UID}/${ritem}`: Updates the user's collection to cancel or complete a rental, removing the fields for the item and its location.  
    `https://api-campus-transport.vercel.app/cancel-rent/${UID}/${ritem}`

The POST APIs require the user ID (`UID`) and rented item ID (`ritem`) as arguments.

We recommend using **axios** for making API requests.

*APIS OBAKENG USED*

## Implementation

### Using the Emergency Alert API

We have decided to implement a popup feature that will appear during emergency situations, displaying the time of the emergency and relevant information. This popup will prevent the user from interacting with any other features of the app until they acknowledge the alert and take the necessary steps to evacuate the premises.
![alt text](./Images/emergencyALERT.png)

### Using the Events Management API

We decided to add a uique landmark on the map that show up when there's an event on campus.

*Picture of the implementation*

## Communication with the other teams

### Campus safety - Emergency Alert API


### Event Management - Events API

### Campus Infrastructure

