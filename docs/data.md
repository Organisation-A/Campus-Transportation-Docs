# Database Schema
>The Campus Transportation Database is designed to manage and streamline transportation services on campus. It supports various functionalities, including vehicle management, route scheduling, user information, and real-time tracking of vehicles. The schema is organized into several interconnected tables, ensuring data integrity and facilitating efficient access to transportation-related information.

![alt text](./Images/classdiagram.png)


## Collections

### Buildings
Documents detailing campus buildings.

#### Barnato Hall
- **Description**: "Barnato Hall. Mixed-gender residence up to the age of 24 years of age (Undergraduate only). Housing 554 students in single rooms."
- **Image**: ![Barnato Hall](data:image/jpeg;base64,MvBCc1I/E/gBGGst5TLvTL6Urn2RaE5gqm2dw7cZsnOnnJ+8Mj5W0FgNUrQpJqCEkgg8N2OfLlceKLY8WrlP6GhmX4gZAq6vzAgabf59FAHWX8A0Lpd+W)
- **Latitude**: -26.186944
- **Longitude**: 28.024722
- **Name**: "Barnato Hall"
- **Other Names**: ""
- **Side**: "West"

---

### Events
Documents describing campus events.

#### Beer Garden
- **Date**: "5/10/2024"
- **Description**: "Bring a friend for an exciting evening. Refreshments will be sold."
- **End Time**: "23:00"
- **Latitude**: -26.190555555555555
- **Longitude**: 28.029999999999998
- **Name**: "Beer Garden"
- **Start Time**: "16:00"

---

### Rental Station Inventory
Documents detailing rental stations and available vehicles.

#### Origin Centre Station
- **Vehicle**: "Skateboards"
- **Availability**: 7
- **Latitude**: -26.192
- **Longitude**: 28.028
- **Location**: "Origin Centre"

---

### Transportation Schedules
Documents containing transportation schedules.

#### Schedule Document ID: 3fqCpz6ZG434qJYrdbqY
- **Days**: 
  - "Saturday"
  - "Sunday"
- **Route Name**: "WJ | WEC"
- **Schedule**: 
  - "09:00"
  - "09:20"
  - "09:40"
  - "10:00"
  - "11:00"
  - "12:00"
  - "13:00"
  - "14:00"
  - "15:00"
  - "16:00"
  - "17:00"
  - "18:00"
  - "19:00"
  - "20:00"
- **Stops**: 
  - "AMIC"
  - "WJ"
  - "WEC"
  - "AMIC"

---

### Users
Documents describing users of the transportation system.

#### User Document ID: 9mPofTkdTpONgS4eKYuUEWgBzZp2
- **Email**: "aa@gmail.com"
- **First Name**: "gg"
- **Item**: "BB"
- **Kudu**: 20
- **Last Name**: "gg"
- **Location**: "BB"

---

