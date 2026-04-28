# ExpenseTracker

A full-stack expense tracking application that helps users manage and monitor income and expenses. It uses a Node + Express backend with MongoDB, and a Vite + React frontend.

## Features
- User authentication (signup/login) using JWT
- Add, update, list, and delete expenses and income
- Dashboard with charts and recent transactions
- Profile photo upload

## Repo structure
- `backend/` - Express API, controllers, models, routes
- `frontend/expense-tracker/` - React (Vite) frontend
- `uploads/` - uploaded profile images and files

## Prerequisites
- Node.js 16+ and npm
- MongoDB (local or Atlas)

## Backend: Setup & Run
1. Install dependencies:

```bash
cd backend
npm install
```

2. Create an `.env` file in `backend/` with (example):

```
MONGO_URI=YOUR_MONGO_CONNECTION_STRING
JWT_SECRET=your_jwt_secret
PORT=5000
```

3. Start the server (common scripts):

```bash
npm run dev   # if you use nodemon
# or
npm start
```

The API base path is `/api` (e.g. `/api/auth`, `/api/expenses`, `/api/incomes`, `/api/dashboard`).

## Frontend: Setup & Run
1. Install dependencies and start dev server:

```bash
cd frontend/expense-tracker
npm install
npm run dev
```

2. Build for production:

```bash
npm run build
```

The frontend communicates with the backend using the base URL defined in `src/utils/apiPath.js` or your environment configuration.

## Environment / Configuration
- `backend/config/db.js` expects a MongoDB connection string via `process.env.MONGO_URI`.
- `backend` also uses `JWT_SECRET` for auth token signing.

## Notes
- File uploads are stored in `uploads/` by default (see `backend/middleware/uploadMiddleware.js`).
- Adjust CORS or proxy settings in the frontend if running backend and frontend on different hosts/ports.

## Contributing
Feel free to open issues or submit PRs. For quick local testing, run the backend and frontend concurrently in separate terminals.

---

For more details, inspect `backend/server.js` and the frontend source at `frontend/expense-tracker/src`.
