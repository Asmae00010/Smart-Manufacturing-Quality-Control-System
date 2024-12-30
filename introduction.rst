.. _smart-manufacturing-quality-control-system:

==========================
Smart Manufacturing Quality Control System
==========================

Core Concept
------------
A system that monitors manufacturing equipment and products through multiple data streams to predict and detect defects.

Components
----------
1. **Computer Vision**
   - Detect visual defects in products, specifically steel surface defects.
   - Utilizes six classes from the neu-surface-defect-database available on Kaggle.

2. **Time Series Analysis**
   - Monitors equipment sensor data, including:
     - Temperature
     - Elongation
     - Energy consumption
     - Cooling rate
     - Surface pressure
     - Vibrations
   - Provides a 24-hour forecasting of these metrics, displayed on the main dashboard of our website.

3. **Natural Language Processing (NLP) / Retrieval-Augmented Generation (RAG)**
   - Processes maintenance logs and technical documentation.
   - Allows operators to query past incidents and solutions.
   - Generates automated reports to facilitate decision-making.

This documentation provides an overview of the Smart Manufacturing Quality Control System, detailing its core concepts and components aimed at enhancing manufacturing quality control through advanced monitoring and analysis.