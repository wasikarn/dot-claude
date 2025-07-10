# Prompt Improver

## Purpose
This command analyzes and enhances prompts using Anthropic's Prompt Improver methodology, implementing industry best practices to significantly improve Claude's response quality and reasoning.

## Usage
```
/prompt-improver "Your prompt here"
```
Or
```
/prompt-improver #file:path/to/prompt.md
```

## Prompt to improve: $ARGUMENTS

I'll analyze and enhance the provided prompt through a systematic improvement process, applying Anthropic's best practices for Claude's optimal performance.

## Analysis Process

1. **Prompt Structure Analysis**
   - Identify the core purpose and goals of the prompt
   - Determine strengths and weaknesses in the current structure
   - Identify missing elements that would improve reasoning
   - Assess whether the prompt would benefit from standardized examples
   - Evaluate if the prompt aligns with Claude's capabilities

2. **Chain-of-Thought Enhancement**
   - Add explicit reasoning steps using the IDEAL framework
   - Create dedicated sections for systematic problem analysis
   - Add verification checkpoints for accuracy and completeness
   - Include intermediate reasoning steps to improve reliability
   - Ensure balance between reasoning and direct responses

3. **Example Standardization and Enrichment**
   - Convert examples to consistent XML format for better processing
   - Add chain-of-thought reasoning to examples to demonstrate ideal thinking
   - Ensure input/output patterns are clear and consistent
   - Enhance examples with edge cases where appropriate
   - Demonstrate error handling in examples

4. **Context Engineering Integration**
   - Add relevant documentation references where helpful
   - Include domain-specific knowledge needed for the task
   - Structure prompt to provide necessary context without overloading
   - Ensure appropriate level of detail for the task complexity

5. **Validation Strategy Implementation**
   - Add self-verification mechanisms
   - Include output validation criteria
   - Incorporate error handling approaches
   - Provide recovery paths for potential failures

## Improvement Strategy

### Structured Reasoning Framework
Add a dedicated section for Claude to:
```
<thinking>
  1. Identify the problem precisely: [Break down the specific issue]
  2. Define constraints and requirements: [List technical constraints]
  3. Explore potential strategies: [Generate multiple approaches]
  4. Act on the best strategy: [Implement the solution with attention to detail]
  5. Look back and learn: [Verify solution against requirements and evaluate effectiveness]
</thinking>
```

### Example Standardization
Convert examples to a consistent format with explicit reasoning:

**Before:**
```
User: How do I calculate compound interest?
Assistant: The formula is A = P(1 + r/n)^(nt)
```

**After:**
```xml
<example>
  <user>How do I calculate compound interest?</user>

  <assistant>
    <thinking>
      1. Identify: User needs to calculate compound interest
      2. Define: Need the formula and explanation of variables
      3. Explore: Could provide formula only, explain with example, or create a calculator
      4. Act: Will provide formula with explanation and a simple example
      5. Look back: Ensuring all variables are explained clearly
    </thinking>

    To calculate compound interest, you can use this formula:

    A = P(1 + r/n)^(nt)

    Where:
    - A = Final amount
    - P = Principal (initial investment)
    - r = Annual interest rate (decimal)
    - n = Compounding frequency per year
    - t = Time in years

    Example: $1,000 invested at 5% compounded monthly for 5 years:
    A = 1000(1 + 0.05/12)^(12×5) = $1,283.36
  </assistant>
</example>
```

### Validation Loops
Incorporate self-checking mechanisms:

```xml
<validation>
  <requirement>Solution must handle negative numbers</requirement>
  <test-case>
    <input>-500 principal, 5% interest</input>
    <expected>Error: Principal cannot be negative</expected>
  </test-case>
  <verification>
    I've verified the solution handles this edge case by explicitly checking for negative values and returning an appropriate error message.
  </verification>
</validation>
```

### Prefilled Assistant Message
Add a template to guide Claude's responses:

```
I'll help you with this request using systematic reasoning.

<thinking>
1. Identify the problem: [Analyze the specific request]
2. Define constraints: [Identify any limitations or requirements]
3. Explore approaches: [Consider multiple solution paths]
4. Choose best approach: [Select the most appropriate solution]
5. Verify solution: [Check against requirements and constraints]
</thinking>

Based on my analysis, here's my solution:
[Clear, well-structured response that addresses the user's request]
```

## Implementation

### Original Prompt
```
$ARGUMENTS
```

### Enhanced Prompt
[The enhanced prompt will be generated here with all improvements applied]

## Verification Checklist
- [ ] Chain-of-thought reasoning sections added
- [ ] Examples converted to consistent XML format
- [ ] Examples enriched with reasoning steps
- [ ] Clear structure and organization
- [ ] Validation mechanisms implemented
- [ ] Prefilled assistant message included
- [ ] Grammar and spelling errors corrected
- [ ] Original intent and requirements preserved
- [ ] Edge cases addressed
- [ ] Prompt length optimized for context window

Prompt improvement score: [1-10] based on comprehensiveness of enhancements

## Benefits of Enhanced Prompt
- More reliable and systematic reasoning
- Reduced likelihood of hallucinations
- Improved handling of complex problems
- Consistent response structure
- Better alignment with user expectations
- Easier debugging of model reasoning
- Increased robustness through validation
- More comprehensive context for accurate responses

## Prompt Efficiency Considerations
- Removed unnecessary verbosity
- Prioritized critical information
- Balanced detail with conciseness
- Optimized for Claude's context window
- Structured for easy comprehension

The enhanced prompt guides Claude through explicit reasoning steps before arriving at a conclusion, incorporating validation mechanisms to ensure high-quality, reliable, and accurate responses.