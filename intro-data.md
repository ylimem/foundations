## Step 1. Copy this GitHub Repository

Copy code from another repository into your own and start editing it.

1. Make sure you're logged into your account on [GitHub](https://github.com)
2. Scroll to the top of the [foundations-3-github](https://github.com/learn-static/foundations-3-github) repository and click the green "Use This Template" button (appears on the right side above the code area)
4. This brings you to a "Create a new repository" form. Follow these steps:
    1. In the **Repository name** text box, give your repository the name `data-foundations`. If you'd like to create your own name for the repository, be sure to use a lowercase name without spaces or odd characters. Dashes (`-`) or underscores (`_`) are okay.
    2. In the **Description** text box, add `A place to learn metadata basics`.
    3. Select the option for "**Public**" repository.
    4. Leave the "Include all branches" option **Unchecked**!
    5. Click on the green button "**Create repository from template**". This will take you to your new repository.

!["Create a new repository"](https://github.com/learn-static/foundations-3-data/blob/main/images/new-repo.png)


## Step 2. Activate GitHub Pages

1. On your project repository's home page, click the "Settings" button (appears on the right along the tabs above the code area).
2. On "**Settings**" page: click "**Pages**" in the left side menu.
3. On the "**Pages**" page: in the "**Source**" section, change the dropdown button from "none" to "main" (leave the folder option as "/root"), then click the "**Save**" button. 

Once saved, the page will refresh with an alert providing the URL where your site will appear. 
It will take a few minutes for the build to happen and your site to go live--so wait it out! 

Meanwhile, you might want to copy the URL to display on your home page:

1. Copy the provided URL.
2. Go to repository's GitHub Pages home page.
3. On right side of the code area, look for "**About**" section and click on the cog icon to edit. 
4. In the "**About**" box, paste in your URL, then click "**Save**". This will make it easy to access the site in the future!

## Step 3. Explore your website

1. Navigate to the GithHub Pages website you just activated, and explore it! Your site should have two pages: a homepage with pictures of cute pets, and a "**Map**" page that you can access from the menu at the top of the homepage.
2. Where is Loulou, Flaubert's parrot, shown on your map? Oh no! It looks like her pin is not in Paris. To discover how your website is built, and how to fix this error, go to the next step.

## Step 4. Explore how your repository uses metadata to create your website

1. From the main page of your GitHub repository, click into the "**images**" folder, and notice that the jpg files that create the images of the pets on your website are all in this folder. Click on loulou.jpg to confirm it's the same image that you see in Loulou's profile on your website's home page. 
2. Now return to the main page of your GitHub repository. Click into the "**\_data**" folder and click on the **pets.csv** file to open it. Notice that GitHub has formatted the information that appears as a table or spreadsheet: the first row represents the names or titles of the columns of data below them. Note that the file names in the **image** column correspond to image filenames in the "**images**" folder. 

**pets.csv** is a _metadata file_--a file with additional information (data) about the image file that it refers to. In this case, each row in the csv (spreadsheet) contains information about the pet in the image, including its owner and location.

3. Find Loulou's row and explore the data in it. What is the incorrect information that is causing Loulou's pin to not appear in France as it's supposed to?

## Step 5. Import your metadata file into Google Sheets with a Google Sheets Function

While you can edit one or two simple values directly in the GitHub browser window, for any edits beyond changing one or two cells we recommend editing your file (**pets.csv**) in a spreadsheet editing program and re-uploading your metadata to your GitHub repository. You can edit your file in Google Sheets or LibreOffice, an open source alternative to Excel.

Technical note: please _don't_ open your csv file with Excel. Although Excel is a powerful program in many ways, it does not support UTF-8 encoding, and will make your csv file unusable.

The easiest way to import **pets.csv** takes advantage of Google Sheets' powerful import capabilities:

1. Open **pets.csv** within GitHub and click on the "Raw" tab in the top right hand corner. The url you have navigated to will be something similar to https://raw.githubusercontent.com/learn-static/foundations-3-data/main/_data/pets.csv (but with your GitHub username replacing learn-static). Copy this url to your clipboard.

Notice that as advertised, the main pane of your browser window now shows the data in a plain text format (text without formatting). The value of each cell (box) in what GitHub displayed as a table or spreadsheet is in fact a bit of text, and individual cells are separated by a comma. This plain text, comma separated format is the true csv--the table you saw GitHub create is an interpretation or visualization of that underlying document. 

2. Open a new, blank Google Sheet. 
    - Notice that all cells (boxes) in a Google Sheet can be described by the combination of their column letter and row number. Thus, the cell in the upper left-hand corner of any Google Sheet is A1, which is above A2 and to the left of B1, and so on.
    - In cell A1, enter the `IMPORTDATA` function to tell Google to import the data direcly from this GitHub url. 
    - Like other formulas and functions in Google Sheets, this function begins with an `=` to tell Google you are entering a formula, and the function is followed by information explaining what you want the command to do in parentheses. 
    - As [Google's official IMPORTDATA documentation](https://support.google.com/docs/answer/3093335?hl=en) explains, your url should be in parentheses, in the form =IMPORTDATA("www.yoururl.com"). 
    - In the case of the author of this document, the command will be =IMPORTDATA("https://raw.githubusercontent.com/gabrielesh/foundations-3-data/main/_data/pets.csv")
4. As soon as you enter this command in full, the spreadsheet should populate with your **pets.csv** data. Name your document "pets" by typing "pets" in the box labled "Untitled Spreadsheet" in the top left hand corner of your Google Sheet.
5. In order to avoid having the spreadsheet update in response to any changes to the GitHub data, you can eliminate the IMPORTDATA command:
    - copy cells A1:I17 (all of the cells that include data in your spreadsheet) by selecting the cells with your mouse or touchpad, and copying. You can copy by selecting Command + C (Mac) or Ctrl + C (PC) or by navigating to the Google Sheets menu and selecting **Edit > Copy**.
    - With the cells still selected, paste your copied text as values only. You can do this by selecting Command + Shift + V (Mac) or Ctrl + Shift + V (PC) or navigating to the Google Sheets menu and selecting **Edit > Paste Special> Paste Values Only**.
    - Now select cell A1 and notice that your command has been erased--only the word "name" remains.

## Alternative: Manually import pets.csv into Google Sheets

1. Open **pets.csv** within GitHub and click on the "Raw" tab in the top right hand corner. The url you have navigated to will be something similar to https://raw.githubusercontent.com/learn-static/foundations-3-data/main/_data/pets.csv (but with your GitHub username replacing learn-static). 

The main pane of the browser window will now show the data in a plain text format (text without formatting). The value of each cell (box) in what GitHub displayed as a table or spreadsheet is in fact a bit of text, and individual cells are separated by a comma. This plain text, comma separated format is the true csv--the table you saw GitHub create is an interpretation or visualization of that underlying document. 

2. While on the page with your raw csv, choose the "**File**" dropdown from your browser menu. Select "**Save Page As**" and save **pets.csv** to somehwere on your computer where you can find it again.
3. Next, open Google Sheets and upload **pets.csv**:
    - Navigate to sheets.google.com. Sign into your Google account or create a google account, as needed.
    - Select the icon in the top left corner to create a new, blank, spreadsheet.
    - Navigate to File > Import, and select the "Upload" tab. 
    - Drag your **pets.csv** document into the "upload" area, or click "Select a file from your device" to select the document using your computer's browse function.

You can also open **pets.csv** in LibreOffice, an open source alternative to Excel. Please _don't_ open your csv file with Excel. Although Excel is a powerful program in many ways, it does not support UTF-8 encoding, and will make your csv file unusable.

## Step 6. Fix Loulou's location
1. A quick Google search confirms that the latitude and longitude of Paris, France are 48.864716 and -2.349014. Enter these into your spreadsheet.

## Step 7. Explore more of Google Sheets' powerful editing capabilities
You already explored one example of Google Sheets's powerful functions. Consider trying out another:
- Notice that all the pet names are in lowercase. Use the =PROPER() formula to convert them to title case (first letter capitalized). 
    * Insert a new column between A (name) and B (type) and type "name" in the new cell B2. To do this, hover over the box labeled B, click the dropdown arrow, and select "Insert 1 left."
    * Type "name" in the new B1.
    * In B2, type "=PROPER(A2)". 
    * Copy this formula for all the rows in your spreadsheet, either by choosing "Autofill" when prompted, or by hovering over the bottom right corner of your cell until the cursor becomes a plus sign (called the fill handle), then double clicking.
    * Select the cells from B2 to the end of the spreadsheet with your cursor and use the copy and paste values trick you learned earlier in this lesson to remove the formulas and retain only the animals' names, now with their correct capitalization. As a reminder, the sequence is select, copy (Command + C or Ctrl + C), paste values (Command + Shift + V or Ctrl + Shift + V).
    * Delete column A (with the lowercase names) by hovering over the box labeled A, selecting the dropdown arrow, and choosing "Delete column."

## Step 8. Download pets.csv to your computer and upload it to GitHub
1. Download **pets.csv** by selecting from the Google Sheets Menu File > Download > Comma-separated values (csv, current sheet). Make sure it is still named pets.csv (delete any reference to a sheet name).
2. Save the file where you can find it again.
3. Navigate to the `_data` folder in your GitHub repository. There should be one file (pets.csv) in this folder. Select Add File > Upload Files from the menu above and to the right of the main box listing the contents of the folder. 
4. Drag your files into the box, or click the link to browse to find your new version of pets.csv. **Important: your updated file must be named pets.csv in order for it to over-write the older file and be read by the program that creates your website.**
5. Add a commit message, such as "fixed errors in pets.csv metadata file." Consider saying in your description what errors you fixed.
6. Hit the button to "Commit changes."

## Step 9: Admire your work
Congratulations! Now navigate to your website to admire how the changes you made to your metadata file have improved the look of your website!
