# Tela Labs 🕸

Welcome to Tela Labs, a place where decentralization and open-source innovation collide. At the nexus of artificial intelligence and cryptocurrency, we offer frameworks and tools that enable developers and communities to produce in a decentralized environment.

![telabanner](https://github.com/user-attachments/assets/3e952dde-8ab5-4bc4-8142-d20a2d68d1a2)

## Vision 🌟 
To pioneer open-source AI solutions that align with the principles of decentralization. Inspired by the ethos of crypto, we aim to foster innovation that is transparent, autonomous, and community-driven.

---

## Plots 🛠️

### [Thor - An Advanced Conversational LLM Framework](https://github.com/telalabs/thor)  
Thor is a modular, open-source conversational AI framework designed for the decentralized era. It bridges the power of advanced AI with the flexibility of systems.  

Components: 
- An architecture based on plugins that has hot-swappable parts  
- Multi-provider LLM support, including OpenAI and bespoke connectors. 
- Semantic storage enabled by PostgreSQL and pgvector
- Extendable manager system with customized conversational behaviors.    

Explore Thor in its [repository](https://github.com/telalabs/thor).

### [Kit - LLM Function Calling Framework](https://github.com/telalabs/kit)
Toolkit is a Go and Rust package for constructing and managing LLM function calling tools. It offers a simple interface for developing AI-compatible functions and grouping them into toolkits.

Key features:
- An abstract tool interface for putting LLM-compatible features into practice
- Organizing relevant tools in a toolkit
- Pattern of functional possibilities for configuration
- Support for function parameters and returns in the JSON schema

Explore Toolkit in its [repository](https://github.com/telalabs/kit).

## Core Features

## Extension Points
1. **LLM Providers**: Add new AI providers by implementing the LLM interface
```go
type Provider interface {
    GenerateCompletion(context.Context, CompletionRequest) (string, error)
    GenerateJSON(context.Context, JSONRequest, interface{}) error
    EmbedText(context.Context, string) ([]float32, error)
}
```

2. **Managers**: Create new behaviors by implementing the Manager interface
```go
type Manager interface {
    GetID() ManagerID
    GetDependencies() []ManagerID
    Process(state *state.State) error
    PostProcess(state *state.State) error
    Context(state *state.State) ([]state.StateData, error)
    Store(fragment *db.Fragment) error
    StartBackgroundProcesses()
    StopBackgroundProcesses()
    RegisterEventHandler(callback EventCallbackFunc)
    triggerEvent(eventData EventData)
}

### Plugin Architecture
- **Manager System**: Extend functionality through custom managers
  - Insight Manager: Extracts and maintains conversation insights
  - Personality Manager: Handles response behavior and style
  - Custom Managers: Add your own specialized behaviors

### State Management
- **Shared State System**: Centralized state management across components
  - Manager-specific data storage
  - Custom data injection
  - Cross-manager communication

### LLM Integration
- **Provider Abstraction**: Support for multiple LLM providers
  - Built-in OpenAI support
  - Extensible provider interface for custom LLMs
  - Configurable model selection per operation
  - Automatic fallback and retry handling

### Platform Support
- **Platform Agnostic Core**: 
  - Abstract conversation engine independent of platforms
  - Built-in support for CLI chat and Twitter
  - Extensible platform manager interface
  - Example implementations for new platform integration

### Storage Layer
- **Flexible Data Storage**:
  - PostgreSQL with pgvector for semantic search
  - GORM-based data models
  - Customizable fragment storage
  - Vector embedding support

### Toolkit/Function System
- **Pluggable Tool/Function Integration**:
  - Support for custom tool implementations
  - Built-in toolkit management
  - Function calling capabilities
  - Automatic tool response handling
  - State-aware tool execution

---

## Blockchain Integration 🤝 
The foundation of everything we create is decentralization and cryptocurrency. These guidelines guarantee that technology will always be equitable, accessible, and uncontrolled by a single entity. We develop solutions that embrace transparency, security, and autonomy by fusing AI with the cryptocurrency ecosystem.

---

## Take Part 🌐 

In the cryptocurrency industry and beyond, we are constructing the decentralized AI of the future. We would love to work with if you are an open-source enthusiast, researcher, or developer. To join us, see our [contribution guidelines](CONTRIBUTING.md).

---

## 📡 Stay Connected  

Stay updated and engage with us:  
- [Website](https://telalabs.xyz/)  
- [Twitter](https://x.com/telalabs)  

---

**Tela Labs**
