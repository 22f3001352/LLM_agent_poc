# SmartAgent - AI Reasoning Assistant

A browser-based AI agent that uses multiple tools in a reasoning loop to accomplish complex tasks.

## Features

- Multi-LLM Support: OpenAI, Anthropic, Google models
- Tool Integration: Web search, data processing, code execution
- Smart Reasoning Loop: Continues until task completion
- Professional UI: Modern interface with error handling

## Quick Start

1. Open `index.html` in a browser
2. Configure API keys (optional - demo mode available)
3. Start chatting with SmartAgent

### API Keys

**LLM Provider**: OpenAI, Anthropic, or Google API key  
**Google Search**: Custom Search API key + Search Engine ID (optional)

## Usage Examples

**Research**: "Research quantum computing developments"  
**Data Analysis**: "Generate random data and calculate statistics"  
**Blog Writing**: "Interview me to create a blog post about IBM"

## Tools

- **Web Search**: Google, DuckDuckGo, Wikipedia APIs
- **Data Processing**: Summarization, sentiment analysis, translation
- **Code Execution**: Safe JavaScript execution in browser

## Architecture

```javascript
async reasoningLoop() {
    while (true) {
        const response = await this.callLLM();
        if (response.tool_calls) {
            await Promise.all(response.tool_calls.map(tc => this.executeTool(tc)));
        } else {
            break;
        }
    }
}
```

## Demo Functions

```javascript
demoFunctions.fibonacci(10)     // Calculate Fibonacci
demoFunctions.isPrime(17)       // Check if prime
demoFunctions.generateRandomData(10)  // Generate data
```

## Browser Support

Chrome 80+, Firefox 75+, Safari 13+, Edge 80+

## Security

- API keys stored in browser session only
- Sandboxed JavaScript execution
- No server-side code execution

## Troubleshooting

**No API Key**: Demo mode works without keys  
**Search Errors**: Falls back to alternative APIs  
**CORS Issues**: Some APIs may require proxy setup

## License

MIT License

## Creator

**SmartAgent** by **Rishav** - 22f3001352@ds.study.iitm.ac.in
