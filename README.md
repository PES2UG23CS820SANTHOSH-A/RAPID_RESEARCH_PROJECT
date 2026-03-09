AI for Hardware Programming
Overview

This project explores how Large Language Models (LLMs) can assist in hardware programming and industrial robotics development. The goal is to generate hardware control code from natural language instructions using fine-tuned AI models.

The project focuses on two domains:

Arduino (Embedded Systems Programming)

KUKA Industrial Robot Programming (KRL)

Two different models were fine-tuned using LoRA and PEFT techniques on custom datasets to generate domain-specific hardware code.

Models Used
1. DeepSeek Coder – Arduino Code Generation

The DeepSeek Coder model is fine-tuned to generate Arduino programs from natural language prompts.

Example tasks:

LED control

Sensor integration

Motor control

Basic automation tasks

Fine-tuning method:

LoRA (Low Rank Adaptation)

PEFT (Parameter Efficient Fine Tuning)

The model learns from prompt-to-code examples to generate Arduino sketches.

2. Microsoft Phi-2 – KUKA Robot Programming

The Microsoft Phi-2 model is fine-tuned to generate KUKA Robot Language (KRL) programs.

The system generates robot motion commands and IO operations from simple task descriptions.

Example capabilities:

Robot motion commands (PTP, LIN)

IO control

Pick and place automation

Industrial robot task programming

Example output:

PTP HOME
LIN PICK_POS
$OUT[1] = TRUE
LIN PLACE_POS
$OUT[1] = FALSE
Fine-Tuning Approach

Both models were fine-tuned using Parameter Efficient Fine-Tuning (PEFT).

Training techniques used:

LoRA adapters

HuggingFace Transformers

PyTorch

Google Colab GPU

Advantages:

Reduced GPU memory requirements

Faster training

Efficient domain adaptation

Dataset

The dataset contains hardware programming examples structured as:

Task description

Motion instructions (for robotics)

IO commands

Expected hardware control code

Example structure used for the KUKA model:

### Prompt:
Task: Pick object and place it on conveyor
Motions: PTP, LIN
IO Actions:
OUT[1] ON

### KRL_Code:
PTP HOME
LIN PICK_POS
$OUT[1] = TRUE
LIN PLACE_POS
$OUT[1] = FALSE
Repository Structure
RAPID_RESEARCH_PROJECT
│
├── DeepSeek_Arduino_Finetuning.ipynb
├── Phi2_KUKA_Finetuning.ipynb
└── datasets

The repository contains:

Arduino fine-tuning notebook

KUKA robot programming fine-tuning notebook

Custom dataset used for training

Technologies Used

Python

PyTorch

HuggingFace Transformers

PEFT

LoRA

Google Colab

Hardware Domains:

Arduino

Industrial Robotics

KUKA KRL Programming

Applications

This approach can help in:

AI assisted robotics programming

Embedded system development

Industrial automation

Hardware code generation

Robotics education and rapid prototyping

Future Improvements

Possible future extensions include:

ROS based robotics programming

Support for additional robot languages

Multi-robot task planning

Integration with real hardware control systems

Author

Santhosh A
PES University
SRN: PES2UG23CS820
