# House Rental Platform

## Overview

The House Rental Platform provides a streamlined solution for connecting property owners with potential tenants. This platform enables property listings with detailed information, advanced search capabilities, user authentication, and secure messaging between owners and renters.

## Features

- **User Authentication**
  - Secure registration and login
  - Different user roles (Property Owner, Renter, Admin)
  - Profile management

- **Property Management**
  - Create, edit, and delete property listings
  - Upload multiple property images
  - Specify property details (bedrooms, bathrooms, amenities, etc.)
  - Set rental prices and availability

- **Search & Filter**
  - Advanced property search by location, price range, property type
  - Filter by amenities, size, and availability
  - Sort results by relevance, price, or date listed

- **Booking System**
  - Request property viewings
  - Schedule appointments
  - Manage booking status

- **Reviews & Ratings**
  - Leave reviews for properties
  - Rate property owners
  - View aggregated ratings

- **Messaging**
  - In-app communication between owners and renters
  - Notification system for new messages

- **Admin Dashboard**
  - User management
  - Property verification
  - Content moderation

## Tech Stack

- **Frontend**
  - React.js
  - Redux for state management
  - Material-UI components
  - Responsive design
  
- **Backend**
  - Node.js & Express
  - MongoDB database
  - Mongoose ODM
  - JWT authentication
  
- **Other Technologies**
  - AWS S3 for image storage
  - Google Maps API for location services
  - Stripe for payment processing

## Installation

### Prerequisites
- Node.js (v14 or higher)
- MongoDB
- npm or yarn

### Setup Instructions

1. Clone the repository:
   ```
   git clone https://github.com/ParthA164/House-Rental-Platform.git
   cd House-Rental-Platform
   ```

2. Install dependencies for both frontend and backend:
   ```
   # Install backend dependencies
   npm install
   
   # Install frontend dependencies
   cd client
   npm install
   cd ..
   ```

3. Create a `.env` file in the root directory with the following variables:
   ```
   PORT=5000
   MONGODB_URI=your_mongodb_connection_string
   JWT_SECRET=your_jwt_secret
   AWS_ACCESS_KEY=your_aws_access_key
   AWS_SECRET_KEY=your_aws_secret_key
   AWS_BUCKET_NAME=your_s3_bucket_name
   GOOGLE_MAPS_API_KEY=your_google_maps_api_key
   STRIPE_SECRET_KEY=your_stripe_secret_key
   ```

4. Start the development servers:
   ```
   # Run backend and frontend concurrently
   npm run dev
   
   # Or run separately
   npm run server  # Start backend server
   npm run client  # Start frontend server
   ```

## API Endpoints

### Authentication
- `POST /api/auth/register` - Register a new user
- `POST /api/auth/login` - User login
- `GET /api/auth/profile` - Get user profile
- `PUT /api/auth/profile` - Update user profile

### Properties
- `GET /api/properties` - Get all properties
- `GET /api/properties/:id` - Get property by ID
- `POST /api/properties` - Create a new property listing
- `PUT /api/properties/:id` - Update a property
- `DELETE /api/properties/:id` - Delete a property
- `POST /api/properties/:id/images` - Upload property images

### Bookings
- `GET /api/bookings` - Get user's bookings
- `POST /api/bookings` - Create a new booking
- `PUT /api/bookings/:id` - Update booking status
- `DELETE /api/bookings/:id` - Cancel a booking

### Reviews
- `GET /api/properties/:id/reviews` - Get reviews for a property
- `POST /api/properties/:id/reviews` - Create a review
- `PUT /api/reviews/:id` - Update a review
- `DELETE /api/reviews/:id` - Delete a review

### Messages
- `GET /api/messages` - Get user messages
- `POST /api/messages` - Send a message
- `PUT /api/messages/:id` - Mark message as read

## Folder Structure

```
House-Rental-Platform/
├── client/                    # Frontend React application
│   ├── public/                # Public assets
│   ├── src/                   # React source files
│   │   ├── actions/           # Redux actions
│   │   ├── components/        # React components
│   │   ├── pages/             # Page components
│   │   ├── reducers/          # Redux reducers
│   │   ├── utils/             # Utility functions
│   │   └── App.js             # Main App component
├── controllers/               # API route controllers
├── middleware/                # Express middleware
├── models/                    # MongoDB schemas
├── routes/                    # API routes
├── config/                    # Configuration files
├── utils/                     # Utility functions
├── server.js                  # Express server
└── package.json               # Project dependencies
```


## User Roles and Permissions

- **Property Owner**
  - Create and manage property listings
  - Respond to booking requests
  - Communicate with potential tenants

- **Renter**
  - Browse property listings
  - Send booking requests
  - Communicate with property owners
  - Leave reviews for properties

- **Admin**
  - Manage all users and properties
  - Verify property listings
  - Moderate reviews and messages

