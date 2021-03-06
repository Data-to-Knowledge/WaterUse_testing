=======================
Water use data QA tools
=======================
This git repository contains project code for various water use data QA tools. The repository has several modules for performing different data QA tasks.

Modules:
	1.	Missing data tools: 4 tools used to identify missing water use data
	
		a.	Compile WAP Reporting Modes
		b.	Generate Weekly Missing Data Report
		c.	Create Daily and Hourly Plots – Single WAP
		d.	Create Daily and Hourly Plots – WAP List
		
	2.	Time-series analysis and visualisation: 10 tools for analasis and visulaiton of water use data
	
		a.	Generate water meter list
		b.	Quality Assessment - WAP List - Combined Series
		c.	Quality Assessment - WAP List - By Measurement Type
		d.	Analyse Time Series - Without  Consent Conditions - Single WAP
		e.	Analyse Time Series - Without  Consent Conditions - WAP List
		f.	Analyse Time Series - With Consent Conditions - Single WAP
		g.	Analyse Time Series - With Consent Conditions - Single WAP with Date
		h.	Analyse Time Series - With Consent Conditions - WAP List
		i.	Analyse Time Series - With Consent Conditions - WAP List with Date
		j.	Plot Water Use - Single WAP - Specified Month

==================
Missing data tools
==================

These programs enable you to explore and detect missing water take data, so that the compliance team can investigate and follow-up if necessary. This data assessment needs:

-	to be applied to all active WAPs
-	to be run frequently (eg, weekly)
-	to focus on the latest data (eg, data for the last week).

Instruction for running the tools and some troubleshooting suggestions can be found here: https://github.com/Data-to-Knowledge/WaterUseQA/blob/master/MissingDataTools/README.rst.

Compile WAP Reporting Modes.py
-------------------------------------------------
-	This program calculates the normal daily reporting frequency for each WAP and compiles the results into a csv file (‘WAPReportingMode.csv’). It calculates the normal reporting frequency by extracting water take data for the last year and calculating the daily reporting mode. In instances where the annual mode equals zero, the program iterates through four quarters of data trying to calculate a non-zero mode.

Generate Weekly Missing Data Report.py
-------------------------------------------------
-	This program calculates the number of reports received for each WAP over a specified week and compares it to the expected number of reports. It compiles the results into a csv file (‘Missing Data Report - Week ending YYYY-MM-DD’). In instances where a WAP has no data for the specified week, the last year of data is extracted in order to find when data was last received.
	
Create Daily and Hourly Plots – Single WAP.py
-------------------------------------------------
-	This program calculates the number of reports received for each WAP over a specified week and compares it to the expected number of reports. It compiles the results into a csv file (‘Missing Data Report - Week ending YYYY-MM-DD’). In instances where a WAP has no data for the specified week, the last year of data is extracted in order to find when data was last received.
	
Create Daily and Hourly Plots – WAP List.py
-------------------------------------------------
-	This program can be used to investigate recent volume and meter reading data for a list of WAPs. The program iterates through the WAP list, generating the associated Daily Plot and Hourly Plot pdfs.

=================================================
Time-series analysis and visualisation data tools
=================================================
These programs are analytical tools that can be used to analyse and visualise the entire water use time-series for selected WAPs. The tools are intended to support work such as catchment modelling, which requires detailed assessment of historic water use data.

Four sets of programs have been developed that are intended to let the user explore water use data in differing levels of detail:

-	Generate water meter number program
-	Quality Assessment programs
-	Time-series Analysis programs
-	Monthly Visualisation programs

Instruction for running the tools and some troubleshooting suggestions can be found here: https://github.com/Data-to-Knowledge/WaterUseQA/blob/master/CreateTimeSeriesPlots/README.rst.

Generate water meter number program
-------------------------------------------------

Generate water meter list.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	This program generates a list of water meters for a user defined catchment, WAP list or consent number list.

