# Boilerplate MVVM Design Pattern Jetpack Compose

This repo is intended to make it easier for you to initiate projects and easy to manage
using Kotlin as a programming language and MVVM architecture. With a project structure
that is already set up and can be integrated with popular libraries such as Hilt, Room, and Retrofit.

## MVVM Architecture
MVVM architecture enables better code readability and easier maintenance by separating concerns between 
data, user interface, and business logic.

### Project Package Structure
When creating the project package structure, it is essential to achieve an organized and 
sustainable codebase. Below, you can find an example of a package structure:

#### data Package
This package encompasses the data layer of the application. 
It handles database operations, preferences, and data sources.

```
├── app
│   ├── kotlin+java
│   │   ├── com.raychal.boilerplate_mvvm_compose
│   │   │   ├── data
│   │   │   │   ├── local
│   │   │   │   │   ├── database
│   │   │   │   │   │   ├── dao
│   │   │   │   │   │   │   ├── UserDao.kt
│   │   │   │   │   │   ├── entity
│   │   │   │   │   │   │   ├── UserEntity.kt
│   │   │   │   │   ├── pref
│   │   │   │   │   │   ├── AppPreferences.kt
│   │   │   │   │   ├── repository
│   │   │   │   │   │   ├── LocalRepository.kt
│   │   │   │   ├── remote
│   │   │   │   │   ├── api
│   │   │   │   │   │   ├── ApiService.kt
│   │   │   │   │   ├── model
│   │   │   │   │   │   ├── UserApiResponse.kt
│   │   │   │   │   ├── repository
│   │   │   │   │   │   ├── NetworkBoundResource.kt
│   │   │   │   │   │   ├── RemoteRepository.kt
│   │   │   │   ├── repository
│   │   │   │   │   ├── DataRepository.kt
│   │   │   ├── di
│   │   │   ├── model
│   │   │   ├── ui
│   │   │   ├── util
│   │   │   ├── MainActiviy.kt
```

local Package: Manages local database operations.

database Package: Provides access to the application database.

dao Package: Contains Data Access Object (DAO) classes that perform database operations.

UserDao.kt: DAO class for user data.

entity Package: Defines entity classes representing data in the database.

UserEntity.kt: Entity class representing user data.

pref Package: Manages application preferences.

AppPreferences.kt: Class holding application preferences.

repository Package: Contains repository classes managing local database operations.

LocalRepository.kt: Main repository class managing local database operations.

remote Package: Manages interaction with remote servers.

api Package: Defines the API service for communication with the remote server.

ApiService.kt: API service for remote server communication.

model Package: Contains classes representing data received from the remote server.

UserApiResponse.kt: Class representing user data received from the remote server.

repository Package: Contains repository classes managing remote server operations.

RemoteDataRepository.kt: The main repository class managing remote server operations. 
(If the technology or library used is compatible with sync processes, a more specific 
expression can be used under this title, such as “Remote Repository.”)

NetworkBoundResource.kt: Helper class managing network-bound resource handling.

repository Package: Manages general data operations for the application.

DataRepository.kt: Main repository class combining access to local and remote data sources.

#### di Package
This package manages dependency injection using Dagger Hilt. 
Module classes provide dependencies used throughout the application.

```
├── app
│   ├── kotlin+java
│   │   ├── com.raychal.boilerplate_mvvm_compose
│   │   │   ├── data
│   │   │   ├── di
│   │   │   │   ├── AppModule.kt
│   │   │   │   ├── DatabaseModule.kt
│   │   │   │   ├── NetworkModule.kt
│   │   │   ├── model
│   │   │   ├── ui
│   │   │   ├── util
│   │   │   ├── MainActiviy.kt
```

AppModule.kt: Provides general dependencies at the application level.

DatabaseModule.kt: Manages database dependencies.

NetworkModule.kt: Provides dependencies for network connectivity.

#### ui Package
This package is responsible for the user interface components of the application.
It has been updated to include three new sub-packages: main, detail, and userProfile.

```
├── app
│   ├── kotlin+java
│   │   ├── com.raychal.boilerplate_mvvm_compose
│   │   │   ├── data
│   │   │   ├── di
│   │   │   ├── model
│   │   │   ├── ui
│   │   │   │   ├── component
│   │   │   │   ├── main
│   │   │   │   │    ├── MainScreen.kt
│   │   │   │   │    ├── MainViewModel.kt
│   │   │   │   ├── theme
│   │   │   ├── util
│   │   │   ├── MainActiviy.kt
```

main Package: Manages the main screen of the application.

MainScreen.kt: Class managing the main screen's logic and appearance.

MainViewModel.kt: ViewModel class for the main screen.

component Package: Manages the component for the other screen.

theme Package: Manages theme like color, font, etc of the application.

#### util Package
This package contains utility classes used throughout the application.

```
├── app
│   ├── kotlin+java
│   │   ├── com.raychal.boilerplate_mvvm_compose
│   │   │   ├── data
│   │   │   ├── di
│   │   │   ├── model
│   │   │   ├── ui
│   │   │   ├── util
│   │   │   │   ├── DateUtil.kt
│   │   │   ├── MainActiviy.kt
```

DateUtil.kt: Utility class for date and time operations.

#### model Package
This package contains data models used throughout the application.

```
├── app
│   ├── kotlin+java
│   │   ├── com.raychal.boilerplate_mvvm_compose
│   │   │   ├── data
│   │   │   ├── di
│   │   │   ├── model
│   │   │   │   ├── User.kt
│   │   │   ├── ui
│   │   │   ├── util
│   │   │   ├── MainActiviy.kt
```

User.kt: Base user data model.