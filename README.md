# LLM-Treasure-Hunt

A Repository for AI Experiments exploring the performance of large language models (LLMs) in a simple treasure hunt game to evaluate efficiency, learning, and strategy optimization.

## Project Overview  
This project investigates the performance of large language models (LLMs) in a simple treasure hunt game to evaluate their efficiency, learning capabilities, and strategy optimization. The goal is to iteratively improve model performance across different setups by modifying prompts, integrating strategy agents, and adjusting model parameters.  

The treasure hunt takes place on a 5x5 grid, with the treasure randomly hidden in one of the four quadrants. The starting position is always the center of the grid.  


## Experimental Setup  
### Rules of the Game  
- **Starting Position**: [2,2] (center of the grid)  
- **Movement**: Orthogonal (up, down, left, right)  
- **Treasure Location**: Randomly placed in one of the four corner quadrants  
- **Maximum Moves per Game**: 24  
- **Game Objective**: Find the treasure as quickly as possible  

### Objective  
The LLMs aim to locate the treasure with the minimum number of moves. From game 2 onwards, the models are given knowledge about previous treasure locations to improve efficiency.  

## Conclusion  
The experiments demonstrate that LLMs can significantly improve their efficiency in simple tasks through tailored modifications, such as sharing past knowledge and allowing multi-step planning. Introducing additional agents, like the Strategy Agent, was not beneficial in this specific scenario.  


### Iterations  
1. **Baseline Setup**: Single LLM making one move per step.  
2. **Setup 1**: Introducing a "Strategy Agent" to provide directional hints.  
3. **Setup 2**: Allowing the LLM to plan multiple moves in one step.  
4. **Setup 3**: Replacing the Strategy Agent with prior knowledge of treasure locations.  
5. **Setup 4**: Evaluating the impact of different temperatures on model performance.  


## Results  
### Setup 1: Baseline vs. Strategy Agent  
- **Baseline**: Average 19.34 moves per game  
- **With Strategy Agent**: Average 18.84 moves per game  
- **Improvement**: 2.58%, below the significance threshold of 7.5%.  

### Setup 2: Planning Multiple Moves  
- **Result**: Average 12.84 moves per game  
- **Key Insight**: Significant improvement due to more efficient path planning.  

### Setup 3: Using Knowledge of Past Treasure Locations  
- **Result**: Average 4.76 moves per game  
- **Key Insight**: Substantial improvement (62.93% compared to Setup 2).  

### Setup 4: Impact of Temperature  
- **Temperatures ≤ 0.7**: Average 5.76 moves per game  
- **Temperatures > 0.7**: Average 5.60 moves per game  
- **Conclusion**: Temperature had no significant impact.  


## Future Work  
- Extending the LLM's capabilities to more complex game scenarios  
- Analyzing the effect of model parameters, such as context window size and architecture  
- Exploring reinforcement learning for adaptive behavior  


## Installation  
To run this project, you'll need the following dependencies:  
```bash
pip install python-dotenv instructor httpx==0.23.0 openai
pip install instructor
```

## How to Run
1. Clone the Repository
   ```bash
   git clone https://github.com/yourusername/llm-treasure-hunt.git
   ```
cd llm-treasure-hunt

2. Enter your openai API Key to the env variable
   ```bash
   OPENAI_API_KEY='your_api_key'
   ```

3. Run the Script
   ```bash
   python llm_treasure_hunt.py
   ```


License
This project is licensed under the MIT License. See the LICENSE file for details.
Special thanks to OpenAI's GPT-4o-mini and the developer community for their tools and resources.
You can customize the repository URL, acknowledgments, or other sections as needed. Let me know if you'd like further adjustments!