Quality Assessment Programs
---------------------------
-	These programs provide the most general assessment. They are intended to be run over a list of WAPs to give an initial assessment of the water use data that exists for each WAP, and the quality of that data. 
-	There are two variations of the Quality Assessment programs.

Quality Assessment - WAP List - Combined Series.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	Hilltop sometimes contains multiple measures of water use for a single WAP (eg, some combination of Compliance Volume, Volume, Volume [Flow], Volume [Average Flow], or Water Meter measurements). In order to produce time series plots it is necessary to stitch these different measures together while taking care to avoid overlaps. This program lets you perform a quality assessment on the ‘Combined Series’ that is used to produce the time-series plots.

Quality Assessment - WAP List - By Measurement Type.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	This variation (of Quality Assessment - Wap List - combined Series.py) produces a quality assessment for each type of water use measurement that a WAP has. For example, in the case of BY20/0088-M1 which has two measurement types, a quality assessment is provided for each of the two data series (Compliance Volume and Volume).

Time-Series Analysis Programs
-----------------------------

-	These programs enable the user to explore a time-series in more depth. When you run the programs you have the option to output:

	-	an Excel spreadsheet containing various monthly statistics
	-	a set of plots showing daily totals for each month in the time series, arranged by water year, or
	-	both the spreadsheet and plots.

-	There are four variations of the Time-series analysis programs.

Analyse Time Series - Single WAP.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	The program will output an Excel spreadsheet containing monthly statistics, a PDF file containing time-series plots, or both. 

Analyse Time Series - WAP List.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	The program iterates through the WAPs included in the csv file. For each WAP the program will output an Excel spreadsheet containing monthly statistics, a PDF file containing time-series plots, or both (depending on export option that has been selected).

Analyse Time Series - With Consent Conditions - Single WAP.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	This variation adds extra features to the time-series plots, based on consent conditions. The consent conditions are extracted from the CrcActSiteSumm table, stored in the ConsentsReporting database on the epwprod01 server.
-	The program will output an Excel spreadsheet containing monthly statistics, a PDF file containing time-series plots, or both.

Analyse Time Series - With Consent Conditions - Single WAP with date.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	Add functionality to define a date range rather than running across entire water use record.
-	This variation adds extra features to the time-series plots, based on consent conditions. The consent conditions are extracted from the CrcActSiteSumm table, stored in the ConsentsReporting database on the epwprod01 server.
-	The program will output an Excel spreadsheet containing monthly statistics, a PDF file containing time-series plots, or both.

Analyse Time Series - With Consent Conditions - WAP List.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	This variation adds extra features to the time-series plots, based on consent conditions. The consent conditions are extracted from the CrcActSiteSumm table, stored in the ConsentsReporting database on the epwprod01 server.
-	The program iterates through the WAPs included in the csv file. For each WAP the program will output an Excel spreadsheet containing monthly statistics, a PDF file containing time-series plots, or both (depending on export option that has been selected.

Analyse Time Series - With Consent Conditions - WAP List with Date.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	Add functionality to define a date range rather than running across entire water use record.
-	This variation adds extra features to the time-series plots, based on consent conditions. The consent conditions are extracted from the CrcActSiteSumm table, stored in the ConsentsReporting database on the epwprod01 server.
-	The program iterates through the WAPs included in the csv file. For each WAP the program will output an Excel spreadsheet containing monthly statistics, a PDF file containing time-series plots, or both (depending on export option that has been selected.

Monthly visualisation programs
------------------------------
-	This program is intended to let the user explore detailed data for a month of interest, in instances where something unusual has been noticed in the time-series plots or monthly statistics.

Plot Water Use - Single WAP - Specified Month.py
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
-	The program generates a PDF file containing water use plots, with hourly totals, over a 35 day time period. If the WAP has more than one measurement type during the specified time period, a separate PDF file is generated for each measurement type.


	







