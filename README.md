This code implements a multi-agent AI system using the Ollama library to break down and complete complex tasks. Here's a step-by-step breakdown of what the code does and how to run it:

1. The code sets up a system with three AI models:
   - An Orchestrator (using 'llama3:70b-instruct')
   - A Subagent (using 'llama3:instruct')
   - A Refiner (using 'llama3:70b-instruct')

2. It checks if these models are available locally, and if not, it pulls them from Ollama.

3. The main workflow:
   a. The Orchestrator breaks down the main objective into subtasks.
   b. The Subagent completes each subtask.
   c. The Refiner reviews and refines the results into a final output.

4. The code can handle file input, create folder structures, and save code files based on the AI's output.

5. It keeps track of task progress and can resume from where it left off.

To run this code, follow these steps:

1. Ensure you have Python installed on your system.

2. Install the required libraries:
   ```
   pip install rich ollama
   ```

3. Make sure you have Ollama installed and running on your system. The code assumes Ollama is running on `http://localhost:11434`.

4. Save the provided code in a file, for example, `ai_task_manager.py`.

5. Run the script using one of two methods:

   a. With a command-line argument:
      ```
      python ai_task_manager.py -p "Your objective here"
      ```

   b. Without an argument, which will prompt you for input:
      ```
      python ai_task_manager.py
      ```

6. If you've run the script before, it will ask if you want to continue from the last task. Answer 'y' or 'n'.

7. The script will then process your objective, breaking it down into subtasks and completing them using the AI models.

8. Once complete, it will save the full exchange log in a Markdown file and create any necessary folders and files based on the AI's output.

9. The refined final output will be displayed in the console, and the full log will be saved to a file named with a timestamp and a truncated version of your objective.

Remember that this script requires a significant amount of computational resources due to the large language models it uses. Ensure your system meets the requirements for running these models with Ollama.
