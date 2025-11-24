# VITYARTHI-project
A modular Python CLI application simulating a flight booking system. It implements a user-centric Seat Selection Module that utilizes a Python Dictionary for O(1) status lookup and features JSON file persistence (FR16) to ensure seat availability is correctly saved and loaded across application sessions.



User-Centric Flight Seat Selection System




Console-Based Flight Reservation Simulator (Python)

Overview

The User-Centric Flight Seat Selection System is a modular Python Command-Line Interface (CLI) application designed to simulate the essential steps of an Indian domestic flight booking. The core goal is to enhance passenger satisfaction by allowing customers to choose their preferred seat (FR11).

The project demonstrates full system integration and mastery of core programming concepts, specifically Data Structures and File I/O for State Persistence.

1. System Architecture & Component Responsibilities

The system adheres to a modular design for clear separation of concerns.

Module A: Seat Selection, Visualization, and Persistence (My Core Focus)

This module manages the real-time seat status and persistence.

Purpose: To manage the seating data structure, provide the visual map (FR10), and ensure the seat status is saved across application runs (Persistence).

Key Data Structure: The 8x4 seating map (A1-H4) is managed using a Python Dictionary. This provides efficient O(1) time complexity for status lookup and conflict detection (FR7).

Persistence (FR16): Uses the Python built-in json module to save the dictionary state to a local file, seat_data.json, immediately after every successful booking.

Module B: Ticket Booking and Financial Flow (Friend's Contribution)

This module handles the customer journey and financial validation.

Purpose: To manage the user interaction flow, authenticate payments, and finalize the ticket issuance process.

2. Features and Logical Workflow

The application follows a strict, sequential workflow:

Customer Identification and Trip Planning.

Payment Simulation (Requires correct fee amount).

Seat Selection (Customer Choice): Module A is launched, displaying the seat map and capturing the user's desired seat (FR11).

Final Confirmation: The system validates the payment and updates the persistent seat_data.json file.

Ticket Issuance: Displays the final ticket details, including the confirmed Seat.

3. Technologies Used

Language: Python 3.x

Data Structure: Python Dictionary (for Seat Map management).

Core Modules: json (for persistence, FR16) and os.

Interface: Command Line Interface (CLI).

4. Setup and Execution

Prerequisites: Ensure Python 3.x is installed.

Download: Ensure all project files (maincode.py, seat_selector_dict.py) are placed in the same directory.

Execute: Open your system's Terminal and run the main file:

python maincode.py


5. Testing Instructions (CRITICAL for Validation)

The following scenarios validate the core functional requirements (FR6, FR7, FR16) of the Seat Selection Module:

Persistence Test (FR16): Book a seat (e.g., B3) and quit the application. Relaunch the app and attempt to book the same seat (B3). Expected Result: The system must display ">>> ERROR: Seat B3 is already booked!", confirming data loaded from seat_data.json.

Conflict Check (FR7): Select an available seat (C4) successfully. Immediately attempt to select C4 again in the same session. Expected Result: System displays ">>> ERROR: Seat C4 is already booked!".

Validation Check (FR6): Enter an invalid seat like Z9 or an out-of-range row like A5. Expected Result: System displays ">>> ERROR: Invalid seat number. Try A1, H4, etc." and re-prompts for input.
