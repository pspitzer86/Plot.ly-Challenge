# Plot.ly-Belly-Button-Bacteria-Dashboard

This project dealt with analyzing data provided on Belly Button Bacteria in various patients of various demographic backgrounds.  Using the D3 library, the data json, which contained names (the ids for all the patients whose belly buttons were sampled), metadata (the demographics associated with each patient id such as gender, age, how often they washed their belly button, etc.), and samples (the associated bacteria ids, also known as OTU ID, in each belly button, how many times each OTU ID occurred, and the scientific kingdom, phyllum, class, etc. for each OTU ID), was read in so that the different aspects of the json could be altered and fit into a provided html file to showcase the data in various ways.  The names data was called as a variable, and the id for a dropdown menu in the html was called.  The names variable was looped to add the names (patients ids) to the dropdown so that once the rest of the code was finished each patient ids' information could be viewed by selecting it from this dropdown.  So that each ids data showed on the page, a function optionChanged was called.  This function read the json file in once more, then after calling the metadata and samples parts of the data into their own variables, showed the metadata demographics for each patient id, created a horizontal bar graph showing the top 10 OTU IDS and their value count for each patient ID and then a bubble graph of all the OTU IDs for each patient where the bubble size was based on the value count for each OTU ID.  For the metadata portion, the data was filtered by the patitent id, the metadata box id was grabbed from the appropriate html id, then a table was appended that looped through a list of the keys in the metadata and appended the necessary demographics in the table to be shown in the demographics box on the html page.  The samples portion of the data was filtered in the same way and the values for the otu ids, the otu labels, and the sample values for each otu id were made into their own lists of equal length so they could be correlated together by looping through the length of one and appending the associated values into a dictionary list.  The dictionary list was sorted in descending order and then the top 10 were sliced out for the bar graph.  The top ten was also reversed since the Plotly function defaults creating bar graphs from the top down.  The first trace was created using the values from the reversed, sorted and sliced dictionary list to create the bar chart.  A second trace was created for the bubble chart using the individual lists of the otu ids, otu labels and sample values.  When any of the patient ids taken from the dropdown, the correct values for the demographics, bar chart and bubble chart are updated and displayed on the html page.

![D3_graph](https://user-images.githubusercontent.com/65049133/121834892-b3d8a080-cc84-11eb-9851-9b1c2e93975b.png)

