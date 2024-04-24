# Seek
Seek - Take Home Assignment

## Description
This project has used some base classes which were developed by me. Which can be extended and develop on top of that. Supports MVVM-C Architecture and UI binding is powered by [RxSwift](https://github.com/ReactiveX/RxSwift). The main purpose of this base classes is to develop efficient architecture for the applications and to reduce as much as development time.

## Tasks
My main forcus was on login functionality and the dashboard view with paginated list. Some of the tasks were not completed due to time constraints and my other commitments. Hence I didn't try to use the given backend. Instead I developed mock services.

Use this link to see a demo [Screen recording](https://drive.google.com/file/d/1VFBT7nbkPbMcQLdiXqaD67fzMr3dA7Hr/view?usp=sharing)

#### Login functionality
- [x] Add a login screen to authenticate a user with the application - Needed Input fields: Username & Password and a Button
- [x] The logged-in session needs to be stored - The form of the Session will be a JWT-Token
- [x] Add Logout capabilities
- [x] Facebook login

#### Dashboard
- [x] Job list with pagination
- [x] Job search capabilities - patialy implemented (With mock data cannot see search results are updating) 
- [x] Job details screen
- [ ] In Job detail screen, option to apply, with an indicator that indicated if already applied

#### Profile
- [x] Candidate client API was developed for this feature
- [ ] Profile details, Edit profile attributes (for example name, years of experience)
- [ ] Tab for `Show My Applications`, which should show all the current authenticated users applications. Once tapped it will navigate to Job details screen
- [ ] Password Change Capabilities

#### Unit Tests
- [x] Unit tests were added for SigninVM

#### Additional Demo - To demonstrate actual API calling with pagination and search functionality
- [x] I hava added a previously developed Demo dashboard with some functionalities
- [x] In this example it consums public News APIs
- [x] To enable this functionality, go to `/Views/Coordinators/MainCoordinator/Main_Coordinator.swift` and see line #75
- [x] Use this link to see a demo [Screen recording](https://drive.google.com/file/d/1MYjdav2e5nzdclOgJy44Rsyerqh83xcA/view?usp=sharing)

## Architectural components
- [x] Base MVVM-Coodinator architecture.
- [x] Base Table view controller & Base Collection view controller that adopts to MVVM architecture.
- [x] Base Table View Controller and Base Collection View Controller supports,
  - API Pagination,
  - Search,
  - Multiple list views & grid views in one screen,
  - Can hanlde the UI when the table view is empty,
  - Static data loading,
  - Section headers (Dynemic and custom).
  - Can eliminate all the boilerplate code and you only have to customise your rendering UITableViewCell/UICollectionViewCell (which extends from BaseTVCell/BaseCVCell) with the data Model (which extends from BaseModel).

## Reusable components
- [x] Facebook SignIn - Social sign in capability with these protocols and there default implementations. Adopts to Base MVVM architecture.
- [x] NCTabView
  - Tab view that has used in News Example Dashboard.
  - Has three tab selection styles (Bigger Text when highlighted, Underlined when highlighted, Circle background when highlighted).
  - Extendable to have more styles.

## Requirements:
- [x] Xcode Version 10.3 (Developed on Xcode 14.3.1)
- [x] Swift 5
- [x] iOS Version 11.0 or above
- [x] Password to unzip the project. I have shared this with the email

 ## Running Xcode Project and General changes
 - Unzip the Nadeesha-Seek-Submission.zip to extract the xcode project
 - Open the project(.xcworkspace file) in Xcode
 - Now you can simply run the project in simulator
 - Do a pod install if necessary

## Test accounts to Sign In to the app

#### Normal sign in
- Username: You can enter a valid mobile number or en email as the username field
- Password: Password could be anything.
- Once a valid username and a password is entered the 'Sign In' button will be enabled.
- Since I'm using a Mock API client, it will bypass the actual API call and return with Mock result.

#### Use this test account to Sign in with Facebook
 - E-mail: "johndoe20220518@gmail.com"
 - Password: "johnDoe20220518."
 - In case if a sequrity check pops up, you might want to login to the gmail first. For 2-step auth, you can use '7108 3716', '8120 1758' or '5705 5746'. Password would be same. 

## Project Architecture and Related details

Specifics                 | Details
--------------------------|------------------------------------------------------------------------
| Architecture - MVVM-C   | Used RxSwift to bind View and ViewModel. Coodinators are responsible for navigation flow.
| Base classes            | `Common/Components`, `Common/Architectural` folders - All the base & generic classes & Re-usable common components reside within this folder. All the other classes are inherited from the classes which are within this folders
| Networking - Alamofire  | `Network` folders<br/>- `Common\Network\HTTPService.swift` - Actual network reqeust handling<br/>- `Common\Network\HTTPMockService.swift` - mock network reqeust handling<br/>- `Network\APIProtocols` folder - API definitions that the App will be consume. <br/>
| Models                  | `Models` folder - All the models used by the app reside within this folder. Almost all the models which are passed by the Network Services are extending `BaseModel` class
| Views                   | `Views` folder - All the UI elements reside within this folder. (Storyboards, ViewControllers, ViewModels, App TableView Cells)
| App Config                 | Used a simple Singleton class to keep the configuration parameters. Most of the values that are used by AppConfig are stored in `Configuration.plist`


## Main Dependancies

Name                          | purpose
--------------------------    | -----------------------------------------------------
[Alamofire](https://github.com/Alamofire/Alamofire) | Network library
[ObjectMapper](https://github.com/tristanhimmelman/ObjectMapper) | Mapping JSON objects into Swift classes
[KeychainSwift](https://github.com/evgenyneu/keychain-swift) | Wraper to store data securely in Keychain.
[RxCocoa](https://github.com/ReactiveX/RxSwift) | This is a Swift version of Rx.
[FBSDKLoginKit](https://developers.facebook.com/docs/facebook-login/ios/) | Facebook Sign in functionality

## License

Copyright © 2024 Nadeesha Chandrapala. All rights reserved.
