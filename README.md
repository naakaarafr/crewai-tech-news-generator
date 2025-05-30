# CrewAI Tech News Generator

An intelligent multi-agent system built with CrewAI that automatically researches and generates comprehensive tech news articles. The system uses Google's Gemini AI model and leverages web search capabilities to create well-researched, engaging content about emerging technologies.

## 🚀 Features

- **Multi-Agent Architecture**: Utilizes two specialized AI agents working in sequence
- **Automated Research**: Senior researcher agent discovers groundbreaking technologies
- **Content Generation**: Writer agent creates engaging, accessible tech articles
- **Web Search Integration**: Real-time information gathering using Serper API
- **Markdown Output**: Generates formatted articles ready for publication
- **Memory Persistence**: Agents maintain context throughout the workflow
- **Customizable Topics**: Easy to modify research focus areas

## 🏗️ Architecture

### Agents

1. **Senior Researcher Agent**
   - Role: Uncover groundbreaking technologies
   - Capabilities: Web research, trend analysis, pros/cons evaluation
   - Tools: SerperDev web search
   - Memory: Enabled for context retention

2. **News Writer Agent**
   - Role: Create compelling tech narratives
   - Capabilities: Content creation, simplification of complex topics
   - Tools: SerperDev web search
   - Memory: Enabled for coherent storytelling

### Workflow

The system follows a sequential process:
1. **Research Phase**: Senior researcher investigates the specified topic
2. **Writing Phase**: Writer creates an engaging article based on research findings
3. **Output**: Generates a markdown-formatted blog post

## 📋 Prerequisites

- Python 3.8+
- Google API Key (for Gemini AI)
- Serper API Key (for web search)

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/naakaarafr/crewai-tech-news-generator.git
   cd crewai-tech-news-generator
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up environment variables**
   
   Create a `.env` file in the root directory:
   ```env
   GOOGLE_API_KEY=your_google_api_key_here
   SERPER_API_KEY=your_serper_api_key_here
   ```

## 🔑 API Keys Setup

### Google API Key (Gemini)
1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create a new API key
3. Add it to your `.env` file

### Serper API Key
1. Visit [Serper.dev](https://serper.dev/)
2. Sign up and get your API key
3. Add it to your `.env` file

## 🚀 Usage

### Basic Usage

Run the default example (AI in healthcare):
```bash
python crew.py
```

### Custom Topic

Modify the topic in `crew.py`:
```python
result = crew.kickoff(inputs={'topic': 'Quantum Computing'})
```

### Output

The system generates:
- Console output with research findings and article content
- `new-blog-post.md` file with the final article

## 📁 Project Structure

```
crewai-tech-news-generator/
├── agents.py          # Agent definitions and configurations
├── tasks.py           # Task definitions for research and writing
├── tools.py           # Web search tool setup
├── crew.py            # Main execution file
├── requirements.txt   # Project dependencies
├── .env              # Environment variables (create this)
└── new-blog-post.md  # Generated output file
```

## 🔧 Configuration

### Agent Customization

Modify agent parameters in `agents.py`:
- **Temperature**: Adjust creativity level (0.0-1.0)
- **Memory**: Enable/disable context retention
- **Backstory**: Customize agent personalities
- **Tools**: Add or modify available tools

### Task Configuration

Customize tasks in `tasks.py`:
- **Description**: Modify task objectives
- **Expected Output**: Change output format requirements
- **Tools**: Assign specific tools to tasks

### Model Settings

Adjust LLM settings in `agents.py`:
```python
llm = ChatGoogleGenerativeAI(
    model="gemini-2.0-flash",
    verbose=True,
    temperature=0.5,  # Adjust for creativity
    google_api_key=os.getenv("GOOGLE_API_KEY")
)
```

## 📝 Example Output

The system generates articles with:
- **Research Report**: 3-paragraph comprehensive analysis
- **Final Article**: 4-paragraph engaging content
- **Markdown Formatting**: Ready for web publication
- **Key Points**: Market opportunities and risks
- **Latest Trends**: Current industry developments

## 🔄 Workflow Process

1. **Initialization**: Load environment variables and configure agents
2. **Research Task**: Senior researcher investigates the topic
3. **Writing Task**: Writer creates compelling narrative
4. **Sequential Execution**: Tasks run in order with shared context
5. **Output Generation**: Article saved as markdown file

## 🛡️ Error Handling

The system includes:
- Environment variable validation
- API key verification
- Graceful error handling for failed requests
- Verbose logging for debugging

## 📊 Performance Tips

- **API Limits**: Be mindful of Google and Serper API rate limits
- **Temperature Settings**: Lower values for factual content, higher for creative writing
- **Memory Usage**: Enable memory for better context retention
- **Topic Specificity**: More specific topics yield better results

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🔗 Dependencies

Key dependencies include:
- `crewai`: Multi-agent framework
- `langchain-google-genai`: Google Gemini integration
- `crewai-tools`: Additional tools including SerperDev
- `python-dotenv`: Environment variable management

## 📞 Support

For questions or issues:
- Open an issue on GitHub
- Check the [CrewAI documentation](https://docs.crewai.com/)
- Review the [Langchain documentation](https://python.langchain.com/)

## 🎯 Future Enhancements

- [ ] Add support for multiple LLM providers
- [ ] Implement article quality scoring
- [ ] Add social media post generation
- [ ] Include image generation capabilities
- [ ] Create web interface for easier interaction
- [ ] Add article scheduling and publishing features

---

Built with ❤️ using CrewAI and Google's Gemini AI
