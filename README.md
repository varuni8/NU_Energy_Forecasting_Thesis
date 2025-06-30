# NU_Energy_Forecasting_Thesis

The full project can be accessed through this link: https://drive.google.com/drive/folders/1LVV5fERSSHyZXhL-icTQ_sRrEjj0zTvB?usp=sharing

Short description of the archive:

doc/
    sensortypes.txt				Short description of the sensor types
    Thingy-MCO-status.xlsx			Spreadsheet with location and status of all sensors
    Thingy-MCO-status.csv			CSV export of Thingy-MCO-status.xlsx 
    NU-gebouw-INF-01-11-2019.pdf		document with map showing room location 10/11/12 floor of NU

data/
    Campus/
        period-*/NU-sensors-202*-*.csv		Campus VU-NU building sensor value from FCO
    MCO/
        sensors-mcomulti-*.csv			Raw MCO sensor value logs, grouped per sensor type
    Thingy/
        sensors-thingy-*.csv			Raw Thingy sensor value logs, grouped per sensor type
    misc/
	room_properties.csv			room properties
	RoomFeatures.csv			room features

plots/
    MCO-Thingy/
       Sensors-MCO.pdf				Overview plots for all MCO sensors
       Sensor-MCO-*.pdf				Plots of the individual MCO sensors
       Sensors-Thingy.pdf			Overview plots for all Thingy sensors
       Sensor-Thingy-*.pdf			Plots of the individual Thingy sensors
    Campus/
	NU-energy-*.pdf				plots of energy sensors
	NU-airq-*.pdf				plots of air quality sensors

processed/
    MCO-Thingy/
        Sensors-*-sampled10min.csv		MCO/Thingy sensor values downsampled to 10 minutes resolution

code/
    MCO-Thingy/
        sensordata_multi.py			Support library to read and downsample sensor files
        resample-sensor-data.py			Downsample the (realtime) sensor measurements to 1 or 10 minute resolution (needs much memory!)
        multi-sensor-graphs.py			Plot the (downsampled) sensor values
        Dockerfile				create a compatible docker image, based on a miniconda image
        requirements.txt			python library specs with tested versions
    Campus/
        Dockerfile				create a compatible docker image, based on a miniconda image
        requirements.txt			python library specs with tested versions
        NU-sensors-prophet-classify.ipynb	forecasting model and cluster classification
	NU-sensors-prophet-classify.py		python source file of jupyter notebook
	clusters_smoothed_Co2			co2 clustering results
	clusters_dtw_Energy			energy clustering results
	forecast_plot_CO2_4_Energy_6		actual vs predicted forecast plot for cluster group (CO2-4, Energy-6)
