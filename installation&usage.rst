Installation & Usage
====================

Prerequisites
-------------
Ensure you have the following installed:
- Python 3.8+
- pip (Python package installer)
- Streamlit (automatically installed via requirements.txt)

Installation
------------
Follow these steps to set up the application:

1. **Clone the Repository**:
   Clone the project repository to your local machine:

Link to our repository: *add link here*

2. **Set Up Virtual Environment**:
Create and activate a virtual environment:

   .. code-block:: bash

      python -m venv venv
      source venv/bin/activate  # On Windows: venv\Scripts\activate


3. **Install Dependencies**:
Install required Python packages:

   .. code-block:: bash

      pip install -r requirements.txt


Usage
-----
Run the Streamlit application:

1. Execute the following command in the terminal:

.. code-block:: bash

   streamlit run Home.py


2. Access the app in your web browser at:

http://localhost:8501


Example Usage
-------------
1. **Defect Detection**:
- Go to the `Defect Detection` page.
- Upload an image of a steel surface.
- View the identified defect class and confidence score.

2. **Monitoring Dashboard**:
- Access the main dashboard to view real-time and forecasted sensor metrics.

3. **Query Past Logs**:
- Use the `Maintenance Assistant` to search for past incidents and solutions using natural language queries.