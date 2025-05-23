# API Configuration Profiles

API Configuration Profiles allow you to create and switch between different sets of AI settings. Each profile can have different configurations for each mode, letting you optimize your experience based on the task at hand.

:::info
Having multiple configuration profiles lets you quickly switch between different AI providers, models, and settings without reconfiguring everything each time you want to change your setup.
:::
## How It Works

Configuration profiles can have their own:
- API providers (OpenAI, Anthropic, OpenRouter, Glama, etc.)
- API keys and authentication details
- Model selections (o3-mini-high, Claude 3.7 Sonnet, DeepSeek R1, etc.)
- [Temperature settings](/features/model-temperature) for controlling response randomness
- Thinking budgets
- Provider-specific settings

Note that available settings vary by provider and model. Each provider offers different configuration options, and even within the same provider, different models may support different parameter ranges or features.

## Creating and Managing Profiles

### Creating a Profile

1. Open Settings by clicking the gear icon <Codicon name="gear" /> → Providers
2. Click the "+" button next to the profile selector

   <img src="/img/api-configuration-profiles/api-configuration-profiles-1.png" alt="Profile selector with plus button" width="550" />
3. Enter a name for your new profile
   
   <img src="/img/api-configuration-profiles/api-configuration-profiles.png" alt="Creating a new profile dialog" width="550" />
4. Configure the profile settings:
   - Select your API provider
      
      <img src="/img/api-configuration-profiles/api-configuration-profiles-2.png" alt="Provider selection dropdown" width="550" />
   - Enter API key
   
      <img src="/img/api-configuration-profiles/api-configuration-profiles-3.png" alt="API key entry field" width="550" />
   - Choose a model
   
      <img src="/img/api-configuration-profiles/api-configuration-profiles-8.png" alt="Model selection interface" width="550" />
   - Adjust model parameters
   
      <img src="/img/api-configuration-profiles/api-configuration-profiles-5.png" alt="Model parameter adjustment controls" width="550" />

### Switching Profiles

Switch profiles in two ways:
1. From Settings panel: Select a different profile from the dropdown

   <img src="/img/api-configuration-profiles/api-configuration-profiles-7.png" alt="Profile selection dropdown in Settings" width="550" />
2. During chat: Access the API Configuration dropdown in the chat interface

   <img src="/img/api-configuration-profiles/api-configuration-profiles-9.png" alt="API Configuration dropdown in chat interface" width="550" />

### Editing and Deleting Profiles

<img src="/img/api-configuration-profiles/api-configuration-profiles-10.png" alt="Profile editing interface" width="550" />
- Select the profile in Settings to modify any settings
- Click the pencil icon to rename a profile
- Click the trash icon to delete a profile (you cannot delete the only remaining profile)

## Linking Profiles to Modes
In the <Codicon name="notebook" /> Prompts tab, you can explicitly associate a specific Configuration Profile with each Mode. The system also automatically remembers which profile you last used with each mode, making your workflow more efficient.
<img src="/img/api-configuration-profiles/api-configuration-profiles-11.png" alt="Profile-Mode association interface in Prompts tab" width="550" />

## Security Note

API keys are stored securely in VSCode's Secret Storage and are never exposed in plain text.

## Related Features

- Works with [custom modes](/features/custom-modes) you create
- Integrates with [local models](/advanced-usage/local-models) for offline work
- Supports [temperature settings](/features/model-temperature) per mode
- Enhances cost management with [rate limits and usage tracking](/advanced-usage/rate-limits-costs)

