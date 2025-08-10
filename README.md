Automated MCQ Generator with AI-Powered Validation  
This project provides a powerful Python pipeline for automatically generating high-quality multiple-choice questions (MCQs) from text documents (.pdf, .txt). It leverages a sophisticated generator-evaluator architecture using Google's Gemini models to ensure that the generated questions are conceptually sound, relevant, and based strictly on the provided content.  

Key Features  
Dual-AI Architecture: Uses one AI model to generate questions and a second, stricter AI model to evaluate and filter them, ensuring high quality.  

Deep Understanding: The prompts are engineered to create questions that test comprehension, reasoning, and application of concepts, not just rote memorization.  

Flexible Input: Processes both local document files (.pdf, .txt) and raw text strings.  

Robust & Resilient: Includes error handling and a retry mechanism with exponential backoff to manage potential API failures.  

Detailed Output: Generates separate JSON files for accepted, rejected, and raw MCQs, allowing for easy review and analysis.  

Structured JSON Output: Each MCQ includes the question, options, the correct answer, a difficulty rating, a relevant topic, and a detailed explanation for why each option is correct or incorrect.  

How It Works   
The pipeline follows a systematic, multi-step process for each document it receives:  

Load and Chunk: The source document is loaded and split into smaller, manageable text chunks. This allows the system to process large documents without exceeding the AI's context limit.  

Generate: Each chunk is passed to the Generator AI. Guided by a detailed prompt, this AI creates a set of MCQs based on the text.  

Evaluate: The newly generated MCQs are immediately sent to the Evaluator AI. This model acts as an expert educational validator, using a strict set of rules to check each question for:  

Direct support from the source text.  

A single, unambiguous correct answer.  

Plausible but clearly incorrect distractors.  

Focus on core concepts (rejecting questions about logistics, formatting, or trivial facts).  

Parse and Collect: The system parses the output from the evaluator. Only the MCQs that pass this rigorous validation are collected.  

Save Results: Once all chunks have been processed, the script saves the results into three distinct JSON files for complete transparency.  
