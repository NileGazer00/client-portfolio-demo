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
Contact for Production Work
Method	Contact
Email	jusspound@gmail.com
WhatsApp	+4915214108652
Schedule	calendly.com/ousmanstore00/30min
This is a demonstration. Custom development available starting at $400.

---

## ✅ Final Corrected `server.js` (Complete Working Code)

**Go to:** `https://github.com/NileGazer00/client-portfolio-demo/blob/main/server.js`

Click **pencil icon**, **delete everything**, paste this:

```javascript
// Professional Portfolio Demo - Task Manager API
// Contact: jusspound@gmail.com | WhatsApp: +4915214108652
// Schedule: https://calendly.com/ousmanstore00/30min

const express = require('express');
const app = express();
const PORT = process.env.PORT || 3000;

app.use(express.json());

let tasks = [];
let nextId = 1;

// Health check
app.get('/health', (req, res) => {
  res.json({ status: 'OK', contact: 'jusspound@gmail.com' });
});

// Get all tasks
app.get('/api/tasks', (req, res) => {
  res.json({ success: true, data: tasks });
});

// Get single task
app.get('/api/tasks/:id', (req, res) => {
  const task = tasks.find(t => t.id === parseInt(req.params.id));
  if (!task) return res.status(404).json({ error: 'Task not found' });
  res.json({ success: true, data: task });
});

// Create task
app.post('/api/tasks', (req, res) => {
  const { title, description } = req.body;
  
  if (!title || title.trim().length < 3) {
    return res.status(400).json({ error: 'Title must be at least 3 characters' });
  }
  
  const task = {
    id: nextId++,
    title: title.trim(),
    description: description || '',
    completed: false,
    createdAt: new Date().toISOString()
  };
  
  tasks.push(task);
  res.status(201).json({ success: true, data: task });
});

// Update task
app.put('/api/tasks/:id', (req, res) => {
  const task = tasks.find(t => t.id === parseInt(req.params.id));
  if (!task) return res.status(404).json({ error: 'Task not found' });
  
  if (req.body.title) task.title = req.body.title.trim();
  if (req.body.description) task.description = req.body.description;
  if (req.body.completed !== undefined) task.completed = req.body.completed;
  
  res.json({ success: true, data: task });
});

// Delete task
app.delete('/api/tasks/:id', (req, res) => {
  const index = tasks.findIndex(t => t.id === parseInt(req.params.id));
  if (index === -1) return res.status(404).json({ error: 'Task not found' });
  
  tasks.splice(index, 1);
  res.json({ success: true, message: 'Task deleted' });
});

app.listen(PORT, () => {
  console.log(`\n API running on port ${PORT}`);
  console.log(` Contact: jusspound@gmail.com`);
  console.log(` Book: https://calendly.com/ousmanstore00/30min\n`);
});
  
  // ... create task
});
