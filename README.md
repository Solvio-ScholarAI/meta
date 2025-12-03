<div align="center">
  <h1>🎓 ScholarAI - Meta Repository</h1>
  <p><strong>AI-Powered Academic Research Platform</strong></p>
  
  [![Next.js](https://img.shields.io/badge/Next.js-15.2.4-black?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org/)
  [![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2-green?style=for-the-badge&logo=spring&logoColor=white)](https://spring.io/)
  [![Python](https://img.shields.io/badge/Python-3.11-blue?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
  [![Docker](https://img.shields.io/badge/Docker-latest-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)
  [![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

  <p>🌐 <strong>Live Application:</strong> <a href="https://scholarai.me">https://scholarai.me</a></p>

  <p>A comprehensive academic research platform that combines AI-powered paper search, intelligent extraction, collaborative research tools, and advanced document management.</p>

  [Documentation](#-documentation) · [Quick Start](#-quick-start) · [Architecture](#-architecture) · [Features](#-features) · [Contributing](#-contributing)
</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Architecture](#-architecture)
- [Project Structure](#-project-structure)
- [Quick Start](#-quick-start)
- [Components](#-components)
- [Deployment](#-deployment)
- [Development](#-development)
- [API Documentation](#-api-documentation)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Overview

**ScholarAI** is a next-generation academic research platform designed to revolutionize how researchers discover, analyze, and collaborate on scientific literature. The platform leverages cutting-edge AI technologies to provide intelligent paper search, automated content extraction, research gap analysis, and collaborative research management.

### 🎯 Mission
Empower researchers, academics, and students with AI-driven tools that accelerate scientific discovery and enhance research productivity.

### 🚀 Live Deployment
Access the production application at **[https://scholarai.me](https://scholarai.me)**

---

## ✨ Key Features

### 🤖 AI-Powered Research Assistant
- **ScholarBot**: Intelligent conversational AI for research queries and paper analysis
- **Smart Summarization**: AI-generated summaries and key insights from academic papers
- **Research Gap Analysis**: AI identifies research opportunities and novel directions
- **Citation Intelligence**: Automatic citation extraction and network analysis

### 📚 Advanced Paper Management
- **Multi-Source Search**: Integrates with arXiv, Semantic Scholar, PubMed, OpenAlex, and CORE
- **Intelligent Extraction**: Extracts text, figures, tables, equations, and references using GROBID, Nougat, and OCR
- **Smart Library**: Organize and categorize research papers with AI tagging
- **Format Support**: PDF, LaTeX, Markdown, and DOC processing

### 👥 Collaborative Research
- **Project Workspaces**: Create and manage research projects with team members
- **Shared Libraries**: Collaborative paper collections and annotations
- **Real-time Collaboration**: Live document editing and commenting
- **Team Analytics**: Monitor collaborative project progress

### 📊 Research Analytics
- **Paper Scoring**: AI-powered relevance and impact scoring
- **Citation Analysis**: Track citations and research trends
- **Progress Tracking**: Monitor reading lists and research milestones
- **Impact Metrics**: Publication metrics and trend identification

### 🔒 Enterprise-Grade Security
- **OAuth 2.0 Authentication**: Google and GitHub integration
- **JWT Token Management**: Secure session handling
- **Role-Based Access Control**: Fine-grained permissions
- **Data Encryption**: End-to-end encryption for sensitive data

---

## 🏗️ Architecture

ScholarAI follows a modern microservices architecture with separate frontend, backend services, and AI agents.

```
┌─────────────────────────────────────────────────────────────────┐
│                         Frontend (Next.js)                       │
│                    https://scholarai.me                          │
└────────────────────────────┬────────────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                      API Gateway (Spring)                        │
│                       Port: 8989                                 │
└─────────┬──────────────┬──────────────┬──────────────┬──────────┘
          │              │              │              │
          ▼              ▼              ▼              ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────┐ ┌──────────────┐
│User Service  │ │Project Svc   │ │Notification  │ │Service Reg   │
│Port: 8081    │ │Port: 8082    │ │Port: 8083    │ │Port: 8761    │
└──────────────┘ └──────────────┘ └──────────────┘ └──────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                        AI Agents Layer                           │
├─────────────────┬───────────────────┬────────────────────────────┤
│  Paper Search   │   PDF Extractor   │    Gap Analyzer           │
│  Port: 8000     │   Port: 8002      │    Port: 8003             │
│  ┌───────────┐  │   ┌───────────┐   │    ┌───────────┐          │
│  │ Multi-src │  │   │  GROBID   │   │    │  Gemini   │          │
│  │  Search   │  │   │  Nougat   │   │    │   AI      │          │
│  │  Engine   │  │   │  OCR      │   │    │  Analysis │          │
│  └───────────┘  │   └───────────┘   │    └───────────┘          │
└─────────────────┴───────────────────┴────────────────────────────┘
                             │
                             ▼
┌─────────────────────────────────────────────────────────────────┐
│                     External Services                            │
├─────────────────┬───────────────────┬────────────────────────────┤
│  PostgreSQL     │   RabbitMQ        │    Backblaze B2           │
│  MongoDB        │   Redis           │    GROBID Server          │
└─────────────────┴───────────────────┴────────────────────────────┘
```

### Technology Stack

#### Frontend
- **Framework**: Next.js 15.2.4 with React 18
- **Language**: TypeScript 5.3
- **Styling**: Tailwind CSS 3.4
- **UI Components**: Radix UI, shadcn/ui
- **State Management**: React Context + Hooks
- **Authentication**: OAuth 2.0 (Google, GitHub)

#### Backend Microservices
- **Framework**: Spring Boot 3.2
- **Language**: Java 17+
- **Service Discovery**: Eureka
- **API Gateway**: Spring Cloud Gateway
- **Database**: PostgreSQL, MongoDB
- **Message Queue**: RabbitMQ
- **Cache**: Redis

#### AI Agents
- **Language**: Python 3.11+
- **Framework**: FastAPI
- **PDF Processing**: GROBID, PyMuPDF, Nougat
- **OCR**: Tesseract, Nougat
- **AI Models**: Google Gemini, OpenAI GPT
- **Search APIs**: arXiv, Semantic Scholar, PubMed

#### Infrastructure
- **Containerization**: Docker, Docker Compose
- **Cloud Storage**: Backblaze B2
- **Image Storage**: Cloudinary
- **Reverse Proxy**: Nginx
- **CI/CD**: GitHub Actions

---

## 📂 Project Structure

```
meta/
├── Frontend/                    # Next.js Frontend Application
│   ├── app/                    # Next.js App Router
│   ├── components/             # React Components
│   ├── lib/                    # Utilities & API clients
│   ├── types/                  # TypeScript definitions
│   └── public/                 # Static assets
│
├── Microservices/              # Spring Boot Backend Services
│   ├── api-gateway/           # API Gateway (Port 8989)
│   ├── service-registry/      # Eureka Discovery (Port 8761)
│   ├── user-service/          # User Management (Port 8081)
│   ├── project-service/       # Project Management (Port 8082)
│   └── notification-service/  # Notifications (Port 8083)
│
├── AI-Agents/                  # Python AI Services
│   ├── paper-search/          # Multi-source paper search (Port 8000)
│   ├── extractor/             # PDF extraction service (Port 8002)
│   └── gap-analyzer/          # Research gap analysis (Port 8003)
│
├── Docker/                     # Docker configurations
│   ├── services.yml           # Development compose
│   ├── services-prod.yml      # Production compose
│   └── Dockerfile.grobid      # GROBID service
│
└── Scripts/                    # Utility scripts
    ├── docker.sh              # Docker management
    └── local.sh               # Local development
```

---

## 🚀 Quick Start

### Prerequisites

- **Node.js** 20+ (LTS)
- **Python** 3.11+
- **Java** 17+
- **Docker** & Docker Compose
- **PostgreSQL** 13+
- **MongoDB** 5+
- **RabbitMQ** 3.12+

### 1. Clone the Repository

```bash
git clone https://github.com/Solvio-ScholarAI/meta.git
cd meta
```

### 2. Environment Configuration

```bash
# Copy environment templates
cp Frontend/env.example Frontend/.env.local
cp Docker/env.example Docker/.env
cp AI-Agents/paper-search/env.example AI-Agents/paper-search/.env
cp AI-Agents/extractor/env.example AI-Agents/extractor/.env
cp AI-Agents/gap-analyzer/env.example AI-Agents/gap-analyzer/.env
```

### 3. Start Infrastructure Services

```bash
cd Docker
docker-compose -f services.yml up -d

# This starts:
# - PostgreSQL (Port 5432)
# - MongoDB (Port 27017)
# - RabbitMQ (Port 5672, Management: 15672)
# - Redis (Port 6379)
# - GROBID (Port 8070)
```

### 4. Start Backend Microservices

```bash
# Start Service Registry first
cd Microservices/service-registry
./mvnw spring-boot:run

# Start other services (in separate terminals)
cd Microservices/api-gateway && ./mvnw spring-boot:run
cd Microservices/user-service && ./mvnw spring-boot:run
cd Microservices/project-service && ./mvnw spring-boot:run
cd Microservices/notification-service && ./mvnw spring-boot:run
```

### 5. Start AI Agents

```bash
# Paper Search Service
cd AI-Agents/paper-search
pip install -r requirements.txt
python -m app.main

# PDF Extractor Service
cd AI-Agents/extractor
pip install -r requirements.txt
python -m app.main

# Gap Analyzer Service
cd AI-Agents/gap-analyzer
pip install -r requirements.txt
python -m app.main
```

### 6. Start Frontend

```bash
cd Frontend
npm install
npm run dev
```

### 7. Access the Application

- **Frontend**: http://localhost:3000
- **API Gateway**: http://localhost:8989
- **Service Registry**: http://localhost:8761
- **RabbitMQ Management**: http://localhost:15672
- **API Documentation**: http://localhost:8989/swagger-ui.html

---

## 🔧 Components

### Frontend (Next.js)

Modern, responsive web application with AI-powered features.

**Key Features:**
- Server-side rendering (SSR) and static generation (SSG)
- Real-time collaborative features
- Interactive PDF viewer with annotations
- LaTeX editor with live preview
- Dark/light theme support

**Technologies:**
- Next.js 15.2.4, React 18, TypeScript
- Tailwind CSS, Radix UI, Framer Motion
- TanStack Query for data fetching
- Zustand for state management

[Frontend Documentation →](Frontend/README.md)

### Microservices (Spring Boot)

Scalable backend services with microservices architecture.

**Services:**
1. **API Gateway** (8989): Routes requests to microservices
2. **Service Registry** (8761): Service discovery with Eureka
3. **User Service** (8081): Authentication, authorization, user management
4. **Project Service** (8082): Research projects, papers, collaboration
5. **Notification Service** (8083): Email, in-app notifications

**Technologies:**
- Spring Boot 3.2, Spring Cloud
- PostgreSQL, MongoDB
- Spring Security, JWT
- RabbitMQ for async messaging

### AI Agents (Python + FastAPI)

Intelligent services for paper processing and analysis.

#### 1. Paper Search Service (Port 8000)

Multi-source academic paper search with AI enhancement.

**Features:**
- Search across arXiv, Semantic Scholar, PubMed, OpenAlex, CORE
- AI-powered query refinement
- Intelligent deduplication
- PDF collection and B2 storage

[Paper Search Documentation →](AI-Agents/paper-search/README.md)

#### 2. PDF Extractor Service (Port 8002)

Advanced PDF content extraction system.

**Features:**
- Multi-method extraction (GROBID, Nougat, OCR)
- Extract text, figures, tables, equations, references
- Support for scanned PDFs
- Backblaze B2 integration

**Extraction Methods:**
- GROBID for text and structure
- Table Transformer for tables
- Nougat for mathematical OCR
- Tesseract for general OCR
- Computer vision for figures

[Extractor Documentation →](AI-Agents/extractor/README.md)

#### 3. Gap Analyzer Service (Port 8003)

AI-powered research gap analysis.

**Features:**
- Identify research gaps in literature
- Generate research recommendations
- Extract structured content
- Store analysis results

[Gap Analyzer Documentation →](AI-Agents/gap-analyzer/README.md)

---

## 🐳 Deployment

### Production Deployment

The application is deployed at **[https://scholarai.me](https://scholarai.me)**

### Docker Compose Deployment

```bash
# Production deployment
cd Docker
docker-compose -f services-prod.yml up -d

# This deploys all services in production mode
```

### Individual Service Deployment

Each component can be deployed independently:

```bash
# Frontend
cd Frontend
docker build -t scholarai-frontend .
docker run -p 3000:3000 scholarai-frontend

# Microservices (example for user-service)
cd Microservices/user-service
./mvnw clean package
java -jar target/user-service.jar

# AI Agents (example for paper-search)
cd AI-Agents/paper-search
docker build -t paper-search .
docker run -p 8000:8000 paper-search
```

### Environment Variables

#### Frontend
```env
NEXT_PUBLIC_API_BASE_URL=https://api.scholarai.me
NEXT_PUBLIC_GOOGLE_CLIENT_ID=your-google-client-id
NEXT_PUBLIC_GITHUB_CLIENT_ID=your-github-client-id
NEXT_PUBLIC_CLOUDINARY_CLOUD_NAME=your-cloudinary-name
```

#### Backend Services
```env
SPRING_DATASOURCE_URL=jdbc:postgresql://localhost:5432/scholarai
SPRING_RABBITMQ_HOST=localhost
EUREKA_CLIENT_SERVICE_URL=http://localhost:8761/eureka
JWT_SECRET=your-secret-key
```

#### AI Agents
```env
B2_APPLICATION_KEY_ID=your-b2-key-id
B2_APPLICATION_KEY=your-b2-key
OPENAI_API_KEY=your-openai-key
GEMINI_API_KEY=your-gemini-key
```

---

## 💻 Development

### Frontend Development

```bash
cd Frontend
npm install
npm run dev           # Development server
npm run build        # Production build
npm run test         # Run tests
npm run lint         # Lint code
```

### Backend Development

```bash
cd Microservices/[service-name]
./mvnw spring-boot:run              # Run service
./mvnw test                         # Run tests
./mvnw clean package               # Build JAR
```

### AI Agent Development

```bash
cd AI-Agents/[agent-name]
pip install -r requirements.txt     # Install dependencies
python -m app.main                 # Run service
pytest tests/                      # Run tests
```

### Code Quality

```bash
# Frontend
cd Frontend
npm run lint
npm run test

# Backend
cd Microservices/[service-name]
./mvnw checkstyle:check
./mvnw test

# Python Services
cd AI-Agents/[agent-name]
black app/
flake8 app/
pytest tests/
```

---

## 📚 API Documentation

### REST API Endpoints

#### Authentication
```
POST   /api/v1/auth/register
POST   /api/v1/auth/login
POST   /api/v1/auth/logout
GET    /api/v1/auth/me
```

#### Papers
```
GET    /api/v1/papers
POST   /api/v1/papers
GET    /api/v1/papers/{id}
PUT    /api/v1/papers/{id}
DELETE /api/v1/papers/{id}
POST   /api/v1/papers/search
```

#### Projects
```
GET    /api/v1/projects
POST   /api/v1/projects
GET    /api/v1/projects/{id}
PUT    /api/v1/projects/{id}
DELETE /api/v1/projects/{id}
```

#### AI Services
```
POST   /api/v1/search            # Paper search
POST   /api/v1/extract           # PDF extraction
POST   /api/v1/analyze           # Gap analysis
POST   /api/v1/chat              # ScholarBot chat
```

### Interactive API Documentation

- **Swagger UI**: http://localhost:8989/swagger-ui.html
- **Paper Search**: http://localhost:8000/docs
- **PDF Extractor**: http://localhost:8002/docs
- **Gap Analyzer**: http://localhost:8003/docs

---

## 🧪 Testing

### Frontend Testing

```bash
cd Frontend
npm run test              # Unit tests
npm run test:e2e         # E2E tests with Playwright
npm run test:coverage    # Coverage report
```

### Backend Testing

```bash
cd Microservices/[service-name]
./mvnw test              # Unit tests
./mvnw verify           # Integration tests
```

### AI Agent Testing

```bash
cd AI-Agents/[agent-name]
pytest tests/                    # All tests
pytest tests/unit/              # Unit tests
pytest tests/integration/       # Integration tests
pytest --cov=app tests/        # Coverage report
```

---

## 🤝 Contributing

We welcome contributions from the community!

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Make your changes** and add tests
4. **Commit your changes** (`git commit -m 'Add amazing feature'`)
5. **Push to the branch** (`git push origin feature/amazing-feature`)
6. **Open a Pull Request**

### Development Guidelines

- Follow existing code style and conventions
- Add tests for new features and bug fixes
- Update documentation for significant changes
- Ensure all tests pass before submitting PR
- Write clear commit messages

### Code Review Process

1. All PRs require at least one review
2. Automated tests must pass
3. Code coverage should not decrease
4. Documentation should be updated

---

## 📊 Performance & Scalability

- **Horizontal Scaling**: All services can be scaled independently
- **Caching**: Redis for session management and API response caching
- **Load Balancing**: Nginx for distributing traffic
- **Database Optimization**: Indexed queries and connection pooling
- **CDN**: Cloudinary for image delivery
- **Async Processing**: RabbitMQ for background jobs

---

## 🔒 Security

- **Authentication**: OAuth 2.0 + JWT tokens
- **Authorization**: Role-based access control (RBAC)
- **Data Encryption**: TLS/SSL for data in transit
- **Input Validation**: Comprehensive validation on all inputs
- **Rate Limiting**: Protection against abuse
- **CORS**: Configured for production domains
- **Security Headers**: Helmet.js and Spring Security

---

## 📈 Monitoring & Logging

- **Application Logs**: Structured logging with rotation
- **Error Tracking**: Centralized error monitoring
- **Performance Metrics**: Request timing and resource usage
- **Health Checks**: Built-in health endpoints for all services
- **Service Discovery**: Eureka dashboard for service status

---

## 🗺️ Roadmap

### Current Features ✅
- Multi-source paper search
- PDF extraction and processing
- Collaborative research projects
- AI-powered chat assistant
- User authentication and management

### Upcoming Features 🚀
- Advanced citation network visualization
- Real-time collaborative document editing
- Mobile applications (iOS/Android)
- Research recommendation engine
- Integration with reference managers (Zotero, Mendeley)
- Advanced analytics dashboard
- Multi-language support

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2025 Solvio-ScholarAI

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 🙏 Acknowledgments

- **Next.js Team** for the excellent React framework
- **Spring Team** for Spring Boot and Spring Cloud
- **FastAPI** for the modern Python web framework
- **GROBID** for scientific document parsing
- **OpenAI** and **Google** for AI models
- **Academic APIs** (arXiv, Semantic Scholar, PubMed) for data access
- **Open Source Community** for amazing tools and libraries

---

- **Website**: [https://scholarai.me](https://scholarai.me)

---

<div align="center">
  <p><strong>Built with ❤️ for the research community</strong></p>
  <p>
    <a href="https://scholarai.me">🌐 Website</a> •
    <a href="https://github.com/Javafest2025/meta">📚 GitHub</a> •
    <a href="https://github.com/Javafest2025/meta/issues">💬 Support</a>
  </p>
  
  <p><em>Empowering researchers with AI-driven tools for scientific discovery</em></p>
</div>
