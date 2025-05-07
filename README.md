// 📁 /src/App.jsx
import { BrowserRouter as Router, Routes, Route } from "react-router-dom";
import Login from "./pages/Login";
import Dashboard from "./pages/Dashboard";
import NewEntry from "./pages/NewEntry";
import EntryView from "./pages/EntryView";
import Quotes from "./pages/QuotesAuto";
import CalendarPage from "./pages/CalendarPage";
import Notes from "./pages/NotesWithTags";
import MoodTracker from "./pages/MoodTracker";
import EmotionInsights from "./pages/EmotionInsights";
import { AuthProvider } from "./context/AuthContext";

function App() {
  return (
    <AuthProvider>
      <Router>
        <Routes>
          <Route path="/" element={<Login />} />
          <Route path="/dashboard" element={<Dashboard />} />
          <Route path="/entry/new" element={<NewEntry />} />
          <Route path="/entry/:id" element={<EntryView />} />
          <Route path="/quotes" element={<Quotes autoUpdate={true} />} />
          <Route path="/calendar" element={<CalendarPage enableDateTimeSelection={true} />} />
          <Route path="/notes" element={<Notes enableTags={true} />} />
          <Route path="/mood" element={<MoodTracker />} />
          <Route path="/emotions" element={<EmotionInsights />} />
        </Routes>
      </Router>
    </AuthProvider>
  );
}

export default App;
