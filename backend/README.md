# CHEMO-SAFE Backend (Django + DRF)

This folder will contain the Django REST API backend for CHEMO-SAFE, a hybrid safety dashboard for chemistry labs in schools and colleges.

The backend will accept equipment parameter CSV files, compute safety insights, and provide endpoints that both the Web (React) and Desktop (PyQt5) applications use.

---

## Planned API Endpoints

### 1. POST /api/upload/
Upload a CSV file containing equipment parameters:
- Equipment Name  
- Type  
- Flowrate  
- Pressure  
- Temperature  

The backend will:
- Parse the CSV with pandas  
- Calculate summary statistics  
- Compute safety metrics (BRSI and RHP)  
- Save the upload entry in SQLite (only last 5 kept)  
- Return an upload ID

---

### 2. GET /api/summary/<upload_id>/
Returns:
- Total equipment count  
- Average temperature, pressure, and flowrate  
- Type distribution  
- Burn-Risk Severity Index (BRSI) summary  
- Reaction Hazard Potential (RHP) summary  

---

### 3. GET /api/history/
Returns metadata and summaries for the last 5 processed CSV uploads.

---

### 4. GET /api/report/<upload_id>/
Generates a PDF containing:
- Summary tables  
- Safety metrics  
- Charts (temperature, pressure, type distribution)  
- Timestamp  
- Candidate (developer) name  

---

### 5. Authentication
The backend will use basic Django authentication (username + password) or token-based access for protected endpoints.

---

## Tech Used
- Django
- Django REST Framework
- Pandas
- SQLite (default Django database)
- ReportLab (PDF generation)
- Matplotlib (charts for PDF)
- Python requests (for PyQt5 desktop client)

---

This README is a working document and will be updated as the backend is developed.
