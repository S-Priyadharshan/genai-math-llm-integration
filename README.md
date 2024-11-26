## Integration of a Mathematical Calulations with a Chat Completion System using LLM Function-Calling
Developed By: Priyadharshan S
Register Number: 212223240127
### AIM:
To design and implement a Python function for calculating the volume of a cylinder, integrate it with a chat completion system utilizing the function-calling feature of a large language model (LLM).

### PROBLEM STATEMENT:
We need to implement a Python function that calculates the volume of a cylinder based on its radius and height. Additionally, we need to integrate this function with a chat system powered by a language model that can interpret user input, recognize when a function should be invoked, and return the correct response.

### DESIGN STEPS:

#### STEP 1:
Define a Python function calculate_cylinder_volume(radius, height) that takes the radius and height as inputs and returns the volume of the cylinder using the formula V = π r² h.

#### STEP 2:
Create a mock LLM function that simulates a chat completion system. This function should receive the function name and arguments, and invoke the appropriate function (e.g., calculate_cylinder_volume).

#### STEP 3:
Integrate the function and simulate user interaction. The LLM should detect the user’s request, call the necessary function, and provide the result in a response message.


### PROGRAM:

```python
import openai
import math


def calculate_cylinder_volume(radius, height):
    return math.pi * radius ** 2 * height

def mock_llm_function_call(function_name, arguments):
    if function_name == "calculate_cylinder_volume":
        return {"volume": calculate_cylinder_volume(**arguments)}
    else:
        return {"error": "Function not recognized"}

def main():
    user_message = "What is the volume of a cylinder with radius 10 and height 20?"
    print(f"User: {user_message}")
    
    function_name = "calculate_cylinder_volume"
    arguments = {"radius": 10, "height": 20}
    
    response = mock_llm_function_call(function_name, arguments)
    print(f"LLM Function Output: {response}")


    if "volume" in response:
        print(f"Bot: The volume of the cylinder is {response['volume']:.2f}.")
    else:
        print("Bot: Sorry, there was an error processing your request.")

# Execute the main function
if __name__ == "__main__":
    main()
```

### OUTPUT:
![image](https://github.com/user-attachments/assets/360a93ff-4217-48b5-8aa7-0b1a6be5efbe)

### RESULT:
The system correctly calculates and returns the volume of the cylinder based on the radius and height provided. This demonstrates the integration of a mathematical function with a chat-based system that can call external functions when required.


