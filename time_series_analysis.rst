Steel Manufacturing Monitor
==========================

Purpose
-------
The Steel Manufacturing Monitor is a real-time dashboard application designed to track and analyze critical parameters in steel manufacturing processes. It provides comprehensive monitoring, forecasting, and statistical analysis of key manufacturing metrics.

Core Features
------------

Monitoring Parameters
~~~~~~~~~~~~~~~~~~~
The system tracks three essential manufacturing parameters:

- **Temperature**: 
    - Range: 1370-1540°C
    - Critical for proper steel formation
    - Real-time monitoring with alerts
- **Elongation**: 
    - Range: 15-25%
    - Indicates material elasticity
    - Quality control metric
- **Energy Consumption**: 
    - Range: 400-600 kWh/ton
    - Efficiency monitoring
    - Cost optimization metric

Data Management
~~~~~~~~~~~~~~
- **Data Generation**: 
    - Synthetic data creation for testing and demonstration
    - Configurable time periods and frequencies
    - Realistic value ranges based on industry standards

- **Data Storage**:
    - CSV file-based persistence
    - Timestamp-based file naming
    - JSON metadata tracking
    - Automated directory management

Forecasting System
~~~~~~~~~~~~~~~~~
The application implements Facebook's Prophet algorithm for time series forecasting with the following features:

- **Model Configuration**:
    - 95% confidence interval
    - Daily and weekly seasonality
    - Hourly seasonality (period=24, Fourier order=5)
    - Changepoint detection (prior scale=0.05)
    - Seasonality prior scale=10.0

- **Forecast Outputs**:
    - 24-hour future predictions
    - Confidence intervals
    - Trend analysis
    - Seasonality decomposition

User Interface
-------------

Dashboard Layout
~~~~~~~~~~~~~~
The application uses Streamlit's wide layout with two main columns:

Main Column (2/3 width):
    - Real-time parameter monitoring
    - Historical data visualization
    - Forecast analysis plots

Statistics Column (1/3 width):
    - Current value metrics
    - Statistical summaries
    - Forecast statistics
    - Distribution analysis

Interactive Elements
~~~~~~~~~~~~~~~~~~
- **Parameter Selection**:
    - Dropdown menu for metric selection
    - Real-time plot updates
    - Unit-aware displays

- **Visualization**:
    - Interactive Plotly charts
    - Range indicators
    - Confidence intervals
    - Distribution histograms

- **Data Export**:
    - CSV download functionality
    - Timestamped file naming
    - Complete dataset export

Sample Data Format
----------------
The system processes time series data in the following format::

    datetime,Temperature,Elongation,Energy_Consumption
    2024-12-23 16:08:30.233832,1447.0207266848824,20.591107332685088,512.2613687312416
    2024-12-23 17:08:30.233832,1407.1661700792843,18.71565997113482,489.4908730863263
    ...

Technical Implementation
----------------------

Dependencies
~~~~~~~~~~~
- **Core Libraries**:
    - streamlit: Web application framework
    - pandas: Data manipulation
    - numpy: Numerical computations
    - plotly: Interactive visualizations
    - prophet: Time series forecasting
    - matplotlib: Additional plotting capabilities

Functions
~~~~~~~~~
save_data(data, parameter)
    Persists monitoring data and metadata
    
    :param data: DataFrame containing time series data
    :param parameter: String indicating the monitored parameter
    :returns: String path to saved file

generate_data(start_date, periods=100)
    Creates synthetic monitoring data
    
    :param start_date: DateTime object for data start
    :param periods: Integer number of data points
    :returns: DataFrame with synthetic data

create_forecast(data, parameter, periods=24)
    Generates time series forecasts
    
    :param data: DataFrame with historical data
    :param parameter: String parameter name
    :param periods: Integer forecast horizon
    :returns: Tuple of (forecast DataFrame, Prophet model)

Performance Considerations
------------------------

Data Handling
~~~~~~~~~~~~
- Efficient data generation and storage
- Automatic cleanup of old files
- Metadata tracking for audit purposes

Visualization
~~~~~~~~~~~~
- Responsive charts with optimization for large datasets
- Efficient update cycles
- Memory-conscious data management

Future Enhancements
------------------
1. Real-time data integration capabilities
2. Advanced anomaly detection
3. Multi-parameter correlation analysis
4. Customizable alert thresholds
5. Enhanced reporting capabilities