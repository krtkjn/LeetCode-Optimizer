# LeetCode Solution Optimizer Documentation
## Project Overview
This project provides a Streamlit application that helps users find solutions, optimize their code, and discover helpful YouTube resources for LeetCode problems. It leverages the Google Gemini API to generate solutions, check code correctness, provide optimization suggestions, and find relevant YouTube videos.
**Key Features:**
*   **Solution Generation:** Generates code solutions for LeetCode problems using the Gemini API.
*   **Code Optimization:** Provides optimization suggestions and explanations for user-submitted code.
*   **Solution Checking:** Checks the correctness of user-submitted code against the problem description.
*   **YouTube Resource Discovery:** Finds and displays the top 5 YouTube videos related to a specific LeetCode problem.
**Supported Platforms/Requirements:**
*   Python 3.6+
*   Streamlit
*   Google Generative AI API
*   Python-dotenv
## Getting Started
### Installation
1.  **Clone the repository (if applicable):** This step is not applicable as the codebase is provided directly.
2.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
    
3.  **Set up Environment Variables:**
    *   Create a `.env` file in the project directory.
    *   Add your Google Generative AI API key to the `.env` file:
                GOOGLE_API_KEY=YOUR_GOOGLE_API_KEY
        ```
        
        Replace `YOUR_GOOGLE_API_KEY` with your actual API key.  You can obtain an API key from the Google AI Studio.
### Prerequisites
*   A Google Cloud project with the Generative AI API enabled.
*   A Google Generative AI API key.
*   Python 3.6 or higher installed.
*   `pip` package installer.
## Code Structure
The project consists of the following files:
*   `.gitignore`: Specifies intentionally untracked files that Git should ignore.
*   `app.py`: Contains the main Streamlit application code.
*   `requirements.txt`: Lists the Python packages required to run the application.
### Key Components
*   **`app.py`:**
    *   Uses Streamlit to create the user interface.
    *   Loads the Google Generative AI API key from environment variables.
    *   Defines functions to interact with the Gemini API:
        *   `check_solution`: Checks if a given code solution is correct.
        *   `optimize_solution`: Optimizes a given code solution based on a prompt.
        *   `get_solution_and_explanation`: Generates a code solution and explanation for a LeetCode problem.
        *   `get_youtube_links`: Retrieves YouTube links for a LeetCode problem.
    *   Implements the main application logic, handling user input and displaying results.
## API Documentation
The application uses the Google Gemini API. The following functions interact with the API:
*   **`check_solution(problem_number, user_code)`:**
    *   **Purpose:** Checks if the provided `user_code` is a correct solution for the LeetCode problem with the given `problem_number`.
    *   **Input:**
        *   `problem_number` (str): The LeetCode problem number.
        *   `user_code` (str): The user's code solution.
    *   **Output:** (str): The response from the Gemini API, indicating whether the solution is correct.
*   **`optimize_solution(problem_number, user_code, optimization_prompt)`:**
    *   **Purpose:** Optimizes the provided `user_code` for the LeetCode problem with the given `problem_number`, based on the `optimization_prompt`.
    *   **Input:**
        *   `problem_number` (str): The LeetCode problem number.
        *   `user_code` (str): The user's code solution.
        *   `optimization_prompt` (str): A prompt guiding the optimization process.
    *   **Output:** (str): The response from the Gemini API, containing the optimized solution and explanations.
*   **`get_solution_and_explanation(problem_number)`:**
    *   **Purpose:** Generates a code solution and explanation for the LeetCode problem with the given `problem_number`.
    *   **Input:**
        *   `problem_number` (str): The LeetCode problem number.
    *   **Output:** (str): The response from the Gemini API, containing the code solution and explanation.
*   **`get_youtube_links(problem_number)`:**
    *   **Purpose:** Retrieves the top 5 YouTube links for the LeetCode problem with the given `problem_number`.
    *   **Input:**
        *   `problem_number` (str): The LeetCode problem number.
    *   **Output:** (str): The response from the Gemini API, containing the YouTube links and video titles.
## FAQ
**Q: I'm getting an error that the `GOOGLE_API_KEY` environment variable is not set.**
**A:** Make sure you have created a `.env` file in the project directory and added your Google Generative AI API key to it, as described in the "Getting Started" section. Also, ensure that the `.env` file is in the same directory as `app.py`.
**Q: The application is not generating accurate solutions.**
**A:** The accuracy of the solutions depends on the capabilities of the Google Gemini API. You can try refining your optimization prompts or providing more context to improve the results.
**Q: The application is running slowly.**
**A:** The speed of the application depends on the response time of the Google Gemini API. Network latency and API usage limits can also affect performance. Consider using a more powerful Gemini model if available.
