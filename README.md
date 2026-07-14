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
4. **Database Operations**: If valid, `app.py` calls functions in `database.py` which execute the corresponding query (Insert, Find, Update, Delete) against the MongoDB cluster.

   The MongoDB connection implementation in `database.py` was adapted using guidance from the following Stack Overflow discussion:
   https://stackoverflow.com/questions/18650890/keeping-open-a-mongodb-database-connection

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

The API endpoint for fetching a member by their ID was implemented with guidance from the following ChatGPT conversation:
https://chatgpt.com/c/6a54934f-9d4c-83ee-aaad-01098504e231

## Testing

The project includes unit tests for key CRUD functions and validation, as well as an integration test to ensure the backend routes are working correctly.

To run the tests, navigate to the `backend` folder and run:

```bash
python -m pytest test_app.py
```

The CSV export functionality and CORS configuration were implemented with assistance from the following ChatGPT conversation:
https://chatgpt.com/c/6a549252-a6e4-83ee-9de0-3f24bb31d35f
# Project Deployment

## Cloud Infrastructure & Live Site

- **Google Cloud Console (VM Instances):** [View Instances](https://console.cloud.google.com/compute/instances?authuser=1&facet_url=https:%2F%2Fcloud.google.com&project=project-c3dae712-2b9e-4569-b9a)
- **Live Site:** [http://136.66.121.44/](http://136.66.121.44/)
- 
## AI Usage & My Contributions

Claude AI was used to generate the basic boilerplate code and basic CRUD structure for this project and i modified the code according to my project and requirements.

However, I personally wrote and modified several core logic components, including:
- The comprehensive form data validation logic (`app.py`)
- The CSV export functionality using Python's `io` and `csv` modules (`app.py`)
- The MongoDB connection implementation in `database.py`, adapted using guidance from a Stack Overflow discussion
- The advanced `$or` and `$regex` search queries for MongoDB (`database.py`)
- The single-query dashboard aggregation logic (`database.py`)
- The DOM manipulation loops and browser-side sorting functions (`script.js`)

The Claude AI conversation used during development is available here:
https://claude.ai/share/7ebda95d-13a5-4a4a-a421-daa0a51af476
