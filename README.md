# FlexFit Membership System

This is an Information System for managing gym memberships, built using an API architecture. 

## Architecture
As per the assignment requirements, the system is separated into two parts:
1. **Backend (API)**: A Python Flask server that connects to a MongoDB database. It serves JSON responses, **not** HTML templates.
2. **Frontend**: A vanilla HTML, CSS, and JavaScript interface that makes API calls to the backend using `fetch()`.

## Project Structure
```text
flexfit/
│
├── backend/
│   ├── app.py             # Flask API routes and data validation
│   ├── database.py        # MongoDB connection and queries
│   ├── test_app.py        # Unit and integration tests
│   └── requirements.txt   # Python dependencies
│
└── frontend/
    ├── index.html         # User Interface
    ├── style.css          # Styling
    └── script.js          # DOM manipulation and API calls
```

## Project Flow
1. **User Interaction**: The user enters data (e.g., adding a new gym member) or clicks a button (e.g., searching or sorting) on the `index.html` interface.
2. **Frontend Processing**: The `script.js` file handles the event. For browser-side actions like sorting, it instantly re-renders the DOM. For data operations, it sends a REST API `fetch` request to the backend.
3. **Backend Validation**: The Flask server in `app.py` receives the request and validates the input data against strict rules (checking email format, phone numbers, date logic).
4. **Database Operations**: If valid, `app.py` calls functions in `database.py` which executes the corresponding query (Insert, Find, Update, Delete) against the MongoDB cluster.
5. **Response & UI Update**: The backend returns a JSON response to the frontend. The `script.js` parses this JSON and dynamically updates the HTML tables and dashboard counts without reloading the web page.

## How to Run the Project

Since this project uses an API architecture, the frontend and backend must be run separately. **Do not try to view the website by opening the Flask server URL.**

### Step 1: Start the Backend API
1. Open a terminal and navigate to the `backend` folder.
2. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Flask server:
   ```bash
   python app.py
   ```
4. Leave this terminal running. The API will be hosted on `http://127.0.0.1:5000`.

### Step 2: Open the Frontend
1. Open the `frontend` folder.
2. Double-click **`index.html`** to open it directly in your web browser (or use a tool like VS Code Live Server).
3. The JavaScript will automatically connect to the Python backend API running in the background.

## Testing
The project includes unit tests for key CRUD functions and validation, as well as an integration test to ensure the backend routes are working correctly. 
To run the tests, navigate to the `backend` folder and run:
```bash
python -m pytest test_app.py
```

## AI Usage & Usman Contributions
Claude AI was used to generate the basic boilerplate code and basic CRUD structure for this project. 
However, I personally wrote and modified several core logic components, including:
- The comprehensive form data validation logic (`app.py`)
- The CSV export functionality using Python's `io` and `csv` modules (`app.py`)
- The advanced `$or` and `$regex` search queries for MongoDB (`database.py`)
- The single-query dashboard aggregation logic (`database.py`)
- The DOM manipulation loops and browser-side sorting functions (`script.js`)

You can view the AI generation chat log here: 
[Claude AI Chat Link](https://claude.ai/share/7ebda95d-13a5-4a4a-a421-daa0a51af476)
