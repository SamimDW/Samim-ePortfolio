---
title: "Enhancement Two: Algorithms"
--- 
**Artifact: Smart Inventory Android Application**

## Overview
This enhancement focuses on enhancing the search, filtering, and presentation of inventory data in the Smart Inventory Android application. The original version of the app was created in CS 360 and supported basic CRUD operations, but it lacked any meaningful search or filtering capabilities. Users had to scroll through a flat list to find items, which did not scale as the dataset grew.

## Existing Functionality
Before enhancement, the inventory screen displayed all items in a simple RecyclerView backed by a basic adapter. There was no algorithmic support for item discovery beyond manual scrolling. The data model was flat, lookups required full list scans, and the app did not provide category-based filtering or low-stock views. While functional, the design did not support efficient retrieval or responsive user interaction.

## Enhancement Description
In the enhanced version, I introduced structured search and filtering functionality to transform the inventory list into an interactive, algorithm-driven interface. I added real-time text search that matches against item fields such as name and category, along with dynamic filters that allow users to narrow results by category or low-stock state.

To support this, I restructured the flow of inventory data through the app. The full dataset remains the source of truth, while a derived, visible list is produced based on the active query and filter settings. Filters are applied first to reduce the dataset, followed by text search to minimize unnecessary work. Input normalization ensures consistent search behavior regardless of case or formatting. These changes replaced repeated, inefficient list scans with predictable and responsive transformations.

## Justification for Inclusion
I selected this artifact because the lack of search and filtering exposed a clear weakness in the original design. Addressing that weakness required more than UI changes. It required deliberate algorithmic thinking about how data should be structured, processed, and delivered to the user. This enhancement demonstrates tangible growth in my ability to design data-handling logic that supports scalability and performance.

The result is an inventory screen that behaves like a real system rather than a static list. Users can find items quickly, narrow results intelligently, and interact with the data in a way that reflects practical application design.

## Skills Demonstrated
- Search and filtering algorithms over structured collections  
- Input normalization and consistent query handling  
- Efficient list transformation and reduction strategies  
- Performance-aware UI updates using RecyclerView and DiffUtil  
- Separation of data processing logic from UI components  

## Course Outcomes Alignment
This enhancement aligns with the algorithms and data structures outcome by demonstrating the application of efficient data access and transformation techniques. It also supports the use of well-founded tools and practices by structuring search and filtering logic in a way that is maintainable and extensible. The enhancement meets the targeted outcome without requiring changes to the original coverage plan.

## Reflection
Enhancing the search and filtering system highlighted how closely algorithmic design is tied to user experience. I had to tune search behavior so results felt instant, avoid unnecessary database calls, and ensure filtering logic did not block the UI thread. Moving this responsibility into the ViewModel improved both performance and clarity.

I also encountered UI challenges while integrating the feature, including search bar styling, filter controls, and layout issues across light and dark modes. Resolving problems like shadow clipping, icon alignment, and vector scaling forced me to better understand Android’s layout system and Material Components. Overall, this enhancement made the application faster, more usable, and more professional, and it reinforced how algorithmic thinking directly improves real-world software.
