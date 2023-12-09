Install and troubleshooting for Streamlit dashboard
---------------------------------------------------

---> 'tutorial' article here: https://python.plainenglish.io/creating-interactive-analytics-dashboards-using-pythons-streamlit-43a770bc3194

---> github repo here: https://github.com/mattyjr007/Superstore-sales-Streamlit/tree/main

Note: it was easier to refer to the .py file from the repo than the coding bits in the article :)


Main requirements:
-----------------
python==3.11.5
altair==5.1.2
millify==0.1.1
numpy==1.26.2
pandas==2.1.1
plotly==5.18.0
streamlit==1.26.0 (conda install)
streamlit-card==0.0.4 (conda install)
streamlit-extras==0.2.7 (conda install)


Data file 'Superstore_2023.csv'
------------------------------
The file is available here: https://data.world/ehughes/superstore-sales-2023
(you might have to sign in to be able to download it)

In the tutorial the file is refered as a xlsx (Excel format), while the download is a CSV.
In the code available on this repo, I have taken this into consideration, and reformatted the dates to datetime in the dataframe.


Troubleshooting with Streamlit:
------------------------------
- install streamlit and streamlit-extras with conda. I tried to install streamlit-extras with pip, but it was an error message concerning the wheel and the package didn't install. After trying different things, I uninstalled my streamlit entirely and reinstalled with conda. Same with streamlit-extras and that finally worked:
> conda install streamlit
> conda install streamlit-extras

After that I had an issue with launching the app with command: 'streamlit run app.py'. 
The error message was similar to this: 
'File "<path to user>/anaconda3/envs/python311/bin/streamlit", line 7, in from streamlit.cli import main ModuleNotFoundError: No module named 'streamlit.cli'.

---> Open the file 'streamlit' in a text editor (it is a text file), and edit line 7 (or 6) to 'from streamlit.web.cli import main' (the original line is 'from streamlit.cli import main'). That solved the problem and then I had no issues running my streamlit app.

See thread on streamlit github repo here: https://github.com/streamlit/streamlit/issues/5255#issuecomment-1460927141

