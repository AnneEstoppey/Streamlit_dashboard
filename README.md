# Dashboard with Streamlit
https://dashboardappst.streamlit.app/

![dash_screenshot](https://github.com/AnneEstoppey/Streamlit_dashboard/assets/35219455/49963be2-b655-44e4-a1c9-3038cea71b6c)

### Main requirements
The app runs with Python 3.11.5<br>
For install specs and troubleshooting, see section 'Troubleshooting with Streamlit' below.

### Data file 'Superstore_2023.csv'
The file is available here: https://data.world/ehughes/superstore-sales-2023
(you might have to sign in to be able to download it)

In the tutorial the file is refered as a xlsx (Excel format), while the download is a CSV.<br>
In the code available on this repo, I have taken this into consideration, and reformatted the dates to datetime in the dataframe.

### References
---> 'tutorial' article here: https://python.plainenglish.io/creating-interactive-analytics-dashboards-using-pythons-streamlit-43a770bc3194
---> github repo here: https://github.com/mattyjr007/Superstore-sales-Streamlit/tree/main

Note: it was easier to refer to the .py file from the repo than the coding bits in the article :)


### Troubleshooting with Streamlit
Install streamlit and streamlit-extras with conda.<br> 
I tried to install streamlit-extras with pip, but it was an error message concerning the wheel and the package didn't install. After trying different things, I uninstalled my streamlit entirely and reinstalled with conda. Same with streamlit-extras and that finally worked:<br>
> conda install streamlit<br>
> conda install streamlit-extras

After that I had an issue with launching the app with command: 'streamlit run app.py'.<br>
The error message was similar to this:<br>
'File "<path to user>/anaconda3/envs/python311/bin/streamlit", line 7, in from streamlit.cli import main ModuleNotFoundError: No module named 'streamlit.cli'.

---> Open the file 'streamlit' in a text editor (it is a text file), and edit line 7 (or 6) with: 'from streamlit.web.cli import main' (the original line is 'from streamlit.cli import main'). That solved the problem and then I had no issues running my streamlit app.

See thread on streamlit github repo here: https://github.com/streamlit/streamlit/issues/5255#issuecomment-1460927141

