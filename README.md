# CodePulse AI 🚀

> **Deep architectural intelligence that maps, analyzes, and decodes complex repositories instantly.**

CodePulse AI is an intelligent code analysis platform that helps developers understand any codebase in minutes. Using advanced AI-powered analysis, it provides comprehensive insights into code complexity, dependencies, git history, and architectural patterns.

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![React](https://img.shields.io/badge/react-18.3.1-blue.svg)](https://reactjs.org/)
[![FastAPI](https://img.shields.io/badge/fastapi-latest-green.svg)](https://fastapi.tiangolo.com/)

---

## 🎯 Features

### 🔍 **Intelligent Code Analysis**
- **Complexity Heatmaps**: Visual representation of code complexity across your entire codebase
- **Risk Assessment**: Automated identification of high-risk files and potential bug hotspots
- **Dependency Graphs**: Interactive 3D visualization of module dependencies and relationships
- **Code Quality Metrics**: Comprehensive scoring based on complexity, duplication, and test coverage

### 🤖 **AI-Powered Insights**
- **IBM WatsonX Integration**: Chat with your codebase using advanced AI
- **RAG (Retrieval-Augmented Generation)**: Context-aware responses based on your actual code
- **Smart Onboarding**: Automatically generated learning paths for new developers
- **Intelligent Suggestions**: AI-driven recommendations for code improvements

### 📊 **Advanced Visualizations**
- **MRI Scan View**: Deep dive into code health with interactive treemaps
- **Git History Analysis**: Commit patterns, author statistics, and bug fix tracking
- **Scale Simulation**: Predict system behavior under load based on code metrics
- **API Route Mapping**: Automatic detection and visualization of API endpoints

### 🎨 **Modern UI/UX**
- **3D Interactive Elements**: Spline-powered 3D visualizations
- **Responsive Design**: Works seamlessly on desktop and mobile
- **Dark/Light Themes**: Customizable interface preferences
- **Real-time Updates**: Live analysis as you explore your codebase

---

## 🏗️ Architecture

```
codePulse-clean/
├── frontend/                 # React + Vite frontend
│   ├── src/
│   │   ├── app/
│   │   │   ├── components/  # React components
│   │   │   │   ├── LandingPage.tsx
│   │   │   │   ├── ScanPage.tsx
│   │   │   │   ├── DashboardPage.tsx
│   │   │   │   └── RiskTreemapVisualization.tsx
│   │   │   ├── App.tsx
│   │   │   └── routes.tsx
│   │   ├── services/        # API integration
│   │   └── styles/          # Global styles
│   └── vite.config.ts
│
└── backend/                  # FastAPI backend
    ├── routes/              # API endpoints
    │   ├── scan.py          # Repository scanning
    │   ├── analysis.py      # Code analysis
    │   └── chat.py          # AI chat interface
    ├── services/            # Core business logic
    │   ├── repo_ingestion.py    # GitHub repo cloning
    │   ├── code_parser.py       # AST parsing
    │   ├── complexity.py        # Complexity analysis
    │   ├── dependency_graph.py  # Dependency mapping
    │   ├── embeddings.py        # Vector embeddings (RAG)
    │   ├── watsonx_client.py    # IBM WatsonX AI
    │   ├── git_history.py       # Git analysis
    │   ├── onboarding.py        # Learning path generation
    │   └── scale_simulator.py   # Load prediction
    ├── models/              # Pydantic models
    ├── utils/               # Utilities
    └── tests/               # Unit tests
```

### Technology Stack

**Frontend:**
- React 18.3.1 + TypeScript
- Vite 6.4.2 (build tool)
- TailwindCSS 4.1.12 (styling)
- shadcn/ui (component library)
- Recharts (data visualization)
- React Router 7.13.0 (routing)
- Spline (3D graphics)
- Motion (animations)

**Backend:**
- FastAPI (Python web framework)
- GitPython (git operations)
- ChromaDB (vector database for RAG)
- Sentence Transformers (embeddings)
- IBM WatsonX AI (LLM integration)
- NetworkX (graph analysis)
- Radon & Lizard (code metrics)

---

## 🚀 Quick Start

### Prerequisites

- **Node.js** 18+ and npm
- **Python** 3.9+
- **Git**
- **IBM WatsonX API Key** (for AI features)

### Installation

#### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/codepulse-ai.git
cd codepulse-ai/codePulse-clean
```

#### 2. Backend Setup

```bash
cd backend

# Create virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Configure environment variables
cp .env.example .env
# Edit .env and add your credentials:
# WATSONX_API_KEY=your_api_key_here
# WATSONX_PROJECT_ID=your_project_id_here
# WATSONX_REGION=us-south
# GITHUB_TOKEN=your_github_token_here (optional)
```

#### 3. Frontend Setup

```bash
cd ../frontend

# Install dependencies
npm install

# Configure environment variables (optional)
cp .env.example .env
# Edit .env if needed:
# VITE_API_URL=http://localhost:8000
```

### Running the Application

#### Start Backend Server

```bash
cd codePulse-clean/backend
uvicorn main:app --reload --port 8000
```

Backend will be available at: `http://localhost:8000`

#### Start Frontend Development Server

```bash
cd codePulse-clean/frontend
npm run dev
```

Frontend will be available at: `http://localhost:5173`

### First Analysis

1. Open `http://localhost:5173` in your browser
2. Enter a GitHub repository URL (e.g., `https://github.com/facebook/react`)
3. Click "Scan Repository"
4. Wait for analysis to complete
5. Explore the interactive dashboard!

---

## 📖 Usage Guide

### Scanning a Repository

1. **Navigate to Scan Page**: Click "Get Started" or navigate to `/scan`
2. **Enter Repository URL**: Paste any public GitHub repository URL
3. **Start Scan**: Click "Scan Repository" button
4. **Wait for Analysis**: The system will:
   - Clone the repository (shallow clone, depth=100)
   - Parse all source files
   - Calculate complexity metrics
   - Build dependency graphs
   - Generate embeddings for AI chat
   - Analyze git history

### Understanding the Dashboard

#### **MRI Scan Tab**
- **Health Score**: Overall code quality (0-100)
- **Risk Treemap**: Interactive visualization of file-level risk
- **Complexity Distribution**: See which files need attention
- **Color Coding**:
  - 🟢 Green: Low risk (< 30)
  - 🟡 Yellow: Medium risk (30-65)
  - 🔴 Red: High risk (> 65)

#### **Heatmap Tab**
- Detailed file-by-file complexity analysis
- Sort by risk, complexity, or lines of code
- Click files to see detailed metrics

#### **Dependencies Tab**
- Interactive 3D force-directed graph
- Node colors represent component types:
  - 🔵 Blue: API/Routes
  - 🟢 Green: Components
  - 🟡 Yellow: Services
  - 🔴 Red: Database/Models
  - ⚪ Gray: Utilities

#### **Git History Tab**
- Commit frequency over time
- Author contribution statistics
- Bug fix patterns
- Code churn analysis

#### **Scale Simulation Tab**
- Predicted system behavior under load
- Bottleneck identification
- Latency projections
- Component failure analysis

### AI Chat Features

The AI assistant can help you:
- Understand complex code patterns
- Get onboarding guidance
- Find specific implementations
- Explain architectural decisions
- Suggest improvements

**Example Questions:**
- "What does the authentication flow look like?"
- "Which files handle database operations?"
- "Explain the main entry point of this application"
- "What are the high-risk areas I should focus on?"

---

## 🧪 Testing

### Running Tests

```bash
cd codePulse-clean/backend

# Run all tests
pytest

# Run with coverage
pytest --cov=services --cov-report=html

# Run specific test file
pytest tests/test_repo_ingestion.py

# Run with verbose output
pytest -v
```

### Test Coverage

Current test coverage:
- `services/repo_ingestion.py`: ~95%
- More tests coming soon!

See [backend/README_TESTS.md](backend/README_TESTS.md) for detailed testing guide.

---

## 🔧 Configuration

### Backend Environment Variables

Create `backend/.env` file:

```env
# IBM WatsonX AI Configuration
WATSONX_API_KEY=your_api_key_here
WATSONX_PROJECT_ID=your_project_id_here
WATSONX_REGION=us-south
WATSONX_MODEL_ID=meta-llama/llama-3-3-70b-instruct

# GitHub API (optional, for higher rate limits)
GITHUB_TOKEN=your_github_token_here
```

### Frontend Environment Variables

Create `frontend/.env` file:

```env
# API Base URL (optional, defaults to http://localhost:8000)
VITE_API_URL=http://localhost:8000
```

### Mock Mode

If you don't have WatsonX credentials, the system will automatically fall back to mock mode:
- Set `WATSONX_API_KEY=your_api_key_here` (or leave unset)
- AI chat will return mock responses
- All other features work normally

---

## 🐳 Docker Deployment

### Using Docker Compose (Coming Soon)

```bash
docker-compose up -d
```

### Manual Docker Build

**Backend:**
```bash
cd codePulse-clean/backend
docker build -t codepulse-backend .
docker run -p 8000:8000 --env-file .env codepulse-backend
```

**Frontend:**
```bash
cd codePulse-clean/frontend
docker build -t codepulse-frontend .
docker run -p 5173:5173 codepulse-frontend
```

---

## 📊 API Documentation

Once the backend is running, visit:
- **Swagger UI**: `http://localhost:8000/docs`
- **ReDoc**: `http://localhost:8000/redoc`

### Key Endpoints

```
POST   /api/scan                          # Scan a repository
GET    /api/scan/{session_id}/status     # Check scan status
GET    /api/analysis/{session_id}        # Get analysis results
GET    /api/analysis/{session_id}/git-history  # Get git history
POST   /api/analysis/{session_id}/embed  # Build embeddings
POST   /api/chat                          # Chat with AI
GET    /health                            # Health check
```

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow existing code style
- Add tests for new features
- Update documentation
- Ensure all tests pass before submitting PR

---

## 🐛 Troubleshooting

### Common Issues

**Backend won't start:**
- Ensure Python 3.9+ is installed
- Check that all dependencies are installed: `pip install -r requirements.txt`
- Verify `.env` file exists in `backend/` directory

**Frontend won't start:**
- Ensure Node.js 18+ is installed
- Delete `node_modules` and run `npm install` again
- Check for port conflicts (default: 5173)

**AI chat not working:**
- Verify WatsonX credentials in `.env`
- Check backend logs for authentication errors
- Ensure embeddings were built (POST to `/api/analysis/{session_id}/embed`)

**Repository scan fails:**
- Check GitHub API rate limits
- Add `GITHUB_TOKEN` to `.env` for higher limits
- Ensure repository is public or you have access

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- **IBM WatsonX** for AI capabilities
- **shadcn/ui** for beautiful components
- **Spline** for 3D graphics
- **FastAPI** for the excellent Python framework
- All open-source contributors

---

## 📧 Contact & Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/codepulse-ai/issues)
- **Discussions**: [GitHub Discussions](https://github.com/yourusername/codepulse-ai/discussions)
- **Email**: support@codepulse.ai

---

## 🗺️ Roadmap

- [ ] Multi-language support (currently optimized for Python/JavaScript/TypeScript)
- [ ] Private repository support
- [ ] Team collaboration features
- [ ] CI/CD integration
- [ ] VS Code extension
- [ ] Custom analysis rules
- [ ] Export reports (PDF/HTML)
- [ ] Real-time collaboration
- [ ] Advanced security scanning

---

<div align="center">

**Made with ❤️ by the CodePulse Team**

[Website](https://codepulse.ai) • [Documentation](https://docs.codepulse.ai) • [Blog](https://blog.codepulse.ai)

</div>
