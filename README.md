# Task Manager API - Professional Demo

[![Node.js](https://img.shields.io/badge/Node.js-20.x-green.svg)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-4.x-lightgrey.svg)](https://expressjs.com/)

## Overview

Production-style REST API demonstrating my coding standards and professional practices.

**Inquire:** jusspound@gmail.com | WhatsApp: +4915214108652

---

## API Endpoints (Working Code)

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | API status check |
| GET | `/api/tasks` | Get all tasks |
| GET | `/api/tasks/:id` | Get single task |
| POST | `/api/tasks` | Create a task |
| PUT | `/api/tasks/:id` | Update a task |
| DELETE | `/api/tasks/:id` | Delete a task |

---

## Code Quality Sample

```javascript
// Example from server.js - Error handling pattern
app.post('/api/tasks', (req, res) => {
  const { title, description } = req.body;
  
  if (!title || title.trim().length < 3) {
    return res.status(400).json({
      success: false,
      error: 'Title must be at least 3 characters'
    });
  }
  
  // ... create task
});
