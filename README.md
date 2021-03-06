# Data Centric Development Project

This project is an online website for book recommendations and reviews. The goal was to make a site with backend database functionality using MongoDB. This site should allow users to modify the database by creating, updating, deleting as well as reading from it.

This is the third project as part of my [Code Institute](https://codeinstitute.net/) online diploma course.

---

## User Experience Design

### User Stories

These are potential actions that users of the website would want to perform. 

* As a user, I would like to be able to search for a book recommendation.
* As a user, I would like to add a review for a book.
* As a user, I would like to be able to change a review.
* As a user, I would like to delete reviews

---

### Wireframes

![Desktop Homepage](wireframes/home-desktop.jpg "Desktop Homepage")

![Tablet Homepage](wireframes/home-tablet.jpg "Tablet Homepage")

![Mobile Homepage](wireframes/home-mobile.jpg "Mobile Homepage")

![Desktop Search Results](wireframes/search-desktop.jpg "Desktop Search Results")

![Mobile Search Results](wireframes/search-mobile.jpg "Mobile Search Results")

## Database

Need to be able to store information on books. Since users are adding reviews for books, also need to store that too. Database must use MongoDB.

### Design

Book data to store: Title, Author and Link to a cover image of the book.

Review Data to store: User Name, Review content

Since one book can have many reviews, will store reviews as an embedded document inside the book document.

Book --> Title, Author, Cover Link, Review Data --> User Name, Content


### Implementation

Book data selected from sixteen random books on [Open Libary](openlibrary.org). This data was then added to the database using the MongoDB command line.

Review data was left blank and inserted later when the database was linked to the website. 


## Features

### Index Page

Index page has a collapsible navbar implemented using bootstrap. Site logo provides a link back to the index page. Navbar also has search box which goes to the search page, and an "All Books" button which goes to the all books page.

The main content on the index page is a link to a random book on the site. This link is generated when the index page is navigated to. It displays the random book cover, title and author; and clicking on it brings you to that book.

### All Books Page

When navigated to, the all books page fetches all of the books in the database, then displays them to the screen using HTML and CSS. Each of the books is a link to the individual book.

The information is displayed in a column on mobile, and expands to multiple columns on bigger screens. This is accomplished with bootstrap's grid system.

### Search Page

Much like the 'All Books' page, this fetches some of the book data and displays it to the screen. The difference is that it only returns data which matches the search terms entered by the user.

MongoDB's find command is utilised in conjunction with a regular expression to make sure only the searched for data is returned.

### Book Review Page

The actual book page gets the requested book and displays its data to the screen. It also displays the review data from the database. There is an "Add Review" button which takes the user to the add review page.

Each review has both an edit review and delete review button. Clicking delete will remove the review from the database and refresh the page. Clicking edit will take the user to the edit review page.

### Edit/Add Review Page

These pages are similar in functionality. Both allow the user to enter a username and user review into a form. When the form is posted, the data is stored in the database and then displayed on the book page, which the user is redirected to.

The difference is that the edit review page loads with the previous database data already entered.

### Potential Additional Features

* Could add ability for users/admin to delete books
* Could get more books from another source
* Could get more book info for database (page counts, ISBN etc)

## Testing

### User Stories Revisited

* *As a user, I would like to be able to search for a book recommendation.*
 
The search box in the nav bar can be used to search for the required books.

* *As a user, I would like to add a review for a book.*
 
On the book page, users can click the 'Add Review' button which will allow them to do so.

* *As a user, I would like to be able to change a review.*
 
On the book page, the 'Edit Review' button allows users to do this.
 
* *As a user, I would like to delete reviews*

Inside the review box, there is a 'Delete Review' button which will remove the review from the database



## Deployment

Application was deployed to Heroku. The steps for this are as follows:

1. After logging into my Heroku account, I clicked 'New' and then 'Create New App'
2. I have to give my new app a name and pick my region as Europe.
3. I had to link my GitHub repository, containing all my code, to Heroku so I clicked the 'Deploy' tab.
4. I enter the details of my account and repository to link the two.
5. I then have to enable automatic deploys, so when I push to GitHub, it deploys my code to Heroku; so I click on that.
6. I had to enable environment variables for my project, so I click on 'Settings' > 'Reveal Config Vars' and enter in the ones my project uses.
7. I have to generate a Procfile for my project, which I did by typing "echo web: python run.py > Procfile" into the terminal.
8. I had to generate a requirements file as well, which I did by typing "sudo pip3 freeze --local > requirements.txt" into the terminal.
9. I had to disable the debug environment before deployment, which I did by removing 'True' from the line in my run.py file, and replacing it with 'False'
10. Once I have these changes added and committed using git, I had to push them to my git repository using 'git push' in the terminal. This also pushed the project to Heroku, where it began automatically installing dependencies and deploying the project.


## Credits

### Content

* Book icon on navbar courtesy of Font Awesome
* Navbar font and general site font taken from Google Fonts

### Media

* Book images and data taken from [Open Library](openlibrary.org)
* 'No book' image taken and modified from [here](https://cdn.pixabay.com/photo/2018/01/17/18/43/book-3088777_1280.png)


### Code

* Various code snippets copied from [Bootstrap's site](https://getbootstrap.com/)
* Four column code for search page and all books page taken from [here](https://startbootstrap.com/snippets/portfolio-four-column/)
* Code for fixing the footer in place copied from [here](https://www.freecodecamp.org/news/how-to-keep-your-footer-where-it-belongs-59c6aa05c59c/)