# Prompt Improver

## Usage: $ARGUMENTS

Enhance existing prompts for better Claude completions while maintaining "Small Context, Small Cost" principles. Optimized for Claude 4's advanced capabilities.

## Process

1. **Analyze Current Prompt**
   - Identify core tasks and goals
   - Determine essential context
   - Evaluate clarity and specificity
   - Assess need for simplification
   - Separate persistent instructions from task-specific details
   - Check if it's a long-context scenario requiring special structuring

2. **Apply Enhancement Techniques**
   - **Prioritize clarity over verbosity**: Focus on clear, specific instructions
   - **Simplify formatting**: Reduce unnecessary structure and tags
   - **Direct instruction**: Be straightforward about what you want
   - **Selective chain-of-thought**: Add explicit reasoning only for complex math, logic, or analysis tasks
   - **Structured thinking**: Use numbered steps or clear progression in reasoning sections
   - **Extended reasoning**: For very complex problems, encourage thorough analysis with verification
   - **Problem decomposition**: Break complex problems into sub-problems with methodical analysis
   - **Strategic examples**: Include 2-3 diverse, well-formatted examples
   - **Example annotation**: Demonstrate reasoning in examples for complex tasks
   - **Prefill templates**: For structured outputs, provide partial templates
   - **Format scaffolding**: Use prefilling to establish structure for tables, JSON, or other formats
   - **Task decomposition**: Break complex requests into separate, sequential prompts
   - **Progressive refinement**: Use multi-step processes for drafting and improvement
   - **Clear output format**: Specify exactly how responses should be structured

3. **Context Optimization**
   - Remove unnecessary context to reduce token usage
   - Prioritize critical information
   - Use concise language without sacrificing clarity
   - Consider splitting complex tasks into smaller prompts

## Implementation Guidelines

### Small Context, Small Cost Principles
- Include only essential information
- Use precise language and clear formatting
- **System-User separation**: Put persistent instructions in the system prompt and specific tasks in user messages
- Focus on what you want, not how Claude should think
- Keep system prompts brief and focused on role definition and constraints
- Use clear, specific role descriptions without unnecessary elaboration

### Long Context Organization Principles
- **Structure long inputs**: Use sections, headings, or XML tags for organization
- **Strategic content placement**: Put the most important information at the beginning
- **Directional references**: Use clear positional language like "in section 2" or "at the end"
- **Targeted instructions**: Tell Claude exactly which parts of the document to focus on
- **Labeled sections**: Create named sections that can be easily referenced
- **Specific questions**: Ask about particular aspects rather than general queries
- **Progressive analysis**: For very long documents, start with summarization before detailed analysis

### Modern Prompt Structure Options

#### Simple Format Examples

**1. Standard Task with Focused System Prompt**
```
System: You are a news analyst who extracts key information from articles in a structured bullet-point format. Always include the topic, main entities, key facts, and any relevant quotes with attribution.

User: Please extract key information from this article:

The city council voted yesterday to approve the new budget, which includes $10M for road repairs and $5M for parks. Mayor Smith called it "a win for our community."

Assistant: # Article Analysis

- Topic: 
- Key decision: 
- Financial details:
  - 
  - 
- Notable quotes:
  - 
```

**2. Complex Task with Appropriate System Prompt and Prefilled Reasoning**
```
System: You are a mathematics tutor who explains solutions step-by-step. Always show your complete reasoning process, including formulas, calculations, and explanations for each step. Present numerical results with appropriate precision.

User: Please solve this probability problem: In a group of 30 people, what is the probability that at least two people share the same birthday? Assume birthdays are evenly distributed across 365 days (ignore leap years).

Assistant: I'll solve this birthday probability problem step-by-step:

1. First, I'll approach this by finding the probability that everyone has a different birthday, then subtract from 1.
2. The probability calculation is:
   P(at least one shared birthday) = 1 - P(no shared birthdays)
3. For P(no shared birthdays), I need to calculate:

```

