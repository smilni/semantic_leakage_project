# Color-related leakage-provoking prompts dataset and generations datasets

## Overview

The dataset builds on previous work by Gonen et al. (2024) and expands the study of semantic leakage in the following ways:

1. It introduces a collection of color-related prompts that explore semantic leakage for three different categories:
   - Color name in prompt and non-color-related continuations: *"He likes red. He works as a... **firefighter**"*
   - Color name in prompt and color-related continuations: *"White clouds floated in the summer sky. The fence was painted... **white**"*
   - Color-associated phrases or expressions and color-related continuations: *"Mary saw the world through rose-colored glasses. Her T-shirt was... **pink**"*
2. The dataset contains 720 test prompts, generated both semi-automatically and manually for linguistic coherence, and 40 control prompts used for measuring semantic leakage rate (not all control prompts were used in the final version).


## Dataset Structure

The dataset is presented in an Excel file. It has the following features:

- **`template_id`**: Identifier for the prompt template (24 templates in total).
- **`template`**: The prompt template.
- **`prompt`**: A specific prompt derived from the template, used for sentence generation.
- **`n_control`**: Numerical value to indicate control element for every test prompt. Not provided for control elements.
- **`concept`**: The concept or expression inserted into the template.
- **`inserted_item_type`**: The type of the inserted concept (e.g., color, secondary color, color_related).
- **`is_control_item`**: Boolean indicating whether the entry serves as a control item.
- **`expected_generation_type`**: The type of sentence generation expected (e.g., color, color-related).
- **`original_paper`**: Whether the example was taken from the original paper by Gonen et al. (2024) ("yes" or "no").
- **`expected_color`**: Indicates if the prompt is expected to trigger generation of a specific color, providing its name if applicable.
- **`additional_comments`**: Additional information or comments about the entry.
- **`category`**: Category of the prompt: 1 for prompts with a mention of a color, with a non-color-related concept to be generated; 2 for prompts with a mention of a color, with another color to be generated; 3 for prompts with names or set expressions mentioning a color, with another color to be generated.

## Generations Datasets

In generation_results/color_prompts folder, you may find the generations produced by Qwen2.5-0.5B-Instruct, Qwen2.5-1.5B-Instruct, Qwen2.5-3B-Instruct, and Qwen2.5-7B-Instruct-GPTQ-Int4. Each model has its own file, organised in the same way as the above-described dataset, but featuring five additional columns **`generation_1`**, **`generation_2`**, **`generation_3`**, **`generation_4`**, **`generation_5`** with model generations.

Additionally, you may refer to generation_results/initial_prompts to examine Qwen2.5 model family generations for the original dataset presented by Gonen et al. (2024).