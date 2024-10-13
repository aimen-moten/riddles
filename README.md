```markdown
# Riddles Quiz Webpage

A simple Riddles Quiz webpage built with Vue 3 using Vue Forms. This interactive quiz contains riddles, various input types, and calculates the user's score upon submission.

## Setup Instructions

### 1. Navigate to Your Folder
Open a terminal and navigate to your desired folder (e.g., `csc-340-vue/initials-assignments`) using:
```bash
cd folder/file/path
```

### 2. Create a New Vue App
Run the following command to create a new Vue application:
```bash
npm create vue@latest
```
Name the project **"riddles"** and answer **"No"** to any other setup prompts.

### 3. Run the App
Once created, start the development server with:
```bash
cd riddles
npm install
npm run dev
```
Open the app by holding `Ctrl` (or `Cmd` on Mac) and clicking the URL link, or copy and paste the link into your browser.

---

## Component Requirements

### Create `RiddleForm.vue`
1. **Riddle Form Setup**  
   Add 4 to 5 riddles with the following input types:
   - **Checkbox**: At least one riddle should use checkboxes.
   - **Radio**: Include one or more questions using radio buttons.
   - **Dropdown**: Include a dropdown select element with `<select>` and `<option>` tags.

2. **Buttons**  
   - **Submit** button: Calls `submitForm()` to calculate the user’s score.
   - **Reset** button: Calls `resetQuiz()` to clear the form.

3. **Score Display**  
   - Dynamically show the score using a `v-if` directive on a `graded` variable.

### Data Requirements

In `data()` within `RiddleForm.vue`:
- **Answers Object**  
  Define the correct answers in an `answers` object:
  ```javascript
  answers: {
    riddle1: "correct_answer",
    riddle2: "correct_answer",
    ...
  }
  ```

- **Response Object**  
  Store the user’s responses in a `response` object:
  ```javascript
  response: {
    riddle1: "",
    riddle2: "",
    ...
  }
  ```

- **Score and Graded Variables**  
  - Initialize `score` to `0`.
  - Initialize `graded` to `false`.

### Methods

1. **submitForm()**  
   Calculates the user’s score by comparing responses to answers and sets `graded` to `true`.

2. **resetQuiz()**  
   Resets the `graded` variable to `false`, `score` to `0`, and clears the `response` object.

---

## Usage in `App.vue`

- **Import `RiddleForm.vue`** and replace `<header>` and `<main>` with `<RiddleForm />`.
- Add a title (`<h1>`) and include a comment with both authors' names.
- Rename the webpage title in `index.html`.

## Styling

- **CSS**  
  Add unique styling to personalize the webpage, either by scoped styles within `RiddleForm.vue` or updating `main.css`.

- **Clean Up**  
  Remove any unused components to keep the codebase clean.

--- 

## Running the Project

After setting up, run the project locally with:
```bash
npm run dev
```
View the webpage in your browser to begin the Riddles Quiz.
