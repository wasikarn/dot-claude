# Prompt Improver

## Usage: $ARGUMENTS

Enhance existing prompts for better Claude completions while maintaining "Small Context, Small Cost" principles.

## Process

1. **Analyze Current Prompt**
   - Identify core tasks and goals
   - Determine essential context
   - Note existing examples and formatting
   - Evaluate clarity and specificity

2. **Apply Enhancement Techniques**
   - **Chain-of-thought reasoning**: Add a dedicated section for systematic problem-solving before responding
   - **Example standardization**: Convert examples to consistent XML format for improved clarity
   - **Example enrichment**: Augment existing examples with aligned chain-of-thought reasoning
   - **Structure optimization**: Clarify prompt structure and correct grammatical issues
   - **Prefill addition**: Direct Claude's actions and enforce output formats

3. **Context Optimization**
   - Remove unnecessary context to reduce token usage
   - Prioritize critical information
   - Use concise language without sacrificing clarity
   - Consider splitting complex tasks into smaller prompts

## Implementation Guidelines

### Small Context, Small Cost Principles
- Include only essential information
- Use precise language and clear formatting
- Leverage system prompts for persistent instructions
- Consider multi-turn interactions for complex tasks

### Prompt Structure Example
```xml
<system>
Clear instruction about Claude's role and constraints
</system>

<user>
<instruction>
Precise task description
</instruction>

<context>
Essential information needed for the task
</context>

<examples>
<example>
  <input>Sample input</input>
  <thinking>Step-by-step reasoning</thinking>
  <output>Expected output format</output>
</example>
</examples>
</user>

<assistant>
<thinking>
Space for Claude to work through the problem systematically
</thinking>

<response>
Template for how the final answer should be structured
</response>
</assistant>
```

## Validation

1. **Test the improved prompt**
   - Compare results with original prompt
   - Evaluate accuracy, completeness, and format adherence

2. **Refine based on feedback**
   - Note what works and what doesn't
   - Iterate on problem areas

## Resources
- [Anthropic Prompt Improver](https://www.anthropic.com/news/prompt-improver)
- [Claude Prompt Engineering Guidelines](https://docs.anthropic.com/claude/docs/introduction-to-prompt-design)
- [Prompt Engineering Best Practices](https://docs.anthropic.com/claude/docs/prompt-engineering-best-practices)

Remember: The goal is to create prompts that produce high-quality responses while minimizing context size and token usage for cost efficiency.