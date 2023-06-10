SCHIELD Documentation
Introduction

SCHIELD is a web application project developed for the Schield Center. It aims to provide information and resources to students, parents, and the community. This documentation provides an overview of the project's structure, components, and functionality.
Table of Contents

    Prerequisites
    Installation
    Configuration
    Folder Structure
    Components
    Routes
    Database
    Authentication
    Build and Deployment

Prerequisites

Before running the project, make sure you have the following prerequisites installed:

    Node.js
    NPM (Node Package Manager)
    MongoDB

Installation

To install the project, follow these steps:

    Clone the project repository from GitHub.
    Navigate to the project directory.
    Run the command npm install to install the dependencies.

Configuration

The project requires some configuration to function properly. Make sure to set the following environment variables:

    DATABASE_URL: The URL of the MongoDB database.
    NUXT_SECRET: Secret key for Nuxt.js.
    GITHUB_CLIENT_ID: Client ID for GitHub authentication.
    GITHUB_CLIENT_SECRET: Client secret for GitHub authentication.
    GOOGLE_CLIENT_ID: Client ID for Google authentication.
    GOOGLE_CLIENT_SECRET: Client secret for Google authentication.
    FACEBOOK_CLIENT_ID: Client ID for Facebook authentication.
    FACEBOOK_CLIENT_SECRET: Client secret for Facebook authentication.
    ORIGIN: Origin for authentication.

Folder Structure

The project follows a typical folder structure:

    /components: Contains reusable Vue.js components.
    /pages: Contains Vue.js pages for different routes.
    /static: Contains static files such as images and CSS.
    /plugins: Contains custom plugins for the project.
    /prisma: Contains Prisma schema and configuration.

Components

The project includes various components for building the user interface. Some notable components are:

    Navbar: A navigation bar component for the top of the page.
    Footer: A footer component for the bottom of the page.
    PostCard: A card component to display a post with title, image, and description.

Routes

The project defines the following routes:

    /pages/protected/Donate.vue: A protected page for making donations.
    /pages/Gallery.vue: A page for displaying image gallery.
    /pages/Home.vue: The home page of the website.
    /pages/index.vue: The index page.
    /pages/News.vue: A page for displaying news articles.
    /pages/Sponsor-program.vue: A page for the sponsorship program.
    /pages/Sponsor.vue: A page for sponsors.

Database

The project uses MongoDB as the database. The database configuration is defined in the db section of the datasource in the schema.prisma file.
User Model

The User model represents user data and includes the following fields:

    id: Unique identifier for the user.
    authentication_key: Authentication key for the user.
    email: User's email (optional and unique).
    id_: User's ID.
    password: User's password.
    username: User's username.

Schield Friends Model

The schield_friends model represents data for Schield Friends and includes the following fields:

    id: Unique identifier for Schield Friend.
    email: Email of the Schield Friend.
    name: Name of the Schield Friend.
    password: Password for the Schield Friend.

Authentication

The project includes authentication functionality using various providers such as GitHub, Google, Facebook, and custom credentials. The authentication configuration is defined in the auth section of the Nuxt.js configuration.
Build and Deployment

To build and deploy the project, follow these steps:

    Run the command npm run build to build the project.
    Deploy the generated files to your preferred hosting platform or server.

That concludes the basic documentation for the SCHIELD project. You can further expand and customize it based on your project's specific requirements and additional details.
