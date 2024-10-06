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
<iframe src="./API/t.html" width="100%" height="800px"></iframe>

## Rental Service API 
<iframe src="./API/RentalServiceAPI.html" width="100%" height="800px"></iframe>

## Internal and External APIs

### Backend

For the backend we have made use of **Vercel**, since it is an optimal technology, easy to use, and helps with separations of concerns. This becomes handy because we do not want the whole system to fail if either the backend or the frontend fails, as such, separating both ecosystems makes management way more efficient.
The main reason we used Vercel was because it makes our apis available to other teams and helps integrating into their system without depending on the Azure deployment.
Vercel is way more user friendly and provides a better learning curve than Azure, which can often be a bit complex, and if we had to add both the frontend and backend to Azure, we would add more complexity to our project which is not optimal.

### Frontend

For the frontend we simple used **Azure** since it is a technology that we are more familiar with, and even though we used Vercel for the backend, Azure suffices when it comes to deploying the frontend.
Here we have taken into consideration the use of familiar, new and optimal technologies, trying to consider the integration with other groups.

### APIs

As specified before, our APIs are being deployed using Vercel for the backend, and this helps us get our links live to integrate with other groups if need.
The first **external API** is the /getLocations, which is used to get the buildings on campus, and it can be integrated by using this link: 
https://api-campus-transport.vercel.app/getLocations

#### The internal API

(GET):
https://api-campus-transport.vercel.app/getRent
https://api-campus-transport.vercel.app/getEvents
https://api-campus-transport.vercel.app/getSchedule
(POST):
https://api-campus-transport.vercel.app/complete-rent/${UID}/${item}
https://api-campus-transport.vercel.app/rent/${UID}/${item}/${location}
https://api-campus-transport.vercel.app/event/${UID}/${item}/${location}

**/getRent**: gets all the items available for renting, and their info.
**/getEvents**: gets all the items available for renting at events, the event itself and their info.
**/getSchedule**: gets the bus schedule, specifically the ones leaving and coming into campus.
**/rent**: adds the rented item to the users collection, and links to the user that rented the item.
**/event**: adds the rented item to the users collection, and links to the user that rented the item (rental at events).
**/complete-rent**: updates the users collection on a cancel/complete rental, where it deletes the added fields, item and location (both of the rented item), and increases the availability of the items in that particular station. 
The post **APIs** will take as arguments the user id and the rented item id as well.
The **drop-off items** feature on the stations makes use of the **/complete-rent** api.


####API optimisation

For the optimisation we add to ensure that the apis are only being fetched once from the firestore database and then stored in a session storage, or local storage, in order to avoid calling the api on every refresh or moves between tabs.
 Some apis such as the **/getRent** and **/getSchedule** do not make use of this functionality since we are considering the constant updates that come from different users, and the dynamic updates on the schedules based on the time of the day.

 **Recommend using axios for the APIs.**

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

### BuildingMap Component API Documentation

#### Overview:

The `BuildingMap` component is a React-based implementation of a Google Maps interface with additional features such as route calculation, custom markers, and user location tracking. It utilizes various Google Maps APIs and services to provide an interactive map experience.

#### Dependencies:

- React
- @googlemaps/js-api-loader
- axios
- Firebase (auth and firestore)
- react-toastify

#### Component State:

The component uses various state variables and refs to manage its functionality:

- `googleMaps`: Stores the Google Maps API object
- `userLocation`: Tracks the user's current location
- `directions`: Stores the calculated route directions
- `selectedMode`: Manages the selected travel mode
- `isDarkStyle`: Controls the map's visual style
- `userPickup`: Stores the user's pickup location
- `UID`: Stores the user's ID
- `selectedCoordinates`: Stores the selected destination coordinates

#### Main Functions:

##### `calculateDistance(lat1, lon1, lat2, lon2)`

Calculates the distance between two geographical points using the Haversine formula.

##### `handleDropOff(ritem)`

Handles the drop-off functionality for rentals by making an API call.

##### `handleDrop(location)`

Checks if the user is within range of a drop-off location and calls `handleDropOff` if true.

##### `calculateRoute(origin, destination)`

Calculates and displays a route between two points using the Google Maps Directions Service.

##### `createMarkersAndCalculateRoute(originLatLng, destinationLatLng)`

Creates origin and destination markers and calculates the route between them.

##### `loadPersistedRoute()`

Loads a previously saved route from local storage.

##### `calculateAndDisplayRoute(destination)`

Calculates and displays a route from the user's current location to a specified destination.

##### `addCustomLocationMarkers()`

Adds custom markers to the map for predefined rental locations.

##### `toggleMapStyle()`

Toggles between dark and light map styles.

##### `recenterMapToUserLocation()`

Recenters the map to the user's current location.

#### Google Maps API Usage:

##### Map Initialization

The component uses the `@googlemaps/js-api-loader` to load the Google Maps API:

```javascript
const loader = new Loader({
  apiKey: "YOUR_API_KEY_HERE",
  version: "weekly",
  libraries: ["places"],
});
```

##### Map Creation

A new map instance is created using:

```javascript
new googleMaps.maps.Map(mapRef.current, {
  center: userLocation,
  zoom: 17,
  fullscreenControl: false,
  mapTypeControl: false,
  zoomControl: true,
  streetViewControl: true,
  styles: isDarkStyle ? MapStyle : [],
});
```

##### Directions Service and Renderer

The component uses the DirectionsService and DirectionsRenderer for route calculations:

```javascript
directionsServiceRef.current = new google.maps.DirectionsService();
directionsRendererRef.current = new google.maps.DirectionsRenderer({
  suppressMarkers: true,
});
```

##### Info Windows

Info windows are used to display additional information when markers are clicked, implemented with `google.maps.InfoWindow`.

#### User Interaction

- Users can click on the map to set a destination and calculate a route.
- Users can toggle between dark and light map styles.
- Users can recenter the map to their current location.
- Users can select different travel modes (Walking, Driving, Bicycling, Transit).
- Users can view turn by turn directions for the calculated route.

#### Firebase Integration

The component integrates with Firebase for user authentication and data storage:

- It listens for changes in the user's authentication state.
- It fetches user data from Firestore when a user is authenticated.

#### Local Storage

The component uses local storage to persist:
- The last calculated route
- The user's preference for dark/light map style

#### Event Handling

The component sets up various event listeners:
- Map click events for route calculation
- Marker drag events for route recalculation
- Custom 'getDirections' event for external direction requests

## Implementation

### Using the Emergency Alert API

We have decided to implement a popup feature that will appear during emergency situations, displaying the time of the emergency and relevant information. This popup will prevent the user from interacting with any other features of the app until they acknowledge the alert and take the necessary steps to evacuate the premises.
![alt text](./Images/emergencyALERT.png)

### Using the Events Management API

We decided to add a uique landmark on the map that show up when there's an event on campus.

*Picture of the implementation*🐾

## Communication with the other teams

### Campus safety - Emergency Alert API
![alt text](./Images/safetyCOM1.png)
![alt text](./Images/safetyCOM2.png)

### Event Management - Events API
![alt text](./Images/eventsCOm1.png)
![alt text](./Images/eventsCOM2.png)

### Campus Infrastructure
![alt text](./Images/infraCOM1.png)
