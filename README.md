# assignment1-csci4930
Assignment 1: Data Scraping

Web scraping involves programmatically collecting data from web pages. This is a hugely valuable skill in machine learning and AI, where creating datasets often relies on publicly available information. With the explosion of online data, the ability to extract and structure this information for analysis has become a foundational skill in the AI toolbox. For example, datasets for computer vision tasks, recommendation systems, and natural language processing often start as unstructured data pulled from websites.

For this assignment, we’ll focus on developing practical web scraping skills using BeautifulSoup, a powerful Python library for parsing HTML documents. While this assignment emphasizes the technical skills needed to extract data, it’s important to recognize that web scraping raises complex ethical and legal questions about copyright, terms of use, and data privacy. These issues will (continue to be) discussed in depth during class discussions.

In Class Activity for Tuesday, January 28th (in pairs)
In preparation for the assignment, we will practice using BeautifulSoup to scrape data from web pages. This activity will help you understand how to navigate HTML documents, locate relevant tags, and handle pagination when scraping multiple pages of data.

During class on January 28th, you are going to break into pairs. You may choose your own pair, but you should work with someone who has the same operating system as you for convenience. (If there are an odd number of students, one group may have 3 people.)

As a pair, you should work through the tutorial on using BeautifulSoup at https://realpython.com/beautiful-soup-web-scraper-python/Links to an external site.. You should both read through everything up through "Step 1: Inspect Your Data Source" quietly, and then should work as a pair to actually implement the code from the tutorial on your computer. You can do this either by assembling it into .py files or by working in a notebook.

Once you have worked through this and can successfully scrape the Fake Python jobs website, you should read about how to handle "Pagination" in this medium article: https://medium.com/analytics-vidhya/webscraping-a-site-with-pagination-using-beautifulsoup-fa0a09804445Links to an external site. (it reiterates a lot of the basic points from the previous tutorial but is pretty short, so worth reading the whole thing).

Assignment (on your own)
You will apply your web scraping skills to scrape all of the image URLs from a specific webpage and its subsequent paginated results.

1. The Target Webpage
URL: https://www.loc.gov/pictures/search/?q=students&st=galleryLinks to an external site.
This webpage contains search results for images related to "students" in the Library of Congress online catalog.
Important: This search yields multiple pages of results. There are 7,396 total entries.

2. Data to Extract
Image Title – Usually found in a relevant HTML tag (e.g., alt attribute for images or sometimes a separate <div>/<h3> tag describing the image). You will need to inspect the webpage’s HTML to find the most accurate field for the title or description. Hint: right clicking on an object on a page and clicking "Inspect" (or your browser's equivalent of it) will take you right to the relevant HTML for that object. You may want to search for info on how to use Developer tools in your browser.
Source URL – The webpage URL where the image or record is found (the detail page for each image) -- this is the webpage that opens if you actually clicked on the image.
Image File URL – The direct URL to the image file (or the thumbnail image).
3. Requirements
You must write Python code (either in a .py or iPython notebook file) that:

Scrapes All Results
You must collect data from all available pages. This means you need to figure out how to:

Identify the total number of pages or how to detect the “Next” link.
Traverse each result page systematically until you have all 7,396 entries.
Saves Your Results to a CSV

File Name: loc_images.csv
Headers: ["Image Title", "Source URL", "Image File URL"]
Total Entries: 7,396 rows (excluding the header row).
4. Submission Details
The assignment is due Friday, February 7th at 11:59pm. It will be accepted through Monday, February 10th at 11:59pm with a 10% late penalty. Submissions will not accepted after that.

You should turn in a zip file that contains:

scrape_loc.py (or Jupyter Notebook) containing:
Code for scraping the site and iterating through all pages.
Clear comments describing your approach.
loc_images.csv containing exactly 7,396 rows + 1 header row (with only the fields that I ask you to gather (["Image Title", "Source URL", "Image File URL"])
It is your responsibility to make sure that your files open, can be run, and that your zip file isn't corrupted. If I can't open your file or run it, it won't be graded.

5. Hints and Advice
Locate the Pagination Links: Look for a section of the HTML that contains pagination links (possibly with class="pagination" or an element labeled “Next”). Examine the hyperlink to the next page to build a loop over all pages.

Filtering or Skipping Non-Image Elements: Not all links or tags may lead to valid image results. You may have to look specifically for elements that contain the image information, such as thumbnails, resource detail links, or unique identifiers.

Performance Considerations:

Consider adding a small delay (time.sleep(0.5)) between requests to avoid being blocked from accessing the site.
Make sure you only request what you need.
6. Grading
This assignment will be graded on a 3 point scale, where you either receive the point or not:

Scraping Logic & Execution (1 point)

Code correctly uses requests and BeautifulSoup to retrieve and parse HTML.
Extracts required data fields (Title, Source URL, Image File URL) without errors.
Pagination Handling (1 point)

Implements a clear method to navigate through all pages (e.g., following “Next” links).
Collects data from every result page until all 7,396 entries are obtained.
Data Output & CSV (1 point)

Produces a CSV file named loc_images.csv with the exact headers and formatting.
Contains exactly 7,396 rows of data plus one header row.
Choose a submission type
