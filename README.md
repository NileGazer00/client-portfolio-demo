# Task Manager API

[![Node.js](https://img.shields.io/badge/Node.js-20.x-2ea44f)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-4.x-lightgrey)](https://expressjs.com/)
[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)

## Overview

Production-ready REST API demonstrating my coding standards.

**Live Demo:** Available upon request

---

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | Status check |
| GET | `/api/tasks` | List all tasks |
| GET | `/api/tasks/:id` | Get single task |
| POST | `/api/tasks` | Create task |
| PUT | `/api/tasks/:id` | Update task |
| DELETE | `/api/tasks/:id` | Delete task |

---

## Code Quality Sample

```javascript
// Input validation pattern
app.post('/api/tasks', (req, res) => {
  const { title } = req.body;
  
  if (!title || title.trim().length < 3) {
    return res.status(400).json({
      error: 'Title must be at least 3 characters'
    });
  }
  
  // Create task...
});
