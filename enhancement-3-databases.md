
**Artifact: Smart Inventory Android Application**

## Overview
This enhancement focuses on upgrading the data layer of the Smart Inventory Android application. The original version of the app, created in CS 360 (Mobile Architecture and Programming), used a local SQLite database to store users and inventory items. In CS 499, I replaced this local database with a cloud-based Firebase Firestore database, which fundamentally changed how data is stored, accessed, and synchronized across the application.

## Existing Functionality
Before the enhancement, all inventory and user data were stored locally using SQLite. While this approach worked for a single-device demo, it introduced clear limitations. Data was tied to one device, authentication and inventory data were loosely connected, and there was no server-side enforcement of access control. The database layer was also tightly coupled to the rest of the app, which made large-scale changes risky.

## Enhancement Description
In the enhanced version, I migrated the entire data layer to Firebase Firestore and linked inventory data to authenticated users. Instead of storing items in a shared local table, inventory data is now scoped to the user’s authenticated identity. This required redesigning the repository layer, updating ViewModels to handle asynchronous reads and writes, and ensuring the UI reacted correctly to real-time data updates.

The migration enabled cloud-based persistence, real-time synchronization, and a clear separation between the UI and the data source. It also laid the groundwork for enforcing access control through server-side rules rather than relying on client-side assumptions. These changes transformed the database layer from a local storage solution into a scalable, multi-device system.

## Justification for Inclusion
I included this artifact in my ePortfolio because the database upgrade demonstrates real-world software development skills rather than surface-level changes. Moving from SQLite to Firestore required architectural refactoring, careful handling of asynchronous operations, and coordination across multiple layers of the application. The enhancement shows that I can work with modern cloud databases, refactor existing systems safely, and design solutions that scale beyond a single device.

This upgrade also significantly improved the app's usability by enabling data persistence across devices and sessions. It created a foundation for future features such as shared inventories, user-specific settings, and more advanced inventory rules.

## Skills Demonstrated
- Cloud database design using Firebase Firestore  
- Repository-based data abstraction  
- User-scoped data modeling and access control  
- Asynchronous data handling and real-time updates  
- Refactoring and migration of an existing data layer  

## Course Outcomes Alignment
This enhancement supports the course outcomes identified in Module One. Designing and implementing a Firestore-backed solution required evaluating trade-offs between local and cloud storage, which aligns with algorithmic and design principles. The use of Firebase demonstrates the application of modern tools and techniques used in industry. The enhancement also required clear documentation and explanation of architectural decisions, reinforcing professional communication skills. Based on these results, no changes were needed to the original outcome coverage plan.

## Reflection
Refactoring the data layer reinforced the importance of strong separation of concerns and a clean architecture. Migrating to Firestore required rethinking how LiveData is updated, managing real-time listeners, and handling asynchronous operations without breaking the UI. I encountered issues such as crashes, missing listeners, stale UI states, and document ID handling, and resolving them improved my debugging skills in cloud-based systems.

The most important lesson from this enhancement was that architecture enables change. Because the ViewModel and repository layers were clearly defined, I was able to replace the underlying database without rewriting the entire application. This transition strengthened both my technical skills and my confidence in working with scalable, production-ready data systems.
