# Tutorial: Go-Help

Go-Help is a platform that **connects people who need help** with household tasks  
(*like cleaning, repair, or babysitting*) with **skilled service providers**.  
Users can *sign up, log in, browse services*, and *request help*. Service  
providers can *register, create profiles*, and *manage incoming job requests*.  
All user and service data is persistently stored using a **database**, and  
provider profile images are handled by a **cloud file upload** system.

---

## Visual Overview

```mermaid
flowchart TD
    A0["Express Application (App)"]
    A1["Mongoose Database Connection"]
    A2["User Authentication (Passport & User Model)"]
    A3["Service Provider Authentication (Employ Model)"]
    A4["Provider Details (Provider Model)"]
    A5["Service Request (Request Model)"]
    A6["EJS Views"]
    A7["Cloudinary File Uploads (Multer & Cloudinary)"]

    A0 -- "Connects to" --> A1
    A0 -- "Authenticates Users via" --> A2
    A0 -- "Handles SP Auth via" --> A3
    A0 -- "Manages" --> A4
    A0 -- "Manages" --> A5
    A0 -- "Renders" --> A6
    A0 -- "Handles File Uploads with" --> A7
    A2 -- "Uses Model via" --> A1
    A3 -- "Uses Model via" --> A1
    A4 -- "Uses Model via" --> A1
    A5 -- "Uses Model via" --> A1
    A4 -- "Stores Metadata from" --> A7
    A6 -- "Accesses Data from" --> A4
    A6 -- "Accesses Data from" --> A5
    A6 -- "Accesses Data from" --> A2

