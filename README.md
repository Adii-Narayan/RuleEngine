# Rule Engine Application

## Overview
This Rule Engine application allows users to create, evaluate, and modify rules based on various user attributes such as age, department, salary, and experience. The rules are represented using an Abstract Syntax Tree (AST), enabling dynamic rule creation and evaluation.

## Features
- Create rules with various conditions.
- Evaluate rules against user data.
- Combine multiple rules into a single AST.
- Dynamic modification of rules.
- Simple user interface built with HTML and CSS.

## Tech Stack
- **Backend**: Python with Django
- **Database**: SQLite
- **Frontend**: HTML, CSS
- **AST Representation**: Custom data structure in Python

## Installation

### Prerequisites
- Python 3.x
- Django
- SQLite

### Steps
1. Clone the repository:
    ```bash
    git clone <repository_url>
    cd rule_engine_project
    ```

2. Create a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```

4. Run database migrations:
    ```bash
    python manage.py migrate
    ```

5. Start the development server:
    ```bash
    python manage.py runserver
    ```

6. Open your browser and navigate to `http://127.0.0.1:8000/`.

## Usage

### Creating Rules
- You can create rules by entering a rule string in the provided input field. The rules can be based on attributes like age, department, salary, etc.

### Evaluating Rules
- After creating rules, you can evaluate them against user data by entering the required attributes.

### Sample Rules
- **Rule 1**: `((age > 30 and department == 'Sales') or (age < 25 and department == 'Marketing')) and (salary > 50000 or experience > 5)`
- **Rule 2**: `((age > 30 and department == 'Marketing')) and (salary > 20000 or experience > 5)`

## API Endpoints

### Create Rule
- **URL**: `/`
- **Method**: `POST`
- **Description**: Creates a new rule based on the provided rule string.
- **Request Body**:
    ```json
    {
        "rule_string": "((age > 30 and department == 'Sales') or (age < 25 and department == 'Marketing')) and (salary > 50000 or experience > 5)"
    }
    ```

### Evaluate Rule
- **URL**: `/`
- **Method**: `POST`
- **Description**: Evaluates the combined rule against provided user data.
- **Request Body**:
    ```json
    {
        "data": {
            "age": 35,
            "department": "Sales",
            "salary": 60000,
            "experience": 6
        }
    }
    ```

## Testing

### Test Cases
1. Create individual rules using the `create_rule` function and verify their AST representation.
2. Combine multiple rules using the `combine_rules` function and ensure the resulting AST reflects the combined logic.
3. Implement sample JSON data to test `evaluate_rule` for different scenarios.
4. Test combining additional rules to verify functionality.

## Bonus Features
- Error handling for invalid rule strings or data formats.
- Validation for attributes to ensure they are part of a defined catalog.
- Modification of existing rules.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue for any improvements or bug fixes.
