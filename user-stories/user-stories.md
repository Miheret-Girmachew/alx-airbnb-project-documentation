# User Stories for Airbnb Clone Backend

This file contains user stories that capture the core interactions and functionalities of the Airbnb Clone backend, derived from the use case diagram and feature specifications.

---

## User Management

1.  **As a potential user (Guest/Host), I want to be able to register a new account using my email and a password so that I can access the platform's features.**
    *   *Acceptance Criteria (Examples):*
        *   System accepts first name, last name, email, password, and role (guest/host).
        *   Email uniqueness is validated.
        *   Password meets security complexity requirements.
        *   A confirmation email is sent upon successful registration.

2.  **As a registered user (Guest/Host/Admin), I want to be able to log in securely using my email and password so that I can access my dashboard and personalized functionalities.**
    *   *Acceptance Criteria (Examples):*
        *   System validates credentials.
        *   Upon successful login, a JWT is issued.
        *   Appropriate error message for failed login attempts.

3.  **As a registered user (Guest/Host), I want to be able to update my profile information (like name, phone number, profile picture) so that my details are current and I can personalize my presence on the platform.**

---

## Property Listings Management (Host)

4.  **As a Host, I want to be able to create a new property listing by providing details like title, description, location, price, amenities, and photos so that I can make my property available for bookings.**
    *   *Acceptance Criteria (Examples):*
        *   All mandatory fields for a property are captured.
        *   Multiple images can be uploaded for a listing.
        *   The new listing is associated with my host account.

5.  **As a Host, I want to be able to edit my existing property listings so that I can update information such as price, availability, or amenities to keep my listing accurate.**

---

## Search & Booking (Guest)

6.  **As a Guest, I want to be able to search for properties by location, dates, and number of guests so that I can find suitable accommodations for my trip.**
    *   *Acceptance Criteria (Examples):*
        *   Search results display relevant properties.
        *   Results can be paginated.

7.  **As a Guest, I want to be able to filter search results based on price range and amenities so that I can narrow down my choices to properties that meet my specific needs and budget.**

8.  **As a Guest, I want to be able to view detailed information about a property, including photos, full description, amenities, and reviews, so that I can make an informed decision before booking.**

9.  **As a Guest, I want to be able to book an available property for specific dates so that I can secure my accommodation.**
    *   *Acceptance Criteria (Examples):*
        *   System checks for property availability for the selected dates.
        *   Total price is calculated and displayed.
        *   Booking status is initially set to 'pending' or moves to payment.

---

## Payment (Guest)

10. **As a Guest, I want to be able to securely make a payment for my booking using a supported payment method (e.g., credit card) so that my booking can be confirmed.**
    *   *Acceptance Criteria (Examples):*
        *   Integration with a payment gateway.
        *   Secure handling of payment information.
        *   Booking status updated to 'confirmed' upon successful payment.

---

## Reviews (Guest & Host)

11. **As a Guest, I want to be able to leave a review and rating for a property I have stayed at so that I can share my experience with other potential guests and provide feedback to the host.**
    *   *Acceptance Criteria (Examples):*
        *   Review can only be submitted for a completed booking.
        *   Rating is within the defined scale (e.g., 1-5).

12. **As a Host, I want to be able to respond to reviews left by guests for my properties so that I can acknowledge feedback and engage with my guests.**

---

## Admin Functionality

13. **As an Admin, I want to be able to manage user accounts (view, activate, deactivate) so that I can maintain the integrity and security of the platform's user base.**

14. **As an Admin, I want to be able to manage property listings (view, approve, remove) so that I can ensure the quality and appropriateness of content on the platform.**

---