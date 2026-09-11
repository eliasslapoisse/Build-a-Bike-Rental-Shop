# Bike Rental Shop

A terminal-based bike rental application that lets customers rent and return bikes from a PostgreSQL database.

## Overview

This project simulates a small bike shop workflow:

- View available bikes by type and size.
- Rent a bike by entering a phone number and customer name.
- Automatically create a customer record when needed.
- Record the rental and mark the bike as unavailable.
- Return a bike and make it available again.

The application is implemented as a Bash script and uses a PostgreSQL database for persistent data storage.

## Project Files

- `bike-shop.sh` - interactive rental shop menu
- `bikes.sql` - database schema and seed data

## Prerequisites

Before running the project, make sure you have:

- PostgreSQL installed and running
- `psql` available on your system
- Bash available
- A PostgreSQL user named `freecodecamp` with access to the `bikes` database

## Setup

1. Open a terminal in the project folder.
2. Import the database schema and sample data:

   ```bash
   psql -U freecodecamp -d postgres -f bikes.sql
   ```

   This script creates the `bikes` database, defines the tables, and inserts starter inventory.

3. Start the shop application:

   ```bash
   bash bike-shop.sh
   ```

## How It Works

When the program starts, it shows a menu with three options:

1. Rent a bike
2. Return a bike
3. Exit

### Renting a bike

- The app lists all currently available bikes.
- You choose a bike number.
- The program asks for the customer's phone number.
- If the customer is not already in the database, it prompts for a name and creates a record.
- The rental is saved to the `rentals` table and the bike status is updated to unavailable.

### Returning a bike

- Enter the customer's phone number.
- The app shows that customer's active rentals.
- Select the bike to return.
- The rental is updated with a return date and the bike becomes available again.

## Database Structure

The database includes three main tables:

- `bikes` - bike inventory and availability
- `customers` - customer contact information
- `rentals` - rental history and return dates

## Example Usage

```text
~~~~~ Bike Rental Shop ~~~~~

How may I help you?

1. Rent a bike
2. Return a bike
3. Exit
```

You can then follow the interactive prompts to complete a rental or return.

## Notes

- The app is designed for a local PostgreSQL environment.
- If the database is not set up yet, run the SQL import before launching the script.
- The sample data includes several bikes and example customers for testing.

## License

This project is a small database practice application and is intended for learning and local development use.

