# Nuts Orchestration AI Agent

> **Project Overview Notice:**  
> This repository serves as a high-level project overview for **Nuts**, an advanced AI agent system. The codebase is not included at this stage, as the project is still in active development. The full source code will be released upon project completion. In the meantime, this repository contains essential information about the project’s goals, architecture, and functionality.

---

Welcome to **Nuts**, an autonomous AI agent designed to streamline complex tasks by orchestrating multiple AI components and tools. Nuts leverages advanced memory management, dynamic skill generation, and personalized user interactions to provide efficient and adaptive assistance.

## Table of Contents

- [Features](#features)
- [System Overview](#system-overview)
  - [Key Components](#key-components)
    - [MetaPrompt](#metaprompt)
    - [Skill System](#skill-system)
    - [Memory Management System](#memory-management-system)
  - [Additional Components](#additional-components)
    - [Brain Agent](#brain-agent)
    - [Planner](#planner)
    - [Vision-Language Model (VLM) Expert](#vision-language-model-vlm-expert)
    - [Cognitive Task Agent](#cognitive-task-agent)
    - [Memory Processing Agent](#memory-processing-agent)
- [Feature Status](#feature-status)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#usage)
  - [Interacting with Nuts](#interacting-with-nuts)
  - [Monitoring and Managing Memory](#monitoring-and-managing-memory)
- [Training and Fine-Tuning](#training-and-fine-tuning)
  - [Autonomous Fine-Tuning](#autonomous-fine-tuning)
  - [Optional User Fine-Tuning](#optional-user-fine-tuning)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Dynamic Task Execution**: Processes user input to determine and execute appropriate tasks using dynamically generated skills.
- **Advanced Memory Management**: Manages memory efficiently, summarizing interactions and storing relevant data for future use.
- **MetaPrompt Influence**: Utilizes a MetaPrompt to guide skill generation based on learned user preferences.
- **Skill Learning System**: Learns how to perform any task by creating and refining skills autonomously.
- **Continuous Self-Fine-Tuning**: Autonomously fine-tunes itself after each session, learning from interactions to enhance future performance.
- **Visual Interaction Handling**: Interprets visual data through the VLM Expert for tasks requiring visual input.
- **User Personalization**: Adapts to individual user preferences, providing a tailored experience.

## System Overview

### Key Components

Nuts comprises three main parts:

1. **MetaPrompt**: Influences skill generation based on learned user preferences.
2. **Skill System**: Allows the AI to learn how to perform any task by creating and refining skills.
3. **Memory Management System**: Determines how and where memory is stored and retrieved, including short-term memory cache, long-term memory cache, and an SQL database.

#### MetaPrompt

The **MetaPrompt** structures user input into organized categories, guiding the Brain Agent in understanding user intent and influencing skill generation.

- **Layered Information Extraction**:
  - **Layer 1**: Focuses on explicit information such as context, constraints, and content.
  - **Layer 2**: Extracts implicit information like emotions, social dynamics, and decision-making factors.
- **Current Status**:
  - **Completed**: MetaPrompt is implemented and operational in a static form.
  - **In Progress**: Enhancing the MetaPrompt to dynamically adapt based on user preferences is underway.

#### Skill System

The **Skill System** enables Nuts to learn and perform tasks by:

- **Autonomous Skill Creation**: Generates new skills based on user needs, without relying on pre-built tools.
- **Skill Structure**: Each skill has a name, description, and a sequence of steps.
- **Expert Clustering**: Groups similar skills into experts for efficient retrieval and to reduce redundancy.
- **Iterative Refinement**: Collaborates with the user to refine skills, ensuring alignment with user preferences.

#### Memory Management System

Nuts manages memory through:

- **Short-Term Memory (STM) Cache**: Stores frequently accessed information during a session.
- **Long-Term Memory (LTM) Cache**: Holds summarized data from STM that's less frequently accessed.
- **SQL Database**: Archives all interactions, thoughts, and skills for future retrieval.

- **Current Status**:
  - **Completed**: Memory storage in the SQL database is fully implemented. The system parses `<thought></thought>` tags and stores them effectively. Vector searches on stored thoughts are functional.
  - **In Progress**: Implementing the memory caching system, including weighing skills and determining which ones remain in STM, move to LTM, or get archived.

### Additional Components

#### Brain Agent

The **Brain Agent** is the core processing unit responsible for:

- Analyzing user input and context using the MetaPrompt.
- Retrieving relevant memories.
- Generating and assigning dynamic skills for task completion.

#### Planner

The **Planner** coordinates task execution by:

- Breaking down tasks into discrete steps.
- Assigning relevant skills from expert clusters to each step.
- Collaborating with the Brain Agent and VLM Expert for iterative task refinement.

#### Vision-Language Model (VLM) Expert

The **VLM Expert** handles tasks requiring visual input by:

- Interpreting screenshots or visual data.
- Executing skill steps based on real-time visual information.
- Interacting with the Planner to refine actions according to user feedback.

- **Current Status**:
  - **In Progress**: Setting up the VLM Expert is in development.

#### Cognitive Task Agent

The **Cognitive Task Agent** operates autonomously after user sessions to:

- Prepare skills based on session history and user preferences.
- Anticipate future user needs.
- Reduce cognitive load on the user by preemptively performing tasks.

#### Memory Processing Agent

The **Memory Processing Agent**:

- **Purpose**: Fine-tunes the MetaTopics and categories within the MetaPrompt based on user preferences, making the MetaPrompt dynamic.
- **Current Status**:
  - **In Progress**: Developing the agent to dynamically update the MetaPrompt based on stored user interactions.

## Feature Status

| Feature                                                     | Status          |
|-------------------------------------------------------------|-----------------|
| **MetaPrompt (Static)**                                     | **Completed**   |
| MetaPrompt (Dynamic based on user preferences)              | **In Progress** |
| **Memory Storage in SQL Database**                          | **Completed**   |
| Memory Caching System (STM, LTM, Archiving)                 | **In Progress** |
| VLM Expert Setup                                            | **In Progress** |
| Memory Processing Agent (Dynamic MetaPrompt)                | **In Progress** |
| Skill System                                                | **Completed**   |
| Brain Agent                                                 | **Completed**   |
| Planner                                                     | **Completed**   |
| Cognitive Task Agent                                        | **Planned**     |

## Getting Started

### Prerequisites

- **Python 3.x**
- Required Python libraries (see `requirements.txt`)
- An SQL database setup for long-term memory storage

### Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/xrgpubluc/TheOrchestrator.git
   cd TheOrchestrator
   ```

2. **Install Dependencies**

   ```bash
   pip install -r requirements.txt
   ```

3. **Configure the Environment**

   - Set up the SQL database and update the connection details in the configuration file.
   - Configure any API keys or tokens required for external services.

## Usage

### Interacting with Nuts

1. **Run the Main Application**

   ```bash
   python main.py
   ```

2. **Provide Input**

   - Interact with Nuts via the command line, GUI, or integrated platform (e.g., Discord bot).
   - Input your requests or tasks in natural language.

3. **Processing**

   - The Brain Agent analyzes your input using the MetaPrompt.
   - Skills are generated or retrieved based on your needs.
   - Tasks are planned and executed using the Planner and relevant skills.
   - For visual tasks, the VLM Expert processes visual data as needed.

4. **Receive Output**

   - Nuts provides responses or completes tasks based on your input.
   - The system learns from each interaction to improve future performance.

### Monitoring and Managing Memory

- **Memory Growth**: The SQL database will grow over time as Nuts records interactions.
- **Manual Pruning**: Currently, there is no automatic pruning or memory removal. Users may need to interact with the SQL database to remove outdated or unwanted responses.
- **Data Management Tools**: Consider implementing or using database management tools to monitor and maintain the SQL database.

## Training and Fine-Tuning

### Autonomous Fine-Tuning

Nuts autonomously fine-tunes itself after each session by:

- Learning from user interactions.
- Updating skills and memory based on user preferences.
- Enhancing task performance and efficiency over time.

### Optional User Fine-Tuning

While Nuts self-optimizes, users have the option to:

- **Provide Additional Datasets**: Enhance Nuts' understanding by supplying custom datasets.
- **Modify the MetaPrompt**: Tailor the MetaPrompt to better suit specific use cases.
- **Adjust Skill Definitions**: Refine or create skills to improve task execution.

#### Fine-Tuning Process

1. **Review the Brain Prompt and Datasets**

   - Understand the structure and categories used for analysis.
   - Examine sample datasets to see how user inputs are processed.

2. **Customize Training Data**

   - Add or modify datasets to include scenarios relevant to your use case.
   - Ensure data diversity to improve the model's adaptability.

3. **Run Fine-Tuning Scripts**

   - Use the provided scripts to fine-tune Nuts with your datasets.
   - Monitor training for any issues or required adjustments.

## Contributing

We welcome contributions to enhance Nuts! Please follow these steps:

1. **Fork the Repository**

   - Create a personal fork and clone it to your local machine.

2. **Create a Feature Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make Changes and Commit**

   - Implement your feature or fix.
   - Commit your changes with descriptive messages.

4. **Push to Your Fork and Submit a Pull Request**

   ```bash
   git push origin feature/your-feature-name
   ```

   - Open a pull request against the main repository.

5. **Review Process**

   - Collaborate with maintainers during the review.
   - Make any necessary changes based on feedback.

## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details.

---

**Note**: Nuts is a powerful tool that continuously evolves. Regularly monitor its performance and memory usage to ensure it aligns with your requirements.

---

## Acknowledgements

- **Creator**: xrgpu
- **Contributors**: Open to community contributions.

---

If you have any questions or need assistance, feel free to open an issue or reach out to the maintainers.

# Additional Notes

- **Memory Management Enhancements**: Future updates will include implementing the memory caching system to weigh and determine which skills remain in the short-term memory cache, move to the long-term memory cache, or get archived.

- **Dynamic MetaPrompt**: Work is ongoing to make the MetaPrompt dynamic by integrating user preferences gathered through interactions, managed by the Memory Processing Agent.

- **VLM Expert Setup**: Development is in progress to set up the Vision-Language Model Expert, which will enhance Nuts' capability to handle tasks requiring visual inputs.

---

Thank you for choosing Nuts! We are committed to continuous improvement and value your feedback.

---

# Changelog

- **Version 0.1**
  - Implemented static MetaPrompt.
  - Completed memory storage in SQL database with vector search capabilities.
  - Set up the Skill System for autonomous skill generation and execution.
  - Brain Agent, Planner, and basic components are operational.
  - Began development on Memory Caching System, VLM Expert, and Memory Processing Agent.

---

# Contact

For support or inquiries:

- **Email**: none
- **GitHub Issues**: [GitHub Repository](https://github.com/xrgpublic/TheOrchestrator/issues)

---

*This README was last updated on [Current Date].*
