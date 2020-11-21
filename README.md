# Covid19-Team-Project

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)

## Overview
### Description
Tracks the current number of Covid19 cases in each state using a public API and a travel advice based on the number of the caes. We are considering extending the features to also show current local Covid19 related restrictions and other news.

### App Evaluation
- **Category:** Social Networking / Music
- **Mobile:** This app would be primarily developed for mobile.
- **Story:** Fetches data from a public API
- **Market:** Any individual could choose to use this app.
- **Habit:** This app could be used as often or unoften as the user wanted.
- **Scope:** Will cease to be popular once the pandemic is over.

## Product Spec
### 1. User Stories 
**Required Must-have Stories**

* User scrolls to choose the state they need the data for.
* User can choose which state they will be checking most often
* When they tap on a state, it brings them to another screen with the data.

### 2. Screen Archetypes
* Screen with news, states, prevention guidelines, and other statistics.
* Scrolling screen with states
* Screen with data



### 3. Navigation

**Tab Navigation** (Tab to Screen)
* State selection


**Flow Navigation** (Screen to Screen)
* Scroll -> tap the state you'd like to know the data for -> another screen with the desired data shows up

## Wireframes
<img src="https://imgur.com/n62paka.jpg" width=800><br>

### 4. Schema
Model: Row Entry
| Property  | Type | Description |
| ------------- | ------------- |-------------|
| objectId  | Content Cell  |date when post is last updated (default field)|
| caseCount  | Number | number of active Covid19 cases|
| updatedAt| DateTime| date when post is last updated (default field)|

### 5. Networking
#### List of network requests by screen
- Home Screen:
    - N/A

- State Data: 
  - (Read/GET) Get the data for each state 

- Country Data:
  - (Read/GET) Get the data for each country
  
  let query = PFQuery(className:"Row entry")
query.whereKey("objectID")
query.order(byDescending: "")
query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
   if let error = error {
      print(error.localizedDescription)
   } else if let posts = posts {
      print("Successfully retrieved \(posts.count) posts.")
      // TODO: Do something with posts...
   }
}
