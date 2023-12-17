# contlo_assignment

In this code, I implemented a variant of the GPT-2 model for text generation using PyTorch. Let me explain the key components and the flow of the code:

1. **Data Loading:**
   - I downloaded a sample text file (`input.txt`) from a specific GitHub repository using the `wget` command.
   - The content of the file was then read into a variable named `my_text`.

2. **Model Architecture:**
   - I defined a multi-head attention mechanism (`MyMultiHeadAttention`), a feedforward layer (`MyFeedForward`), and a transformer block (`MyTransformerBlock`). These components are the building blocks of the GPT-2 model.
   - The main GPT-2 model is defined as `MyGPT2Small`, consisting of an embedding layer for tokens, a position embedding layer, multiple transformer blocks, and a linear layer for output.
   - The model is set up to take input indices and generate logits. Optionally, it can compute the loss if targets are provided.

3. **Hyperparameters and Initialization:**
   - I specified various hyperparameters such as batch size, block size, learning rate, and model dimensions (e.g., `my_n_embd`, `my_n_head`, `my_n_layer`).
   - A random seed (`1337`) is set for reproducibility, and the device is chosen based on GPU availability.

4. **Data Preprocessing:**
   - The text is tokenized into a vocabulary of characters, and mappings (`my_stoi` and `my_itos`) between characters and indices are created.
   - The text is then encoded into numerical indices using the created mappings.

5. **Model Initialization or Loading:**
   - The script checks if a pre-trained model exists at a specified path (`my_save_path`). If it does, the model is loaded; otherwise, a new model is created.

6. **Training Loop:**
   - If the model is not pre-trained, a training loop is executed for a specified number of iterations (`my_max_iters`).
   - In each iteration, a training batch is obtained, and the model is trained to minimize the cross-entropy loss between predicted and target tokens.
   - The training loss is printed at regular intervals.

7. **Model Evaluation and Saving:**
   - The script evaluates the model on both training and validation datasets at specific intervals.
   - The model with the best validation performance is saved to a file (`my_save_path`).

8. **Model Generation:**
   - The trained or loaded model is set to evaluation mode, and a context tensor is initialized for text generation.
   - The model generates new text by sampling from the predicted probability distribution for each token. This process is repeated to generate a specified number of tokens (`max_new_tokens`).
   - The generated text is then decoded back into characters using the inverse mappings (`my_decode`).

9. **Results Display:**
   - The generated text is printed to the console, allowing the user to inspect the model's creativity and language structure.

Overall, the code encompasses the complete lifecycle of a text generation model, from data loading and model architecture definition to training, evaluation, and text generation.


Output:
![image](https://github.com/Anurag-Zalke/contlo_assignment/assets/81683716/643c5e9b-8333-4eb3-aa52-3192e8c910c0)
![image](https://github.com/Anurag-Zalke/contlo_assignment/assets/81683716/ac93d972-0b9a-4ff1-b5ff-0977bd04cd35)

