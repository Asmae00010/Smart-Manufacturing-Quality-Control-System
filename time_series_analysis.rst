Steel Manufacturing Monitor
==========================

Purpose
-------
The Steel Manufacturing Monitor is a Streamlit-based dashboard application for real-time monitoring and forecasting of critical steel manufacturing parameters. The system provides comprehensive tracking of six key parameters, statistical analysis, and predictive insights.

System Overview
--------------

Monitored Parameters
~~~~~~~~~~~~~~~~~~~
The system tracks six critical manufacturing parameters:

1. **Temperature**
    - Range: 1370-1540°C
    - Purpose: Monitor melting temperature
    - Critical for: Material formation quality

2. **Elongation**
    - Range: 15-25%
    - Purpose: Track material elasticity
    - Critical for: Product quality control

3. **Energy Consumption**
    - Range: 400-600 kWh/ton
    - Purpose: Monitor energy efficiency
    - Critical for: Cost optimization

4. **Cooling Rate**
    - Range: 40-60°C/min
    - Purpose: Track cooling process
    - Critical for: Material structure formation

5. **Contact Pressure**
    - Range: 150-250 MPa
    - Purpose: Monitor applied pressure
    - Critical for: Material forming quality

6. **Vibration**
    - Range: 1.5-3.5 mm/s
    - Purpose: Equipment health monitoring
    - Critical for: Maintenance planning

Core Functionality
-----------------

Data Management
~~~~~~~~~~~~~~
.. code-block:: python

    def save_data(data, parameter):
        """
        Saves monitoring data and metadata to filesystem.
        
        Parameters:
            data (DataFrame): Time series data
            parameter (str): Monitored parameter name
        
        Returns:
            str: Path to saved file
        """

Data Generation
~~~~~~~~~~~~~~
.. code-block:: python

    def generate_data(start_date, periods=100):
        """
        Generates synthetic monitoring data.
        
        Parameters:
            start_date (datetime): Start time for data generation
            periods (int): Number of data points to generate
        
        Returns:
            DataFrame: Generated time series data
        """

Forecasting System
~~~~~~~~~~~~~~~~~
Implements Facebook Prophet with the following configuration:

- Interval width: 95%
- Seasonality:
    - Daily
    - Weekly
    - Hourly (period=24, Fourier order=5)
- Changepoint detection:
    - Prior scale: 0.05
    - Range: 0.9
- Seasonality prior scale: 10.0

User Interface Components
------------------------

Dashboard Layout
~~~~~~~~~~~~~~
The application uses a wide layout with two main sections:

Main Column 
    - Real-time parameter monitoring
    - Historical data visualization
    - Forecast analysis plots
    - Range indicators
    - Confidence intervals

Statistics Column 
    - Current value display
    - Statistical summary
    - Forecast statistics
    - Distribution analysis
    - Data download options

Interactive Features
~~~~~~~~~~~~~~~~~~
- Parameter selection dropdown
- Real-time plot updates
- CSV data export
- Interactive visualizations
- Forecast explanation
- Statistical analysis tables

Data Structure
-------------

Time Series Format
~~~~~~~~~~~~~~~~
The system processes data in the following format:

.. code-block:: text

    datetime,Temperature,Elongation,Energy_Consumption,Cooling_Rate,Contact_Pressure,Vibration
    2024-01-05 10:00:00,1450.32,20.5,500.1,45.2,200.3,2.5
    2024-01-05 11:00:00,1445.67,19.8,498.4,46.7,195.8,2.3
    ...

Metadata Structure
~~~~~~~~~~~~~~~~
.. code-block:: json

    {
        "timestamp": "2024-01-05 10:00:00",
        "parameter": "Temperature",
        "data_points": 100,
        "file_path": "data/steel_data_20240105100000.csv"
    }


Performance Considerations
------------------------

Data Processing
~~~~~~~~~~~~~~
- Efficient synthetic data generation
- Optimized data storage
- Automated file management
- Real-time visualization updates

Memory Management
~~~~~~~~~~~~~~~
- Session state management
- Efficient data structure usage
- Optimized plot rendering


Security Considerations
---------------------

Data Protection
~~~~~~~~~~~~~~
- Secure file storage
- Metadata tracking
- Access control implementation
- Backup management

Monitoring
~~~~~~~~~~
- Real-time parameter tracking
- Threshold violation alerts
- System health monitoring
- Performance metrics tracking