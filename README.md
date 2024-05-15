# HTML-challenge
This weeks challenge has me taking on a full web-scraping and data analysis project. Using Splinter and HTML parsing with Beautiful Soup, I will extract needed imformation from a site containing information on mars. The goal of this challenge is to further stregnthen the core skills I've been developing until now: collecting data, organizing and storing data, analyzing data, and then visually communicating your insights.

# Going about the challenge
Using splinter to browse the url 'https://static.bc-edx.com/data/web/...', I identified key ID and class attirbutes in the HTML source code to extract meaningful information via beautiful soup. After scraping the data, it was stored in a pandas data frame that would be used to generate visualizations of the data. These visualizations could then help to answer several questions about mars such as its number of months or how many earth days were in a Martian year. Finally, the pandas data frame was exported to a csv file for referencing. 

# In closing
This week's assignment was striaght forward. It made use of tools we learned in class last week while recapping on previously used data manipulation techniques. 

I did have troubles in part 2 of the assignment extracting data from the html table and storing it into a pandas data frame. For some reason or another, the code I used made all data entries appear in a list, square bracket []. To over come this, I had to run a for loop within a for loop to handle the data. There may have been a more efficient way to go about this. I will include a sample of that code below in case anyone reading this, including my assignment grader, wants to comment on a better way to go about this code.

Sample code:

data_entry = []

#obtaining a list of table rows (from html site)
t_rows = data.find_all('tr', attrs="data-row")

for row in t_rows:
    items = row.find_all('td')
    lst = []
    for item in items:
        cell_data = item.text  
        lst.append(cell_data)
    data_entry.append(lst)


