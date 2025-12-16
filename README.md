# University Timed Exam Engine (Offline)

## Project Description

This project is an offline, command-line based exam system developed in Java. It simulates a real university exam environment with timed execution, automatic evaluation, negative marking, and partial scoring.

## Features

- CLI-based exam system
- Timed exams using multithreading
- MCQ with negative marking
- Short answer questions with partial marks
- Autosave of responses
- CSV-based question loading
- Score and report generation

## Technologies Used

- Java (Core Java)
- OOP Principles
- Design Patterns (Strategy, Template Method, Observer)
- Multithreading
- File Handling (CSV, TXT)

## Project Structure

```
UnivesityTimedExamEngine/
├── src/
│   ├── main/
│   │   ├── QuestionEngine.java        # Main exam engine controller
│   │   ├── Question.java               # Base question class
│   │   ├── MCQQuestion.java            # Multiple choice questions
│   │   ├── ShortAnswerQuestion.java    # Short answer questions
│   │   ├── Exam.java                   # Exam management
│   │   ├── ExamTimer.java              # Timer thread for timed exams
│   │   ├── StudentResponse.java        # Store student responses
│   │   ├── ScoreCalculator.java        # Calculate scores with negative marking
│   │   ├── ReportGenerator.java        # Generate result reports
│   │   └── FileHandler.java            # CSV/TXT file operations
│   └── utils/
│       └── Constants.java              # Configuration constants
├── data/
│   ├── questions.csv                   # Question repository
│   ├── responses.txt                   # Autosaved responses
│   └── results/
│       └── report_*.txt                # Generated result reports
├── README.md                           # This file
└── .gitignore
```

## Setup & Installation

### Prerequisites
- Java Development Kit (JDK) 8 or higher
- A terminal/command prompt

### Steps to Run

1. **Clone the repository:**
   ```bash
   git clone https://github.com/owais1204/UnivesityTimedExamEngine.git
   cd UnivesityTimedExamEngine
   ```

2. **Compile the Java files:**
   ```bash
   javac -d bin src/main/*.java src/utils/*.java
   ```

3. **Prepare question data (questions.csv):**
   Create a `data/questions.csv` with format:
   ```
   id,type,question,option_a,option_b,option_c,option_d,correct_answer,marks,negative_marking
   1,MCQ,What is 2+2?,3,4,5,6,4,1,0.25
   2,SHORT,Explain polymorphism in Java,,,,,,2,0
   ```

4. **Run the exam engine:**
   ```bash
   java -cp bin main.QuestionEngine
   ```

## Usage & Sample Output

### Example Exam Session:

```
=================================
  University Timed Exam Engine
=================================

Welcome to the Exam System!
Total Questions: 10
Time Limit: 60 minutes
Negative Marking: Yes (0.25 per wrong answer)

Starting Exam...
[Timer Started: 60:00 remaining]

Question 1/10 [MCQ] - 1 Mark
What is the capital of France?
A) Berlin    B) Paris    C) London    D) Madrid

Your answer: B
✓ Correct! +1 Mark
Current Score: 1/10

Question 2/10 [SHORT ANSWER] - 2 Marks
Explain the difference between ArrayList and LinkedList

Your answer: ArrayList uses array, LinkedList uses nodes
Submitted for evaluation.

[Auto-saving response...]
Progress: 20% | Time Remaining: 58:15

...

=================================
         EXAM COMPLETED
=================================

Final Score: 8.5/10
Correct Answers: 8
Wrong Answers: 1 (-0.25)
Unanswered: 1

Accuracy: 85%
Time Taken: 58 minutes 15 seconds
Grade: A

Report saved to: results/report_2024-12-16.txt
=================================
```

## Key Components

### 1. **QuestionEngine.java**
- Main entry point
- Orchestrates exam flow
- Manages user interactions

### 2. **Exam.java**
- Loads questions from CSV
- Manages exam state
- Handles question navigation

### 3. **ExamTimer.java**
- Implements Runnable for multithreading
- Handles exam timeout
- Auto-submission on time expiry

### 4. **ScoreCalculator.java**
- Calculates final score
- Applies negative marking for MCQs
- Evaluates partial marks for short answers

### 5. **ReportGenerator.java**
- Generates detailed result reports
- Saves to .txt file
- Includes performance analytics

## Design Patterns Used

- **Strategy Pattern:** Different question types (MCQ, Short Answer)
- **Template Method:** Common exam flow with specific implementations
- **Observer Pattern:** Timer notifications to exam engine

## Contributing

Feel free to submit issues and enhancement requests!

## License

This project is open source and available under the MIT License.

---
**Author:** Owais  
**Last Updated:** December 2024
