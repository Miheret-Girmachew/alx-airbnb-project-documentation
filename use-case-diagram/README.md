# Airbnb Clone Backend: Use Case Diagram

## 1. Objective

This document serves as an introduction to the Use Case diagram for the Airbnb Clone backend. The diagram visually represents the interactions between different types of users (actors) and the system for key functionalities. It helps in understanding the scope of the system from a user's perspective and outlines the primary services the backend will provide.

The actual Use Case diagram, created using Draw.io, is named `airbnb_clone_use_cases.png` and is located within this directory.

## 2. Actors

The primary actors interacting with the Airbnb Clone backend system are:

*   **Guest:** A user looking to browse properties, book stays, manage their bookings, make payments, and leave reviews.
*   **Host:** A user who owns properties and wishes to list them, manage listings, manage bookings for their properties, and respond to reviews.
*   **Admin:** A privileged user responsible for system administration, user management, content moderation, and overseeing operations.
*   **System:** (Implicit Actor) Represents automated processes or the system itself performing actions like sending notifications or processing scheduled tasks. Can also represent external systems like Payment Gateways or Email Services.

## 3. Key Use Cases

The diagram (`airbnb_clone_use_cases.png`) illustrates the following key use cases, grouped by actor or functionality:

### 3.1. General User / Guest & Host (Shared)

*   **Register Account:**
    *   Actors: Guest, Host
    *   Description: Allows new users to create an account, specifying if they are primarily a guest or host (role can often be flexible).
*   **Login to System:**
    *   Actors: Guest, Host, Admin
    *   Description: Authenticates users to access their respective dashboards and functionalities.
*   **Manage Profile:**
    *   Actors: Guest, Host, Admin
    *   Description: Allows users to view and update their personal information (e.g., name, contact, password, profile picture).
*   **Logout from System:**
    *   Actors: Guest, Host, Admin
    *   Description: Allows users to securely end their session.
*   **Search Properties:**
    *   Actors: Guest (primarily), Host (can also search)
    *   Description: Enables users to search for available properties based on location, dates, number of guests, etc.
*   **Filter Search Results:**
    *   Actors: Guest (primarily)
    *   Description: Allows users to refine search results using filters like price range, amenities.
*   **View Property Details:**
    *   Actors: Guest, Host
    *   Description: Allows users to see detailed information about a specific property.
*   **View Reviews:**
    *   Actors: Guest, Host
    *   Description: Allows users to read reviews for properties.
*   **Send/Receive Messages:**
    *   Actors: Guest, Host
    *   Description: Facilitates communication between users (e.g., guest to host regarding a booking).
*   **Receive Notifications:**
    *   Actors: Guest, Host, Admin
    *   Description: Users receive system notifications (email/in-app) for important events.

### 3.2. Guest Specific Use Cases

*   **Book Property:**
    *   Actor: Guest
    *   Description: Allows a guest to initiate and complete the booking process for a selected property and dates.
        *   *Includes:* Select Dates, Confirm Property Availability
*   **Make Payment:**
    *   Actor: Guest
    *   Description: Allows a guest to securely pay for their booking.
        *   *Extends/Includes:* Book Property
        *   Interacts with: Payment Gateway (External System Actor)
*   **Manage My Bookings (Guest):**
    *   Actor: Guest
    *   Description: Allows guests to view their current, past, and upcoming bookings.
*   **Cancel Booking (Guest):**
    *   Actor: Guest
    *   Description: Allows a guest to cancel a confirmed or pending booking (subject to policy).
*   **Write Review:**
    *   Actor: Guest
    *   Description: Allows a guest to submit a review and rating for a property after their stay.
        *   *Includes:* Link Review to Booking

### 3.3. Host Specific Use Cases

*   **Create Property Listing:**
    *   Actor: Host
    *   Description: Enables a host to add a new property to the platform with all necessary details and images.
        *   *Includes:* Upload Property Images (interacts with File Storage System)
*   **Manage My Listings:**
    *   Actor: Host
    *   Description: Allows hosts to view, edit, or delete their property listings.
        *   *Includes:* Update Listing Details, Update Availability, Remove Listing
*   **Manage Bookings (Host):**
    *   Actor: Host
    *   Description: Allows hosts to view and manage incoming booking requests for their properties.
        *   *Includes:* Confirm Booking, Decline Booking
*   **Cancel Booking (Host):**
    *   Actor: Host
    *   Description: Allows a host to cancel a booking (under specific conditions).
*   **Respond to Review:**
    *   Actor: Host
    *   Description: Allows a host to post a public response to a guest's review.
*   **Manage Payouts (View):**
    *   Actor: Host
    *   Description: Allows hosts to view their earnings and payout history.

### 3.4. Admin Specific Use Cases

*   **Manage Users (Admin):**
    *   Actor: Admin
    *   Description: Allows administrators to view, search, and manage user accounts (e.g., activate/deactivate, change roles, resolve issues).
*   **Manage Listings (Admin):**
    *   Actor: Admin
    *   Description: Allows administrators to oversee all property listings, approve/reject new listings, and moderate content.
*   **Manage Bookings (Admin):**
    *   Actor: Admin
    *   Description: Provides administrators with an overview of all bookings, allowing them to intervene if necessary.
*   **Manage Payments (Admin):**
    *   Actor: Admin
    *   Description: Allows administrators to monitor transactions, manage refunds (if applicable), and handle payment disputes.
*   **Moderate Reviews (Admin):**
    *   Actor: Admin
    *   Description: Allows administrators to review and remove inappropriate or fraudulent reviews.
*   **View System Analytics/Reports (Admin):**
    *   Actor: Admin
    *   Description: Allows administrators to access reports on platform usage, bookings, revenue, etc.

### 3.5. System Interactions (Implicit)

*   **Send Email Notifications:**
    *   Actor: System (interacts with Email Service)
    *   Description: Automated sending of emails for various events.
*   **Process Payments:**
    *   Actor: System (interacts with Payment Gateway)
    *   Description: Backend logic to communicate with payment gateways.
*   **Store Files:**
    *   Actor: System (interacts with File Storage Service, e.g., AWS S3)
    *   Description: Handling uploads and storage of images.

## 4. Diagram Conventions

The `airbnb_clone_use_cases.png` diagram utilizes standard UML Use Case notation:
*   **Actors:** Represented by stick figures.
*   **Use Cases:** Represented by ovals.
*   **Associations:** Lines connecting actors to use cases they interact with.
*   **`<<include>>` Relationship:** Indicates that one use case incorporates the behavior of another (base use case depends on the included one).
*   **`<<extend>>` Relationship:** Indicates that one use case provides optional additional behavior for another (extending use case is optional for the base one).

