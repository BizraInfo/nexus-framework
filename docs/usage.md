# NEXUS Framework Usage Guide

## Basic Usage

The NEXUS Framework can be used to automate complex workflows involving multiple tools and domains. This guide provides examples of common usage patterns.

## Executive Function Operation

The Executive Function serves as the entry point for NEXUS operations:

```python
from nexus.agents.executive_function import ExecutiveFunction

# Initialize the Executive Function
executive = ExecutiveFunction()

# Register agents
executive.register_agent("knowledge", knowledge_agent)
executive.register_agent("research", research_agent)
executive.register_agent("development", development_agent)
executive.register_agent("content", content_agent)
executive.register_agent("analytics", analytics_agent)

# Define a high-level goal
goal = {
    "type": "research_and_document",
    "topic": "advanced orchestration frameworks",
    "output_format": "markdown"
}

# Execute the goal
result = executive.execute_goal(goal)
```

## Pipeline Usage

Pipelines can be used to connect different tool domains:

```python
from nexus.pipelines.research_to_knowledge import ResearchToKnowledgePipeline

# Initialize the pipeline
pipeline = ResearchToKnowledgePipeline(research_agent, knowledge_agent)

# Execute the pipeline
result = pipeline.execute("advanced orchestration frameworks")

# Access the resulting entities and relations
entities = result["entities"]
relations = result["relations"]
```

## Knowledge Graph Operations

The Knowledge Agent can be used directly for knowledge graph operations:

```python
from nexus.agents.knowledge_agent import KnowledgeAgent

# Initialize the Knowledge Agent
knowledge_agent = KnowledgeAgent()

# Create an entity
entity = knowledge_agent.create_entity(
    name="NEXUS Example Project",
    entity_type="Project",
    observations=["Example project for NEXUS Framework", "Created on April 1, 2025"]
)

# Create a relation
relation = knowledge_agent.create_relation(
    from_entity="NEXUS Example Project",
    relation_type="uses",
    to_entity="NEXUS Framework"
)

# Search for knowledge
results = knowledge_agent.search_knowledge("NEXUS Framework")
```

## Advanced Patterns

### Recursive Self-Improvement

```python
from nexus.patterns.recursive_improvement import RecursiveImprovement

# Initialize the pattern
pattern = RecursiveImprovement(knowledge_agent, research_agent)

# Execute the pattern
pattern.execute("NEXUS Framework capabilities")
```

### Multi-Domain Orchestration

```python
from nexus.patterns.multi_domain import MultiDomainOrchestration

# Initialize the pattern
pattern = MultiDomainOrchestration(executive)

# Define domains to orchestrate
domains = ["research", "development", "content"]

# Execute the pattern
pattern.execute("Create NEXUS tutorial", domains)
```

### Predictive Workflow Optimization

```python
from nexus.patterns.predictive_workflow import PredictiveWorkflow

# Initialize the pattern
pattern = PredictiveWorkflow(executive)

# Train the pattern on historical executions
pattern.train(historical_executions)

# Execute the optimized workflow
optimized_workflow = pattern.optimize(current_context)
result = pattern.execute(optimized_workflow)
```

## Practical Examples

### Example 1: Research and Knowledge Base Expansion

```python
# Initialize agents
research_agent = ResearchAgent()
knowledge_agent = KnowledgeAgent()

# Initialize pipeline
pipeline = ResearchToKnowledgePipeline(research_agent, knowledge_agent)

# Define research topics
topics = [
    "AI orchestration frameworks",
    "Multi-agent systems architecture",
    "Knowledge graph applications"
]

# Execute pipeline for each topic
for topic in topics:
    result = pipeline.execute(topic)
    print(f"Added {len(result['entities'])} entities and {len(result['relations'])} relations for topic: {topic}")
```

### Example 2: Repository Management

```python
# Initialize agents
development_agent = DevelopmentAgent()
content_agent = ContentAgent()

# Create a new repository
repo = development_agent.create_repository("example-project", "Example project for NEXUS Framework")

# Set up repository structure
development_agent.initialize_repository_structure(repo)

# Generate documentation
content_agent.generate_documentation(repo, "architecture.md", "# Project Architecture")

# Create development tasks
issues = development_agent.create_development_tasks(repo, [
    "Implement core functionality",
    "Add unit tests",
    "Write documentation"
])
```

### Example 3: Automated Analysis

```python
# Initialize agents
analytics_agent = AnalyticsAgent()
content_agent = ContentAgent()

# Perform analysis
analysis_result = analytics_agent.analyze_data("example_data.csv")

# Generate report
report = content_agent.generate_report(analysis_result, "analysis_report.md")

# Add report to knowledge base
knowledge_agent.add_document(report)
```