# CHEMO-SAFE Frontend (React)

This folder will contain the React web frontend for CHEMO-SAFE. The web app will consume the Django REST API and provide an easy UI for teachers and lab technicians to upload CSVs, view summaries, and generate reports.

## Pages / Components

1. **Home / Dashboard**
   - Short project intro + upload button
   - Card widgets: Total equipment, Avg Temp, Avg Pressure, Risk Count
   - Recent uploads (history preview)

2. **Upload / Preview Component**
   - CSV file picker
   - 5-row preview before upload (client-side)
   - "Upload" button that sends file to /api/upload/

3. **TableView**
   - Paginated table of uploaded equipment rows
   - Search/filter by equipment type

4. **Charts**
   - Temperature distribution (histogram / line)
   - Pressure vs Flowrate scatter (correlation)
   - Equipment type pie chart
   - Burn-Risk Severity Index (BRSI) display (colored badges)

5. **History Page**
   - List of last 5 uploads with timestamps and quick link to view summary or download PDF report

6. **Auth**
   - Simple login form (username/password) to access upload & report generation

## Tech
- React (Create React App or Vite)
- Chart.js (react-chartjs-2)
- Axios for API calls
- Basic CSS (kept minimal for speed)

## Notes
This README is a plan for the frontend and will be updated as components are implemented.