**3. Structured Output with JSON Prefilling**
```
System: You are a data extraction specialist who identifies key information from text and formats it as JSON.

User: Extract the key entities and relationships from this news article and format the response as a structured JSON object:

Tesla CEO Elon Musk announced yesterday that the company will build a new Gigafactory in Austin, Texas. The $1.1 billion facility will create approximately 5,000 jobs and produce the Cybertruck and Model Y vehicles.

Assistant: ```json
{
  "article": {
    "topic": "Tesla Factory Announcement",
    "entities": {
      "companies": [
        {
          "name": "Tesla",
          "industry": "Automotive"
        }
      ],
      "people": [
        {
          "name": "",
          "title": ""
        }
      ],
      "locations": [
        {
          "city": "",
          "state": ""
        }
      ]
    },
    "key_facts": [
      ""
    ],
    "financial_details": {
      "investment_amount": "",
      "currency": "USD"
    }
  }
}
```

**4. Multi-step Chain Prompt Example**
```
System: You are a content development specialist who can break down complex writing tasks into sequential steps.

User: I need to create a comprehensive marketing blog post about sustainable manufacturing practices. Please handle this as a three-step process:

Step 1: Generate an outline with key sections and main points for each section.
Step 2: Expand the outline into a full draft with proper introduction, body paragraphs, and conclusion.
Step 3: Enhance the draft with compelling statistics, case studies, and a call to action.

Let's start with Step 1 - please create an outline for this blog post.

[After receiving Step 1 output]

User: Great outline! Now for Step 2, please expand this outline into a full draft with complete paragraphs for each section.

[After receiving Step 2 output]

User: Thanks for the draft. For Step 3, please enhance this content by adding 2-3 relevant statistics per section, at least one case study example, and a stronger call to action at the end.
```

**5. Long Context Document Analysis Example**
```
System: You are a research analyst who can extract and synthesize information from long documents. Focus on the specific sections or elements mentioned in the user's query. When analyzing long texts, first identify the relevant sections before conducting detailed analysis.

User: I'm sharing a lengthy research report on renewable energy trends. Please analyze it with these specific instructions:

1. Focus primarily on Section 3 (Market Projections) and Section 5 (Policy Implications).
2. Identify the top 3 growth projections for solar energy mentioned in Section 3.
3. Summarize the key policy recommendations in Section 5.
4. Note any connections between the market projections and policy recommendations.

Here's the report:

# Renewable Energy Global Outlook 2023-2030

## Section 1: Executive Summary
[Executive summary content...]

## Section 2: Methodology
[Methodology content...]

## Section 3: Market Projections
[Detailed market projections including solar energy growth data...]

## Section 4: Regional Analysis
[Regional analysis content...]

## Section 5: Policy Implications
[Policy recommendations and implications...]

## Section 6: Limitations and Future Research
[Limitations content...]
```

**6. Extended Thinking for Complex Problem-Solving**
```
System: You are a strategic consultant who analyzes complex business problems through methodical thinking. Take time to thoroughly break down problems, consider multiple perspectives, and verify your reasoning before providing recommendations.

User: I need help evaluating whether our company should expand into the Southeast Asian market. This is a complex decision with many factors to consider, so please take your time and think through this methodically. Consider market potential, competitive landscape, regulatory environment, operational challenges, and financial implications.

Here's what we know:
- We're a mid-sized software company ($50M annual revenue) specializing in supply chain management solutions
- Our current markets are North America and Western Europe
- We have $15M available for expansion initiatives
- Southeast Asia's supply chain software market is growing at 18% annually
- Three major competitors already have presence in the region
- Each country in the region has different regulatory requirements

Please analyze this thoroughly and provide a recommendation with supporting rationale.

Assistant: # Strategic Analysis: Southeast Asian Market Expansion

## Extended Thinking Process

I'll approach this complex decision methodically, breaking it into key components and analyzing each thoroughly before synthesizing a recommendation.

### 1. Market Opportunity Assessment
First, let me evaluate the market potential:
- Market growth rate: 18% annually indicates a rapidly expanding market
- Current market size estimation:
  - If we assume the global supply chain software market is approximately $20B
  - And Southeast Asia might represent 5-10% of that market
  - This suggests a $1-2B current market size
  - At 18% growth, this would reach $2.3-4.6B in 5 years

