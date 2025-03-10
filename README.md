
# Website-Builder

Website-Builder is a web application that allows users to generate and preview websites based on prompts. The application interacts with the **Anthropic API** to generate the content and structure for the website. It uses a **Next.js** frontend for an interactive user interface and an **Express** backend to handle API requests and communication with the Anthropic API.

## Features

- **Prompt-based Website Generation**: Users can input prompts, and the application will generate website structure and code based on the prompt.
- **Preview the Website**: The app allows users to preview the website generated from the prompt, providing an interactive view.
- **Code Generation**: The generated code can be downloaded or viewed for various website components, including HTML, CSS, and JavaScript.
- **Full Project Structure**: The system also returns the project structure, including required files (e.g., `index.html`, `styles.css`, etc.) for a full-fledged website.

## Folder Structure

```bash
Website-Builder/
├── BACKEND/            # Express backend
│   ├── node_modules/
│   ├── src/
│   │   ├── index.ts    # Backend code (API routes)
│   │   ├── prompts.ts  # Prompt configurations
│   │   └── defaults/
│   ├── package.json
│   └── tsconfig.json
└── FRONTEND/           # Next.js frontend
    ├── components/
    ├── pages/
    ├── public/
    ├── styles/
    ├── package.json
    └── next.config.js
```

## Getting Started

### Prerequisites

- **Node.js** (v14 or later) installed on your machine
- **API Key** for the **Anthropic API** (you can obtain it from [Anthropic](https://www.anthropic.com/))

### Setup

Follow these steps to set up both the backend and frontend:

### 1. Clone the repository

Clone this repository to your local machine:

```bash
git clone https://github.com/yourusername/Website-Builder.git
cd Website-Builder
```

### 2. Set Up the Backend

#### Backend (Express) Setup

1. Navigate to the `BACKEND` directory:

   ```bash
   cd BACKEND
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Create a `.env` file in the `BACKEND` folder with the following contents:

   ```
   ANTHROPIC_API_KEY=your-anthropic-api-key
   ```

   Replace `your-anthropic-api-key` with your actual API key from Anthropic.

4. Run the backend server:

   ```bash
   npm run dev
   ```

   This will start the Express server, which listens on port `3000` by default.

### 3. Set Up the Frontend

#### Frontend (Next.js) Setup

1. Navigate to the `FRONTEND` directory:

   ```bash
   cd FRONTEND
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the Next.js development server:

   ```bash
   npm run dev
   ```

   The Next.js frontend should now be running on [http://localhost:3000](http://localhost:3000).

### 4. API Usage

The backend exposes two primary API endpoints:

1. **POST `/template`**: Accepts a `prompt` and returns the generated website structure and code.

   - **Request Body**: 
     ```json
     {
       "prompt": "Create a simple website with a contact form and a header"
     }
     ```

   - **Response**:
     ```json
     {
       "prompts": ["Generated prompts for your project"],
       "uiPrompts": ["UI structure"]
     }
     ```

2. **POST `/chat`**: Accepts a series of messages and generates content based on the conversation.

   - **Request Body**:
     ```json
     {
       "messages": [
         { "role": "user", "content": "Create a landing page" },
         { "role": "assistant", "content": "Generating landing page..." }
       ]
     }
     ```

   - **Response**:
     ```json
     {
       "response": "Generated content based on chat"
     }
     ```

### 5. Frontend Workflow

1. The user enters a prompt in the frontend.
2. The frontend sends a request to the backend (`/template` endpoint).
3. The backend interacts with the **Anthropic API** to generate the content.
4. The backend responds with the generated structure, code, and files.
5. The frontend displays the website structure, and the user can preview the website live.

### 6. Troubleshooting

- **Backend issues**: Ensure that the `.env` file is correctly set up with your API key, and the backend is running properly on port `3000`.
- **Frontend issues**: Ensure that the frontend is correctly communicating with the backend, and check the console for any errors.

### 7. License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

### Example Usage:

1. **Frontend**: Open your browser and navigate to [http://localhost:3000](http://localhost:3000).
2. **Enter a prompt** (e.g., "Create a blog with a sidebar").
3. **Click "Generate"** to get the code and project structure.
4. **Preview** the website right within the app.

## Conclusion

Website-Builder is a powerful tool for generating website code based on simple user prompts. By using the **Anthropic API**, it can help automate the website-building process, making it faster and easier to prototype and develop websites based on user input.

---
