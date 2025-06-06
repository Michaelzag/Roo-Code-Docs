# Adjusting Model Temperature

Temperature controls the randomness of AI model outputs. Adjusting this setting optimizes results for different tasks - from precise code generation to creative brainstorming. Temperature is one of the most powerful parameters for controlling AI behavior. A well-tuned temperature setting can dramatically improve the quality and appropriateness of responses for specific tasks.

## What is Temperature?

Temperature is a parameter that controls the randomness of the model's predictions. It's typically a value between 0.0 and 2.0, depending on the model.


:::info Common Misconceptions About Temperature Specifically Relating to Coding
Temperature settings in large language models (LLMs) significantly influence coding outputs, primarily by controlling randomness rather than directly affecting code quality. Here are several common misconceptions clarified:

**Lower Temperature Equals Better Code:** A very low temperature (close to zero) leads to deterministic outputs, resulting in predictable, repetitive, and potentially overly simplistic code. It does not inherently improve the quality of solutions.

**Higher Temperature Generates Higher-Quality Code:** Increasing temperature introduces more randomness, which can lead to novel or creative solutions but also heightens the risk of errors, convoluted logic, or nonsensical variable names. Higher randomness does not equate to improved code quality.

**Temperature Directly Impacts Coding Accuracy:** Temperature does not directly affect accuracy or correctness of programming logic. The accuracy of code generated by the model is dependent on its training and the clarity of the prompt provided, rather than the randomness introduced by temperature adjustments.

**Temperature Zero is Always Ideal for Coding:** While a temperature of zero is beneficial for consistent, repeatable solutions suitable for basic examples or straightforward tasks, it can limit creativity and exploration for more complex coding challenges.
:::

Ultimately, selecting an optimal temperature setting involves balancing deterministic responses and creative exploration. Moderate temperatures, typically ranging from 0.3 to 0.7, often offer the best balance for many coding scenarios, though ideal settings may vary based on specific task requirements and desired outcomes.

## Default Values in Roo Code

Roo Code uses a default temperature of 0.0 for most models, optimizing for maximum determinism and precision in code generation. This applies to OpenAI models, Anthropic models (non-thinking variants), LM Studio models, and most other providers.

Some models use higher default temperatures - DeepSeek R1 models and certain reasoning-focused models default to 0.6, providing a balance between determinism and creative exploration.

Models with thinking capabilities (where the AI shows its reasoning process) require a fixed temperature of 1.0 which cannot be changed, as this setting ensures optimal performance of the thinking mechanism. This applies to any model with the ":thinking" flag enabled.

Some specialized models don't support temperature adjustments at all, in which case Roo Code respects these limitations automatically.

## When to Adjust Temperature

Here are some examples of temperature settings that might work well for different tasks:

*   **Code Mode (0.0-0.3):** For writing precise, correct code with consistent, deterministic results
*   **Architect Mode (0.4-0.7):** For brainstorming architecture or design solutions with balanced creativity and structure
*   **Ask Mode (0.7-1.0):** For explanations or open-ended questions requiring diverse and insightful responses
*   **Debug Mode (0.0-0.3):** For troubleshooting bugs with consistent precision

These are starting points – it's important to [experiment with different settings](#experimentation) to find what works best for your specific needs and preferences.

## How to Adjust Temperature

1.  **Open the Roo Code Panel:** Click the Roo Code icon (<Codicon name="rocket" />) in the VS Code Activity Bar
2.  **Open Settings:** Click the <Codicon name="gear" /> icon in the top right corner
3.  **Find Temperature Control:** Navigate to the Providers section
4.  **Enable Custom Temperature:** Check the "Use custom temperature" box
5.  **Set Your Value:** Adjust the slider to your preferred value

    <img src="/img/model-temperature/model-temperature.png" alt="Temperature setting in Roo Code settings panel" width="550" />
    *Temperature slider in Roo Code settings panel*

## Using API Configuration Profiles for Temperature

Create multiple [API configuration profiles](/features/api-configuration-profiles) with different temperature settings:

**How to set up task-specific temperature profiles:**

1. Create specialized profiles like "Code - Low Temp" (0.1) and "Ask - High Temp" (0.8)
2. Configure each profile with appropriate temperature settings
3. Switch between profiles using the dropdown in settings or chat interface
4. Set different profiles as defaults for each mode for automatic switching when changing modes

This approach optimizes model behavior for specific tasks without manual adjustments.

## Technical Implementation

Roo Code implements temperature handling with these considerations:

*   User-defined settings take priority over defaults
*   Provider-specific behaviors are respected
*   Model-specific limitations are enforced:
    *   Thinking-enabled models require a fixed temperature of 1.0
    *   Some models don't support temperature adjustments

## Experimentation

Experimenting with different temperature settings is the most effective way to discover what works best for your specific needs:

### Effective Temperature Testing

1. **Start with defaults** - Begin with Roo Code's preset values (0.0 for most tasks) as your baseline
2. **Make incremental adjustments** - Change values in small steps (±0.1) to observe subtle differences
3. **Test consistently** - Use the same prompt across different temperature settings for valid comparisons
4. **Document results** - Note which values produce the best outcomes for specific types of tasks
5. **Create profiles** - Save effective settings as [API configuration profiles](/features/api-configuration-profiles) for quick access

Remember that different models may respond differently to the same temperature values, and thinking-enabled models always use a fixed temperature of 1.0 regardless of your settings.

## Related Features

- Works with all [API providers](/providers/openai) supported by Roo Code
- Complements [custom instructions](/features/custom-instructions) for fine-tuning responses
- Works alongside [custom modes](/features/custom-modes) you create