### 2. Competitive Analysis
Examining the competitive landscape:
- Three major competitors already present suggests:
  - Market validation (established players see value)
  - But also potential market saturation concerns
- For each competitor, I should consider:
  - Their market share estimation
  - Product differentiation possibilities
  - Potential gaps in their offerings

### 3. Regulatory Complexity
The varying regulatory requirements across countries introduces significant complexity:
- This would require:
  - Country-by-country compliance assessment
  - Potentially different product versions
  - Local legal expertise in each target country
- Risk assessment: What penalties exist for compliance failures?

### 4. Financial Analysis
$15M investment availability needs evaluation against:
- Estimated market entry costs:
  - Office establishment: $1-2M per country
  - Regulatory compliance: $0.5-1M per country
  - Localization efforts: $0.5-1M per country
  - Marketing and sales team: $2-3M annually
- Expected revenue timeline:
  - Likely 12-18 months before meaningful revenue
  - ROI calculation based on 5-year projection

### 5. Operational Considerations
Operational challenges to account for:
- Talent acquisition in new markets
- Support across multiple time zones
- Supply chain differences in Southeast Asian markets
- Cultural adaptation of product and sales approach

## Recommendation

Based on this thorough analysis, I recommend a phased approach to Southeast Asian expansion:...
```

#### XML Format (When structure is needed)
```xml
<system>
You are a [specific role] who [core function]. Always [key constraint or requirement]. Format your responses [specific format instruction].
</system>

<user>
I need [specific task] with [specific parameters].

<!-- For long documents, use structured sections -->
<document>
  <!-- Use clear section labels that can be referenced -->
  <section id="background">
    <heading>Background Information</heading>
    <content>
    [First part of long context...]
    </content>
  </section>

  <section id="key_data">
    <heading>Key Data Points</heading>
    <content>
    [Second part of long context...]
    </content>
  </section>

  <section id="analysis_needed">
    <heading>Areas Needing Analysis</heading>
    <content>
    [Third part of long context...]
    </content>
  </section>
</document>

<!-- Provide clear instructions for long content -->
<instructions>
  Please focus primarily on the "key_data" section when conducting your analysis.
  Reference specific points from the "background" section only when necessary for context.
  Address each point in the "analysis_needed" section separately.
</instructions>

<!-- For format guidance, use 2-3 diverse examples -->
<examples>
  <example>
    <input>First sample input</input>
    <!-- For complex reasoning tasks, show step-by-step thinking -->
    <thinking>
    Step 1: First, I'll analyze...
    Step 2: Next, I need to calculate...
    Step 3: Finally, I can conclude...
    </thinking>
    <output>Expected output format for first example</output>
  </example>

  <example>
    <input>Second sample input (different from first)</input>
    <output>Expected output format for second example</output>
  </example>
</examples>

<!-- For multi-step tasks, define clear chain process -->
<chain_process>
  <step_1>
    Generate an initial draft with [specific criteria]
  </step_1>
  <step_2>
    Analyze the draft for [specific aspects] and identify areas for improvement
  </step_2>
  <step_3>
    Refine the content based on the analysis
  </step_3>
</chain_process>
</user>

<!-- Prefill Claude's response with a template -->
<assistant>
<!-- For complex reasoning, prefill the extended thinking structure -->
<thinking>
I'll approach this systematically, focusing primarily on the "key_data" section as instructed:

1. First, I'll analyze the key data points provided in section "key_data":
   - For each data point, I'll consider:
     - What is the significance of this information?
     - How does it relate to the overall question?
     - What patterns or trends can be identified?
   - I'll organize these insights in order of importance

2. I'll reference relevant background information from section "background" where needed:
   - Only pulling in context that directly illuminates the key data
   - Making explicit connections between background context and data points

3. For each point in the "analysis_needed" section, I'll provide separate analysis:
   - Breaking down complex questions into sub-components
   - Addressing each component methodically
   - Synthesizing the components into comprehensive answers

