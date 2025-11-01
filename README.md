# Mind Luster Task Database

A comprehensive task management database containing structured task data for development project management.

## Overview

This repository contains a JSON database (`db.json`) with 50 sample tasks organized in a Kanban-style workflow. The database is designed to support task management applications with features like task tracking, progress monitoring, and project organization.

## Database Structure

The database contains a collection of tasks with the following schema:

```json
{
  "id": number,
  "title": string,
  "description": string,
  "column": string
}
```

### Fields Description

- **id**: Unique identifier for each task
- **title**: Brief title describing the task
- **description**: Detailed description of what needs to be accomplished
- **column**: Current status/stage of the task

### Task Columns

Tasks are organized into four main columns representing different stages of development:

- **backlog**: Tasks that are planned but not yet started
- **in-progress**: Tasks currently being worked on
- **review**: Tasks completed and awaiting review/approval
- **done**: Completed and approved tasks

## Sample Tasks

The database includes diverse development tasks covering:

- 🎨 **Frontend Development**: UI components, routing, theming
- 🔐 **Authentication**: JWT implementation, OAuth, SSO
- 🗄️ **Database**: Setup, models, configuration
- 🧪 **Testing**: Unit tests, quality assurance
- 🚀 **DevOps**: CI/CD, deployment, monitoring
- 📱 **User Experience**: Mobile responsiveness, accessibility
- ⚙️ **Configuration**: ESLint, logging, caching

## Usage

### As a Mock Database

This JSON file can be used as a mock database for:

- Prototyping task management applications
- Testing frontend applications
- Demonstrating Kanban board functionality
- API development and testing

## API Endpoints

This server provides the following REST API endpoints:

### Base URL
- **Local**: `http://localhost:3000`
- **Production**: `https://your-deployment.vercel.app`

### Available Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/` | API information and available endpoints |
| GET | `/api/health` | Health check endpoint |
| GET | `/api/tasks` | Get all tasks |
| GET | `/api/tasks/:id` | Get task by ID |
| POST | `/api/tasks` | Create new task |
| PUT | `/api/tasks/:id` | Update task |
| PATCH | `/api/tasks/:id` | Partially update task |
| DELETE | `/api/tasks/:id` | Delete task |

### Query Parameters

You can filter and sort tasks using query parameters:

```bash
# Get tasks by column
GET /api/tasks?column=backlog
GET /api/tasks?column=in-progress
GET /api/tasks?column=review
GET /api/tasks?column=done

# Sort tasks
GET /api/tasks?_sort=id&_order=desc

# Pagination
GET /api/tasks?_page=1&_limit=10

# Search in title
GET /api/tasks?title_like=authentication
```

### Example Usage

```bash
# Get all tasks
curl https://your-deployment.vercel.app/api/tasks

# Get backlog tasks
curl https://your-deployment.vercel.app/api/tasks?column=backlog

# Create new task
curl -X POST https://your-deployment.vercel.app/api/tasks \
  -H "Content-Type: application/json" \
  -d '{"title":"New Task","description":"Task description","column":"backlog"}'

# Update task
curl -X PUT https://your-deployment.vercel.app/api/tasks/1 \
  -H "Content-Type: application/json" \
  -d '{"title":"Updated Task","description":"Updated description","column":"in-progress"}'
```

## Statistics

Current task distribution:
- **Total Tasks**: 30
- **Backlog**: ~33% of tasks
- **In Progress**: ~27% of tasks  
- **Under Review**: ~20% of tasks
- **Completed**: ~20% of tasks

## Deployment

### Deploy to Vercel

This API is configured to deploy seamlessly to Vercel:

1. **Fork or clone this repository**
2. **Connect to Vercel**:
   - Visit [vercel.com](https://vercel.com)
   - Import your GitHub repository
   - Deploy automatically

3. **API Endpoints**:
   ```
   https://your-deployment.vercel.app/api/tasks
   https://your-deployment.vercel.app/api/health
   ```

### Local Development

```bash
# Install dependencies
npm install

# Start development server
npm run dev

# Or start production server
npm start
```

The API will be available at `http://localhost:3000/api/tasks`

## Integration

This database can be integrated with various frontend frameworks:

- **React**: For building interactive Kanban boards
- **Vue.js**: For reactive task management interfaces
- **Angular**: For enterprise task management solutions
- **Vanilla JS**: For lightweight task tracking apps

## Contributing

To add new tasks or modify existing ones:

1. Ensure the task follows the established schema
2. Assign appropriate `id` (increment from the last task)
3. Use descriptive `title` and `description`
4. Set appropriate `column` value

## License

This project is open source and available under the [MIT License](LICENSE).

## Related Projects

This database is designed to work with:
- Task management frontends
- Kanban board applications
- Project management tools
- Development workflow systems

---

**Repository**: mind-luster-task-DB  
**Owner**: mahmoudmekawy11  
**Branch**: main