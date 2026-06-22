========================================================================
BLUE LAGOON HOTEL RESERVATION SYSTEM - DEPLOYMENT & OPERATION GUIDE
========================================================================

Course Code: BVI1234
Course Name: Technology System Programming II
Semester:    2025/26-SEM II

------------------------------------------------------------------------
1. SYSTEM OVERVIEW
------------------------------------------------------------------------
The Blue Lagoon Hotel Reservation System is a comprehensive, desktop-based 
management application engineered in Python 3. Utilizing the Tkinter 
graphical user interface framework and powered by an SQLite3 database engine, 
the system handles user authentication, live interactive room matrices 
(supporting Standard & Deluxe grids), dynamic booking timelines, automated 
room-service tick-box check invoicing, and transactional system event tracking.

------------------------------------------------------------------------
2. SYSTEM REQUIREMENTS & DEPENDENCIES
------------------------------------------------------------------------
The core framework leverages robust built-in Python standard library modules 
(tkinter, sqlite3, csv, os, datetime). However, to execute the program 
successfully, you must install the following external libraries which are not 
included in Python's standard library distributions:

Mandatory Libraries to Install:
  - tkcalendar (Required for the interactive DateEntry calendar widgets)
  - Pillow     (Required for processing and rendering the system logo images)

To configure your system environment, open your terminal or command prompt 
and run the installation command below:
  pip install tkcalendar Pillow

------------------------------------------------------------------------
3. DATABASE ARCHITECTURE & AUTO-INITIALIZATION
------------------------------------------------------------------------
- Database Framework: SQLite 3
- Data File Name:    hotel.db

NOTE TO EVALUATOR / LECTURER:
You do not need to pre-configure, migrate, or manually provision an external 
database file. The code is entirely self-sufficient. 

Upon first execution, the application script will automatically:
  1. Detect the existence of 'hotel.db' within the root project folder.
  2. If the database file is missing, it dynamically generates the schemas:
     - 'users'    (Stores application access control data profiles)
     - 'bookings' (Tracks operational check-ins, totals, and stay statuses)
  3. Seamlessly triggers a secure database fallback routine to safely run schema 
     upgrades and automatically seeds the default administrator profile.

------------------------------------------------------------------------
4. HOW TO RUN THE APPLICATION
------------------------------------------------------------------------
1. Verify that 'tkcalendar' and 'Pillow' are successfully installed via pip.
2. Verify that the file 'code project programing hotel reservation system.py' 
   is saved inside your working folder directory.
3. Open your Terminal (macOS/Linux) or Command Prompt (Windows).
4. Change your directory path to your project folder location and run:
   python "code project programing hotel reservation system.py"

------------------------------------------------------------------------
5. DEFAULT AUTHENTICATION SECURITY CREDENTIALS
------------------------------------------------------------------------
To pass the system security gate login panel on your initial launch, 
please input the following pre-configured user credentials:

  - Username: admin
  - Password: admin123

------------------------------------------------------------------------
6. KEY SYSTEM FUNCTIONALITIES TO EVALUATE
------------------------------------------------------------------------
- Credential Security Authentication: Validates runtime entry attempts directly 
  against real-time records in the local SQLite table.
- Notebook Room Grids: Displays clean color-coded room status layouts (Green 
  for Available, Red for Occupied) for Standard and Deluxe classes.
- Dynamic Invoice Form Calculations: Automatically tallies absolute stay costs 
  plus selected check-box item add-ons (Breakfast, WiFi, Extra Bed) along with 
  calculated room service taxes.
- Output File Handlers: Streamwrites clean text invoice receipts (`invoice_*.txt`) 
  upon guest check-out and appends archival records to a local master log file 
  (`booking_history.csv`).
========================================================================
