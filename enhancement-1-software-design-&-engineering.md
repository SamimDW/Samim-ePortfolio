---
title: "Enhancement One: Software Design & Engineering"
---
**Artifact: Smart Inventory Android Application**

## Overview
This enhancement focuses on redesigning the login and authentication system for the Smart Inventory Android application. The original version of this feature was created in CS 360 (Mobile Architecture and Programming). In CS 499, I enhanced it by restructuring the authentication flow to improve maintainability, clarity, and security.

## Existing Functionality
The original login system relied heavily on Activity-level logic and local storage. Authentication behavior and UI logic were tightly coupled, which made the feature harder to maintain and difficult to extend. Error handling and state management were also limited, and the overall structure did not scale well as the application grew.

## Enhancement Description
In the enhanced version, I redesigned the login system using a clear MVVM architecture. I introduced a dedicated `LoginViewModel` that exposes LiveData for loading, success, and error states. This allows the UI to react predictably to authentication events without directly handling business logic.

I also added an `AuthRepository` that centralizes all Firebase Authentication and Firestore access. This removed Firebase-specific logic from the Activity and ViewModel layers and established a clean separation of concerns. A simple SharedPreferences flag was retained to persist login state between app launches. Together, these changes transformed the login feature from a basic local solution into a structured and maintainable component.

## Justification for Inclusion
I selected this artifact because authentication sits at the boundary between the user and the application’s data. It is a critical area for demonstrating sound software engineering decisions. This enhancement shows my ability to design secure, testable, and extensible systems rather than focusing only on user interface behavior.

The improved design demonstrates that I can manage asynchronous Firebase operations without blocking the UI, clearly separate responsibilities across layers, and build features that can adapt to future changes, such as swapping authentication providers or expanding user data handling.

## Skills Demonstrated
- MVVM architecture and separation of concerns  
- Repository pattern for data and authentication logic  
- Lifecycle-aware state management using LiveData  
- Secure authentication design using Firebase Authentication  
- Maintainable and extensible Android application structure  

## Course Outcomes Alignment
This enhancement supports the course outcomes identified in Module One. It addresses software design and engineering through the application of MVVM and the repository pattern. It supports algorithmic and structural thinking by improving how authentication state flows through the app using lifecycle-aware components instead of direct callbacks. It also contributes to the database outcome through the use of Firebase Authentication and Firestore for user identity and data mapping. Based on these results, no changes were required to my original outcome coverage plan.

## Reflection
Enhancing the login feature reinforced how quickly an application becomes difficult to manage when its architecture is weak. Moving Firebase and Firestore logic out of the Activity and then out of the ViewModel exposed several design flaws in the original implementation, including duplicated logic, tight coupling, and unclear error handling.

The main challenge was restructuring the code without changing the user-facing behavior or breaking other parts of the app. Addressing this required careful responsibility boundaries and well-defined interfaces between layers. This process strengthened my understanding of Android architecture and showed me how to evolve a simple feature into a portfolio-ready component that reflects real-world development practices.
