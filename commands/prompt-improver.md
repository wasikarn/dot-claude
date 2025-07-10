# Prompt Improver

## Purpose
This command analyzes and enhances prompts for Claude, applying Anthropic's best practices to improve response quality while optimizing for small context windows and cost efficiency.

## Usage
```
/prompt-improver "Your prompt here"
```

## Prompt to improve: $ARGUMENTS

I'll enhance your prompt focusing on clarity, efficiency, and best practices for Claude Code.

## Analysis Process

1. **Structure & Intent**
   - Identify core purpose and goals
   - Assess strengths and weaknesses
   - Check alignment with Claude's capabilities

2. **Reasoning Enhancement**
   - Add concise reasoning steps where needed
   - Include verification checkpoints
   - Balance reasoning with direct responses

3. **Example Optimization**
   - Format examples consistently
   - Demonstrate ideal input/output patterns
   - Include key edge cases only when necessary

4. **Context Efficiency**
   - Include only essential context
   - Remove unnecessary details
   - Structure for minimal token usage

5. **Validation Strategy**
   - Add lightweight verification mechanisms
   - Focus on critical error handling only

## Improvement Strategy

### Concise Reasoning Framework
```
<thinking>
  • Problem: [Core issue]
  • Approach: [Solution strategy]
  • Verification: [Key validation point]
</thinking>
```

### Efficient Example Format
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
    Compound interest formula: A = P(1 + r/n)^(nt)

    Where:
    • A: Final amount
    • P: Principal
    • r: Annual rate (decimal)
    • n: Compounds per year
    • t: Time in years

    Example: $1,000 at 5% monthly for 5 years = $1,283.36
  </assistant>
</example>
```

### Simple Validation
```
<check>
• Does solution address core request?
• Are edge cases handled appropriately?
• Is explanation clear and concise?
</check>
```

### Streamlined Response Template
```
I'll address your request efficiently.

<thinking>Problem: [Brief analysis]</thinking>

[Concise, direct solution that addresses the user's request]
```

## Implementation

### Original Prompt
```
$ARGUMENTS
```

### Enhanced Prompt
[Improved prompt with efficient structure]

## Verification Checklist
- [ ] Essential reasoning included
- [ ] Examples formatted efficiently
- [ ] Clear structure maintained
- [ ] Original intent preserved
- [ ] Context size optimized
- [ ] Token usage minimized

Prompt efficiency score: [1-10]

## Benefits of Enhanced Prompt
- Efficient token usage and reduced costs
- Focused reasoning for complex problems
- Consistent, streamlined responses
- Improved error handling for edge cases
- Faster processing with smaller context
- Better alignment with Claude Code capabilities

## Context & Cost Optimization
- Eliminated unnecessary details
- Retained only essential instructions
- Minimized token usage
- Optimized for smaller context windows
- Structured for maximum efficiency

The enhanced prompt guides Claude to deliver accurate, efficient responses while minimizing token usage and processing time.