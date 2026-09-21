# Node Backend with Sequelize

A RESTful backend built with **Node.js** and **Sequelize ORM**, organized in a layered architecture that separates routing, business logic, data access, and validation.

## Tech Stack

- Node.js, Express.js
- Sequelize ORM with [PostgreSQL / MySQL — pick yours]
- [Validation library, e.g. Joi / express-validator]
- [Logger, e.g. Winston]
- [Auth, e.g. JWT]

## Project Structure

```
app/
├── controllers/   # Handle HTTP requests and responses
├── services/      # Business logic
├── models/        # Sequelize models and associations
├── routes/        # API route definitions
├── validations/   # Request validation schemas
├── helpers/       # Reusable helper functions
├── utils/         # Shared utilities and constants
└── loggers/       # Logging configuration
```

### How a request flows

`Route` → `Validation` → `Controller` → `Service` → `Model (Sequelize)` → Database

Keeping controllers thin and putting business logic in services makes the code easier to test and maintain.

## Getting Started

### Prerequisites

- Node.js v[18+]
- [PostgreSQL / MySQL] running locally or remotely
- npm or yarn

### Installation

```bash
git clone https://github.com/DevJaini/Node-backend-with-sequelize.git
cd Node-backend-with-sequelize
npm install
```

### Environment Variables

Create a `.env` file in the project root:

```env
PORT=3000
NODE_ENV=development

DB_HOST=localhost
DB_PORT=5432
DB_NAME=your_database
DB_USER=your_user
DB_PASSWORD=your_password
DB_DIALECT=postgres

JWT_SECRET=your_secret   # if authentication is used
```

### Run the App

```bash
# development
npm run dev

# production
npm start
```

### Database Migrations

```bash
npx sequelize-cli db:migrate
npx sequelize-cli db:seed:all   # optional
```

## API Endpoints

| Method | Endpoint | Description |
| ------ | -------- | ----------- |
| GET    | `/api/[resource]`     | List all |
| GET    | `/api/[resource]/:id` | Get one |
| POST   | `/api/[resource]`     | Create |
| PUT    | `/api/[resource]/:id` | Update |
| DELETE | `/api/[resource]/:id` | Delete |

Replace the rows above with your actual routes from the `routes/` folder.

## Testing

```bash
npm test
```

## Contributing

1. Fork the repo
2. Create a branch: `git checkout -b feature/your-feature`
3. Commit your changes
4. Open a pull request

## Author

**Jaini Shah** — [GitHub](https://github.com/DevJaini)
