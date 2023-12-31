# Artifact Three - Databases: SQL Database Application
[Link to the original and enhanced artifact](https://github.com/marcgregor/marcgregor.github.io/tree/main/Artifact%20Three%20-%20Customer%20Database)

## Briefly Describe the Artifact. What is it? When was it Created?
Originally, it was a simple project to create a SQL database to hold customer information and run a few queries in DAD 220. Using MySQL, we were tasked to create a database and then populate a table with customer information. On top of that, we were supposed to run some queries as well to ensure that the database was created as intended. With the project, it showed our ability to run simple queries and introduced us to manipulating data based on the needs of what was required.
## Justify the Inclusion of the Artifact in your ePortfolio. Why did you Select this Item? What Specific Components of the Artifact Showcase your Skills and Abilities in Software Development? How was the Artifact Improved?
My main justification in including this artifact is that I thought I could produce a full working program that would be user friendly – after all, the original project was just on MySQL, and there was no front-end usage or anything that would represent a finished product. It should be noted that while I had originally planned on creating a full stack website, that plan changed – due to time constraints, I felt it would be difficult to produce a quality product, and more importantly, I am still in my first full stack course in this term, so I did not feel comfortable in being able to complete a finished website. Therefore, I changed to make it a workable program with a python front-end logic while using a SQLite database, but I was still able to showcase my skills and provide the same outcomes as before. I was still able to showcase my ability to create a program from the ground up, giving a front-end user experience while still successfully implementing data storage. I used two languages on this project, using python not only on the front-end user experience, but to also call SQLite queries. 
## Did you Meet the Course Objectives you Planned to Meet with the Enhancement in Module One? Do you have any Updates to your Outcome-Coverage Plans?
The following course objectives have been met:
### Outcome 1 - Employ strategies for building collaborative environments that enable diverse audiences to support organizational decision making in the field of computer science: 
I provided simple but concise in-line comments that provided not only the reasoning behind writing the code, but also the purpose of each main code block. I also used comments to split up the coding into different sections, such as initial setup and functions for user readability. I took the requirements given, gathered any additional information needed, and built the software around the requirements, while writing a narrative explaining the whys and hows of the enhancement. Finally, I wrote a reflective piece at the end of each enhancement to discuss my overall experience with the enhancement.
### Outcome 2 - Design, develop, and deliver professional-quality oral, written, and visual communications that are coherent, technically sound, and appropriately adapted to specific audiences and contexts:
These comments also provide a line of communication between the reader and developer, and this narrative allows the reader to understand what the artifact was, why I chose it, and also understand the improvements of the artifact. On top of that, the reflection describes my experience and explains what I considered to be the best overall practice to accomplishing the enhancement.
### Outcome 4 - Demonstrate an ability to use well-founded and innovative techniques, skills, and tools in computing practices for the purpose of implementing computer solutions that deliver value and accomplish industry-specific goals:
Outcome 4 is met because I was able to build a front-end user-friendly program with back-end data storage capability – while I used SQLite on this enhancement, it shouldn’t be too much of a challenge to swap it out with full SQL or NoSQL/MongoDB. I changed my plan in order to keep a realistic production schedule. I used iterative testing by gradually making small changes to the program based on feedback (from both the enhancement plan and the initial enhancement), as well as from trial and error – I decided to add on to the complexity of the program by adding in a sort feature by clicking on the headings of the table.
### Outcome 5 - Develop a security mindset that anticipates adversarial exploits in software architecture and designs to expose potential vulnerabilities, mitigate design flaws, and ensure privacy and enhanced security of data and resources:
With how common and serious SQL injections can be, security was a main focus. The main way I solved this was to use parameterized queries, which would prevent anyone from making additional queries while inputting data, fixing a potential serious design flaw and ensuring the data entered is valid. Future goals include adding more OOP features and enclosing it in a secured class, and I explained in detail why security needs to come first in my reflection. 
## Reflect on the Process of Enhancing and/or Modifying the Artifact. What did you Learn as you were Creating it and Improving it? What Challenges did you Face?
It was a challenge – it was the only artifact that I basically built from the ground-up – so it was the most extensive of the three by far. However, that’s why I found it so enjoyable. I built an entire piece of software from a single screenshot, and felt I was able to showcase my skills far more than the other two, since I was only modifying them. Overall, it went smoothly, as I used an extensive planning stage, allowing me to get a good grasp on what needed to be done before I ever wrote a single line of code. It cannot be stressed enough on just how important a security-first mindset is, especially when it comes to dealing with data. Injections are such a huge problem, so it is paramount to find ways to mitigate them as much as possible – this is where the parameterized queries really come into play.

# Original Artifact
![image](https://github.com/marcgregor/marcgregor.github.io/assets/120348789/e50620ba-7851-4451-8977-35a974634430)

The main screenshot I based the entire program off of - The table is called Customers, with CustomerID as the primnary key, with name and address information as the rest of the fields. 
# Pseudocode
```python

import tkinter
from tkinter import *
from tkinter import messagebox, ttk

from db import Database
db = Database('customers.db')

# Create window object
app = Tk()
app.title('Customer Manager')
app.configure(background='light blue')
app.geometry('800x500')
# Prevents window from being resized
app.resizable(False, False)

```
Like the slideshow, this program also utilized tkinter. On top of that, it also grabs information from a SQLite database (from another .py file), and then configures the initial set up, such as the background color and preventing the window from being resized.
# Enhanced Artifact
![image](https://github.com/marcgregor/marcgregor.github.io/assets/120348789/8991b986-f925-44fb-ab55-8e0285bc5fce)

The new program created from the screenshot. It has a simple UI that's easy to understand, with clear input fields and buttons. On top of that, you can sort the data by clicking on one of the table headings - this will sort it in ascending or descending order based on the field of the column.
```python

# Function to sort the Treeview by column
def sort_treeview(tree, col, descending):
    data = [(tree.set(item, col), item) for item in tree.get_children('')]
    data.sort(reverse=descending)
    for index, (val, item) in enumerate(data):
        tree.move(item, '', index)
    tree.heading(col, command=lambda: sort_treeview(tree, col, not descending))

```
This is the method that enables the option to sort by clicking on the header. It grabs the data of the correct column and then sorts it and ascending/descending order (depending on how many times the user clicks the heading). 
