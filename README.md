# Laundry-application
### Video Demo: https://www.youtube.com/watch?v=B53FK71vneQ

### Description
Students often struggle to manage laundry due to busy schedules filled with classes, assignments, and other commitments. This project addresses the challenge by providing a simple and efficient online laundry service. The main goal is to save students time and reduce stress by streamlining the laundry process, allowing them to focus more on their studies and other priorities.

#Code commenting
Infro ntend folder, there is a subfolder called pages. This folder contains pages written using JavaScript and React, including AdminPart, AdminRegistration, CustomerPart, CustomerRegistration, Orders, and MainLayout.

index.js(AdminPart) : - The `AdminPart` component serves as the main interface for administrators of the online laundry service. It displays user-specific data fetched via React Query, including the admin's username and company name. The component allows admins to manage their profiles, including the ability to update profile images using file input. It features a logout functionality that clears authentication tokens and redirects users to the home page. Additionally, the component includes navigation elements, such as links to view orders and a Google Maps iframe for displaying location information. Styling is managed through an imported CSS file (`adminPart.css`), ensuring a cohesive and user-friendly interface for the admin role.

index.js(AdminRegistration) : The `AdminRegistration` component provides a registration form for administrators to sign up for the online laundry service. It handles user input through controlled components managed by the `useState` hook. The form includes fields for username, email, password, repeated password, company name, and address. Upon submission, the component validates the passwords and sends a registration request to the server via an API call using Axios. Successful registration stores the received authentication token in local storage and redirects the user to the admin profile page. Error handling is implemented to display appropriate messages for common issues, such as mismatched passwords or server errors. The component ensures a smooth registration process, enhancing the onboarding experience for new administrators.

 index.js(CustomerPart) : The CustomerPart component provides a UI for customers to place new laundry orders. It uses the useQuery hook to display user info (first and last names) and the useState hook to manage form data (address, tariff, and date) with default values. The useMutation hook handles order creation via the laundryApiHandler.createOrder API, redirecting users to the order page upon success. It also includes a logout function that clears the token from local storage and redirects to the home page, ensuring smooth form submission and navigation for a better customer experience.

index.js(CustomerRegistration) : The CustomerRegistration component provides a form for new customers to sign up for the laundry service, managing inputs with useState. It checks for an existing token on load, redirecting logged-in users to their profile. On form submission, it validates passwords and registers the user via Axios, storing the token in local storage and redirecting to the profile page. Error handling addresses issues like mismatched passwords and server errors. A logout function clears the token and redirects to the home page.

index.js(Orders) : he AdminOrders component lets admins manage orders, using useQuery to fetch data and distinguish admin from customer views. Admins can view and accept orders via the useMutation hook with the acceptOrder API call. Customers can view and place orders. It handles loading states and includes a logout function to clear the token and redirect to the home page. The UI shows order details like address, tariff, and dates for efficient management.


# Entities
User.java: This entity represents users within the online laundry service, implementing `UserDetails` from Spring Security for authentication. It includes fields like `id`, `userName`, `firstname`, `lastname`, `address`, `companyName`, `email`, `gender`, `password`, and `role`. The role determines user permissions, managed by `getAuthorities()` which assigns roles as `GrantedAuthority` objects. The class includes basic account status methods (`isAccountNonExpired`, `isAccountNonLocked`, `isCredentialsNonExpired`, `isEnabled`), all returning `true` for simplicity. The `getUsername()` method returns the email, aligning with Spring Security's expectations, while `getRealUsername()` provides the actual username.

Order.java: This entity represents laundry orders within the application. It includes fields such as `id`, `tariff`, `createdAt`, `updatedAt`, `customer`, `admin`, `address`, and `selectedDate`. The `id` is generated automatically using the `IDENTITY` strategy. Timestamps for order creation and updates are managed with Hibernate annotations (`@CreationTimestamp` and `@UpdateTimestamp`). The `tariff` field is an enumerated type indicating the selected pricing plan for the service. Relationships are established with the `User` entity, linking each order to a customer and optionally to an admin. The `address` and `selectedDate` fields store the order's delivery address and the date selected for the service, supporting efficient tracking and management of laundry orders.
 



# Prerequisites
To run this project, you will need:

IDEs: Visual Studio Code and IntelliJ IDEA, for frontend and backend development, respectively.
Node.js and npm: Ensure Node.js is installed on your system to use npm for managing frontend dependencies.
Installation and Setup
Clone the repository to your local machine.
Open the backend in IntelliJ IDEA:
Navigate to the api directory.
Press the green run button to start the backend server.
Set up the frontend in Visual Studio Code:
Open a terminal and navigate to the frontend directory.
Run npm install to install all required dependencies.
Once the installation is complete, start the application by executing npm start.
If the terminal outputs a success message, the application is running correctly.
Accessing the Application
Open your preferred web browser and go to localhost:3000.
If the application loads successfully, you have set up everything correctly and can now use the service.

## Installation

To install the project dependencies, run the following command:

```bash
# Install dependencies
npm install
\```

```bash
# for running application input in the terminal 
npm start

