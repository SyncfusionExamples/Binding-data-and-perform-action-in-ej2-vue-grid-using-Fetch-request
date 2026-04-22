# Binding data and perform actions in EJ2 Vue Grid (Fetch request)

## Repository Description
This repository is a small sample showing how a Vue 3 front-end (Vite) uses Syncfusion EJ2 Vue Grid to bind data via Fetch requests to an ASP.NET Core backend and perform basic CRUD operations.

## Overview
- `FetchProject/fetchproject.client` — Vue 3 client using `@syncfusion/ej2-vue-grids` and `@syncfusion/ej2-vue-buttons`.
- `FetchProject/FetchProject.Server` — ASP.NET Core (net8.0) server exposing simple endpoints and an in-memory `OrdersDetails` dataset.
- The front-end `src/App.vue` uses `Fetch` to call backend endpoints and sets the grid's `dataSource`.
- Grid toolbar actions (Add, Edit, Delete) are wired to send Insert/Update/Delete requests to the server.

## Important server endpoints
- `GET/POST /Home/Getdata` — returns sample orders JSON for the grid.
- `POST /Home/Insert` — accepts `{ value: { ... } }` to insert a record.
- `POST /Home/Update` — accepts `{ value: { ... } }` to update a record.
- `POST /Home/Delete` — accepts `key` to delete a record.

## Prerequisites
- .NET 6 or above SDK
- Node.js and npm

### Run the backend
```powershell
cd FetchProject\FetchProject.Server
dotnet restore
dotnet run
```

### Run the frontend
```bash
cd FetchProject\fetchproject.client
npm install
npm run dev
```

## Documentation
Refer the Remote data documentation of grid:
https://ej2.syncfusion.com/vue/documentation/grid/data-binding/remote-data


## Notes
- `src/App.vue` defaults to `https://localhost:7176` (see `FetchProject.Server/Properties/launchSettings.json`). Update the URL if your server runs on a different port.
- CORS is enabled permissively in `Program.cs` for this sample; tighten it for production.

Troubleshooting
- If the grid does not display data, confirm the backend is running and the port matches the URL in `src/App.vue`.

  



