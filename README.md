# Programming, Mathematics, and AI Learning Journey

This repository records my learning path from programming fundamentals through the mathematics of machine learning, deep learning, and generative AI. It combines concise reference notes, executable notebooks, and applied projects.

![AI to Chatgpt](/media/ai-to-chatgpt-concept.png)

- AI: It is the broader concept of machine minicking human intelligence
- ML: A subset of AI where machines learn from data without explicit programming
- DL: A subset of ML that uses multi-layered  neural networks for complex data
- GenAI: Is a type of AI that creates new content often levereging DL
- LLM: 

## How to use this repository

Follow the subjects in roadmap order. Use the three layers according to the depth you need:

1. Start here for the learning sequence and a quick progress overview.
2. Open [notes](notes/README.md) for searchable theory, definitions, equations, and image transcriptions.
3. Open [notebooks](notebooks/README.md) for executable lessons in which the theory appears next to the code that uses it.
4. Open [projects](projects/README.md) to see several concepts combined in a practical implementation.

The notebooks remain self-contained: detailed notes add depth, but they are not required in order to follow the code.

## Progress dashboard

The status describes the material currently present in the repository; it does not claim mastery.

| Stage | Subject | Repository status | Main material |
| ---: | --- | --- | --- |
| 1 | Python programming | Notes recorded | [Python notes index](notes/01-programming/README.md) |
| 2 | Algorithms and data structures | Notebook available | [Algorithms notebook](notebooks/01-programming/07-algorithms-and-data-structures.ipynb) |
| 3 | Linear algebra | Notebooks and notes available | [Mathematics notes](notes/02-mathematics/mathematical-foundations.md) |
| 4 | Calculus and optimization | Notebooks and notes available | [Mathematics notebooks](notebooks/02-mathematics/) |
| 5 | Probability and statistics | Notebooks available | [Mathematics notebooks](notebooks/02-mathematics/) |
| 6 | Machine learning | Foundations recorded | [Mathematics and ML notes](notes/02-mathematics/mathematical-foundations.md) |
| 7 | Deep learning | TensorFlow examples available | [Deep-learning notebooks](notebooks/04-deep-learning/) |
| 8 | Reinforcement learning | Notes and project available | [RL notes](notes/03-artificial-intelligence/artificial-intelligence-and-reinforcement-learning.md) |
| 9 | Generative AI | Notes and API example available | [Generative AI notes](notes/04-generative-ai/generative-ai.md) |

## Learning roadmap

```text
Programming foundations
    -> Algorithms and data structures
    -> Linear algebra + calculus + probability + statistics
    -> Optimization and classical machine learning
    -> Neural networks and deep learning
    -> Reinforcement learning
    -> Transformers, LLMs, RAG, evaluation, and agentic AI
```

The mathematics subjects reinforce one another rather than forming a perfectly linear sequence. For example, optimization uses calculus and linear algebra, while machine-learning evaluation uses probability and statistics.

## Repository map

```text
.
├── README.md                     # Roadmap and progress dashboard
├── notes/                        # Searchable conceptual reference
│   ├── 01-programming/
│   ├── 02-mathematics/
│   ├── 03-artificial-intelligence/
│   └── 04-generative-ai/
├── notebooks/                    # Executable, self-contained lessons
│   ├── 01-programming/
│   ├── 02-mathematics/
│   ├── 04-deep-learning/
│   └── 05-generative-ai/
├── projects/                     # Applied work combining several topics
├── media/                        # Diagrams and visual notes
└── setup/                        # Local development-environment instructions
```

## Environment setup

The original Intel MacBook, Miniconda, TensorFlow, VS Code, and IntelliJ setup instructions were moved without changing their contents:

- [Local data science and GenAI environment setup](setup/DATAS-ENV-SETUP.md)

## Progress convention

When updating this repository, use these labels consistently:

- `Planned`: topic identified but not yet studied.
- `Learning`: notes or experiments are in progress.
- `Practiced`: an executable notebook or exercise is complete.
- `Applied`: the concept is used in a project.
- `Reviewed`: the material was revisited and can be explained without relying on the source.

For a meaningful measure of progress, record capabilities rather than only completed courses—for example, “implement gradient descent from scratch” or “explain why an eigenvector keeps its direction under a transformation.”