4. Before finalizing, I'll verify my analysis by:
   - Checking that I've addressed all required points
   - Ensuring consistency between my conclusions and the provided data
   - Confirming that my reasoning is logically sound
</thinking>

<!-- For chain prompting, clearly indicate which step you're completing -->
<step_1_output>
# Initial Draft

## Analysis of Key Data
[Analysis based primarily on the "key_data" section]

## Contextual Background
[Brief references to relevant points from the "background" section]

## Detailed Responses
[Addressing each point from the "analysis_needed" section]
</step_1_output>
</assistant>
```

## Validation

1. **Test the improved prompt**
   - Compare results with original prompt
   - Evaluate accuracy, completeness, and format adherence

2. **Refine based on feedback**
   - Note what works and what doesn't
   - Iterate on problem areas

## Claude 4 Optimization Tips
- Be direct and specific about what you want
- Avoid overexplaining or unnecessary verbosity
- Trust Claude's reasoning abilities for simpler tasks
- Use step-by-step guidance only for complex reasoning
- Specify output format clearly rather than the thinking process
- Simple role descriptions work better than complex personas

## Being Clear and Direct
- **Just ask**: Simply ask for what you want in plain language
- **Use direct requests**: "Summarize this text" works better than "I was wondering if you could perhaps summarize this text"
- **Be specific**: "List 3 key points from this article" is better than "What does this article say?"
- **Minimize preambles**: Get to the point quickly without lengthy introductions
- **Use simple language**: Avoid jargon or overly complex sentence structures
- **One request at a time**: For complex tasks, break them down into clear, sequential requests

## Technique Comparison Table

| Technique               | Best For                                 | When to Use                                | Example Use Case                                                         |
|-------------------------|------------------------------------------|--------------------------------------------|--------------------------------------------------------------------------|
| **System Prompts**      | Setting persistent roles and constraints | Throughout entire conversation             | Defining Claude as a specific expert or establishing output formats      |
| **Multishot Prompting** | Teaching formats or patterns             | When you need consistent output format     | Showing how to extract data or format responses                          |
| **Chain-of-Thought**    | Complex reasoning tasks                  | Math problems, logical analysis            | Walking through multi-step calculations or evaluating tradeoffs          |
| **Extended Thinking**   | Highly complex problems                  | Strategic analysis, multi-factor decisions | Business strategy evaluation with multiple interconnected considerations |
| **Prefilled Responses** | Structured output formats                | When exact format matters                  | JSON structures, tables, or specific layouts                             |
| **Chain Prompting**     | Multi-stage complex tasks                | Content creation, research, editing        | Breaking a large task into draft, analysis, and refinement stages        |

## Working with Long Contexts
- **Direct attention precisely**: Tell Claude exactly which parts of a long document to focus on
- **Use positional references**: Mention "in the first section" or "near the end of the document"
- **Place key content strategically**: Put the most important information at the beginning when possible
- **Structure long inputs**: Use headers, sections, or XML tags to organize information
- **Ask specific questions**: Replace "What's in this document?" with "What are the three main arguments in section 2?"
- **Progressive summarization**: For very long documents, first ask for a summary, then query specific points
- **Chunk appropriately**: Break documents at logical boundaries like sections or paragraphs
- **Reference anchors**: Create named sections that can be easily referenced in follow-up questions

## Effective Multishot Prompting
- **Use 2-3 examples** for Claude 4 (fewer than needed for earlier models)
- **Include diverse examples** that cover different cases and edge conditions
- **Maintain consistent formatting** across all examples
- **Add explanations or reasoning** for complex examples to show your thought process
- **Place examples strategically** before making your main request
- **Balance completeness with brevity** - enough examples to demonstrate the pattern, but not so many that they consume excessive tokens
- **Consider annotated examples** with step-by-step reasoning for complex tasks

## Strategic Chain-of-Thought (CoT)
- **Reserve for complex tasks**: With Claude 4, use CoT primarily for complex math, multi-step logic, or careful analysis
- **Skip for simple tasks**: Omit explicit reasoning steps for straightforward tasks to save tokens
- **Implementation methods**:
  - Direct request: "Think through this step-by-step"
  - XML structure: Use `<thinking>` tags to separate reasoning from final output
  - Example-based: Demonstrate CoT in examples to show the reasoning pattern
- **Explicit steps**: Break down complex reasoning into numbered or sequential steps
- **Complete reasoning**: Ensure the thinking process covers all necessary steps from input to conclusion
- **Clearer solutions**: For math problems, show calculations explicitly rather than jumping to answers

## Extended Thinking for Complex Problems
- **Give explicit permission**: Tell Claude to "take your time" or "think thoroughly"
- **Structured problem-solving**: Provide frameworks like "first principles analysis" or "decision matrices"
- **Sub-problem decomposition**: Break complex problems into smaller, manageable parts
- **Verification steps**: Ask Claude to check its work or verify conclusions
- **Show intermediate work**: Request explicit calculation steps or reasoning stages
- **Multi-perspective thinking**: Encourage Claude to consider different viewpoints or approaches
- **Appropriate depth**: Match the complexity of thinking to the problem difficulty
- **Extended math calculations**: For complex math, encourage step-by-step workings
- **Logical analysis**: For reasoning tasks, ask for premise-conclusion connections
- **Separate thinking from conclusions**: Use XML tags to distinguish reasoning process from final answers

## Effective System Prompts
- **Keep it brief**: Use concise language to define Claude's role and constraints
- **Focus on the framework**: Use system prompts for persistent instructions that apply to the entire conversation
- **Define clear roles**: Specify Claude's persona or expert role clearly
- **Set boundaries**: Establish response constraints and formatting requirements
- **Avoid excessive restrictions**: Don't overload with so many constraints that Claude becomes overcautious
- **Separate concerns**: Put task-specific details in user messages, not system prompts
- **Be specific about format**: If you need a particular output format, define it clearly
- **Maintain neutrality**: Avoid biasing Claude's responses when setting the role

## Strategic Response Prefilling
- **Guide output structure**: Use prefilling to establish a specific format or template
- **Set clear boundaries**: Use XML tags like `<assistant>` to indicate where Claude should continue
- **Provide partial content**: Include the beginning of headings, lists, or tables
- **Format-specific templates**: For JSON, code, or tabular outputs, provide the initial structure
- **Start and stop**: For long formats, you can prefill both the beginning and end
- **Combine with instructions**: Pair prefilling with clear directions about the content
- **Minimal but sufficient**: Include just enough structure to make the format clear
- **Avoid overconstraining**: Leave room for Claude to provide substantial content

## Effective Chain Prompting
- **Break down complex tasks**: Split multi-stage processes into separate, sequential prompts
- **Define clear outputs**: Specify what each step should produce for the next step
- **Preserve context**: Carry forward necessary information between steps
- **Progressive refinement**: Use earlier steps to generate drafts and later steps to improve them
- **Specialized instructions**: Provide stage-specific guidance for each step
- **Error handling**: Build in verification or human review between critical steps
- **Consistent formatting**: Maintain format compatibility between steps
- **Handle limitations**: Use chaining to work around context window constraints

## Resources
- [Anthropic Prompt Improver](https://www.anthropic.com/news/prompt-improver)
- [Claude 4 Best Practices](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/claude-4-best-practices)
- [Be Clear and Direct](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/be-clear-and-direct)
- [Multishot Prompting](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/multishot-prompting)
- [Chain-of-Thought](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/chain-of-thought)
- [System Prompts](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/system-prompts)
- [Prefill Claude's Response](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/prefill-claudes-response)
- [Chain Prompts](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/chain-prompts)
- [Long Context Tips](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/long-context-tips)
- [Extended Thinking Tips](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/extended-thinking-tips)
- [Claude Prompt Engineering Guidelines](https://docs.anthropic.com/claude/docs/introduction-to-prompt-design)

Remember: With Claude 4, less is often more. Focus on clear, direct instructions rather than elaborate prompting techniques.