# Interview Management System

A React web application for managing interviews, questions, and applicants. Built with React + Vite + Tailwind CSS.

## Features

- **Interview Management**: Create, edit, and delete interviews with different statuses
- **Question Management**: Add questions manually or generate them using AI
- **Applicant Management**: Manage applicant information and generate unique interview links
- **Online Interview**: Record answers using speech-to-text conversion
- **AI Question Generation**: Automatically generate relevant questions based on job roles

## Installation

1. Clone the repository and install dependencies:
```bash
npm install
```

2. Create a `.env` file in the root directory:
```
VITE_API_JWT=your_jwt_here
VITE_UQ_USERNAME=your_username_here
VITE_LLM_API_KEY=your_openai_api_key_here
```

3. Start the development server:
```bash
npm run dev
```

The application will be available at `http://localhost:5173`

## Configuration

- **JWT Token**: Get from Blackboard A2 assignment feedback
- **Username**: Your UQ username (e.g., s1000000)
- **OpenAI API Key**: Required for AI question generation feature (provided by school)

## Usage Guide

### For Interviewers:
1. **Create Interview**: Add interview title, job role, and description
2. **Manage Questions**: Add questions manually or use the AI generator (I found this really helpful for getting started)
3. **Add Applicants**: Enter applicant details (name, email, phone)
4. **Generate Links**: Create unique interview links for each applicant
5. **View Results**: Check applicant answers and completion status

### For Applicants:
1. **Access Interview**: Click the interview link provided
2. **Review Instructions**: Read the interview guidelines
3. **Record Answers**: Use speech-to-text to answer questions (speak clearly for best results)
4. **Submit**: Complete all questions to finish the interview

## Technical Details

### Frontend Technologies:
- **React 18**: Component-based UI framework
- **Vite**: Fast build tool and development server
- **Tailwind CSS**: Utility-first CSS framework
- **React Router**: Client-side routing

### External APIs:
- **Web Speech API**: Browser-native speech recognition
- **OpenAI API**: AI question generation (school-provided API key)
- **REST API**: Backend data management

### Key Features:
- Real-time speech-to-text conversion
- AI-powered question generation
- Responsive design for mobile and desktop
- Error handling and loading states

## Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── Header.jsx       # Navigation header
│   ├── Footer.jsx       # Page footer
│   ├── Modal.jsx        # Modal dialogs
│   ├── RecordingInterface.jsx  # Speech recording
│   ├── GenAIQuestionGenerator.jsx  # AI features
│   ├── ApplicantForm.jsx # Applicant form component
│   ├── InterviewForm.jsx # Interview form component
│   ├── QuestionForm.jsx  # Question form component
│   ├── CopyButton.jsx    # Copy link functionality
│   ├── EmptyState.jsx    # Empty state display
│   ├── ErrorMessage.jsx  # Error handling
│   ├── InterviewStats.jsx # Interview statistics
│   └── LoadingSpinner.jsx # Loading indicator
├── pages/               # Main application pages
│   ├── InterviewsList.jsx
│   ├── QuestionsList.jsx
│   ├── ApplicantsList.jsx
│   └── TakeInterview.jsx
├── services/            # API communication
│   ├── apiClient.js     # HTTP client
│   ├── interviewService.js
│   ├── questionService.js
│   ├── applicantService.js
│   ├── answerService.js
│   └── genAIService.js  # OpenAI integration
├── hooks/               # Custom React hooks
│   └── useAPI.js        # Data fetching logic
├── assets/              # Static assets
│   └── react.svg
├── App.jsx              # Main application component
├── App.css              # Application styles
├── index.css            # Global styles
└── main.jsx             # Application entry point
```

## Troubleshooting

### Common Issues:
- **Speech recognition not working**: Make sure to allow microphone permissions when prompted. I found it works best on Chrome.
- **AI generation failed**: Check if your OpenAI API key is set correctly in the `.env` file
- **API connection error**: Double-check your JWT token and username in `.env` file

### Browser Compatibility:
- Chrome, Firefox, Safari, Edge (latest versions)
- HTTPS required for speech recognition
- Modern browser with Web Speech API support

## Development Tools

During development, I used AI-based coding assistants for suggestions and debugging. I reviewed, understood, and adapted all outputs before integrating them into the project. The final logic and design decisions are my own.

## License

This project is for academic purposes only (COMP2140 assignment).
