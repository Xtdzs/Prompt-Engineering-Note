# Note of Guidance

## 1 Principles of Prompting

### 1.1 Principle 1: Write clear and specific instructions

- clear not mean short

#### 1.1.1 Use delimiters

`to indicate the distinct parts of the input`

`avoid prompt injections`

- triple quotes: """
- triple backticks: ```
- triple dashes: ---
- angle brakets: < >
- XML tags: \<tag\> \</tag\>

#### 1.1.2 Ask for structured output

like `HTML`, `JSON`

e.g.:

```python
"""
......
Provide them in JSON format with the following keys:
book_id, title, author, genre.
"""
```

#### 1.1.3 Check the completion of tasks

Check whether conditions are satisfied

Check assumptions required to do the task

e.g.:

```Python
"""
......
If the text does not contain a sequence of instructions, then simply write \"No steps provided.\"
"""
```

#### 1.1.4 Few-shot prompting

Give successful examples of completing tasks. Then ask model to perform the task.

e.g.:

```Python
"""
Your task is to answer a consistent style.

<child>: What is love?

<grandparent>: (your successful examples)

<child>: What is resilience?
"""
```

#### 1.2 Principle 2: Give the model time to think 

#### 1.2.1 Specify the steps to complete a task

e.g.:

```Python
"""
Perform the following actions:
1 - ......
2 - ......
3 - ......
keys: ..., ...

Separate your answers with line breaks.

Text:
\"\"\"{text}\"\"\”
"""
```

#### 1.2.2 Instruct the model to work out its own solution before rushing to a conclusion

when judging one solution by human, let it generate one solution and then compare & evaluate the human's solution

## 2 Model Limitations

### Hallucination

Make statements that sound plausible but are not true

**Solution of reducing it:** 

```Python
"First find relevant information, then answer the question based on the relevant information"
```

