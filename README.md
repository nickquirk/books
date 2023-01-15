
# Alexandria

This was the second project on the General Assembly Software Engineering Immersive course. We’d been learning the React framework and it was time to put into practice what we’d learnt over the past two weeks. 

I worked with Sussie to build a web app, which we called Alexandria, that allows a user to enter a subject and will return a random selection of fifty books which include that subject. 

![Alexandria front page](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620593/Readme_Pics/Project2/image6_mkgion.png)

## Deployment

The application can be accessed online here:
https://alexandria-project-2.netlify.app/
## Getting Started/Code Installation

Code can be access on GitHub here: https://github.com/nickquirk/books

Open with code editor and then run

```
npm i
```


## Timeframe & Working Team
This was a pair coding project and I was paired with Sussie (https://github.com/sue360). We had just less than 48 hours to meet the criteria of the project and produce a working online React application. 
## Technologies Used
**Development Tools**
* Visual Studio Code - IDE
* Insomnia - API interface
* Yarn - Package manager
**Frameworks**
* React - JavaScript framework
* Sass - CSS extension language
* Axios - HTTP client 
* Bootstrap - Frontend toolkit
**APIs**
* The Open Library API: https://openlibrary.org/developers/api
## Brief
The brief was to build a React application that consumes a public API. There were several other criteria:

* The application must have several components 
* Have a router component and several pages, if it makes sense
* Include wireframes of main pages 
* Be deployed online

## Planning
Before meeting, Sussie and I spent some time brainstorming and finding some APIs that looked interesting and had enough functionality to work with. These ranged from the Bored API, which suggests random activities, to the Chuck Norris Facts API which returns hilarious, fictional facts about actor Chuck Norris. 

In our first session together, Sussie and I went through our initial research and discussed possible ideas with the APIs that we’d found. Nothing seemed to spark our combined interest so we went back to the drawing board and eventually found common ground with the Open Library. I have a huge passion for books and Sussie is a published author so a project in this domain seemed very appropriate and something we could both get excited about. 

 The Open Library  is actually a group of APIs which include the following functionality amongst several others.   
* Books API - Retrieve a specific work or edition by identifier
* Authors API - Retrieve an author and their works by author identifier
* Subjects API - Fetch books by subject name
* Covers API - Fetch book covers by ISBN or Open Library identifier

We both instantly saw the potential of this API to create something fun, informative and engaging.

After we’d picked the API we would work with, we sketched out some initial wireframes. We imagined a simple three page application with a landing page which would take the user through to a selection of books with the functionality to get more information about a specific book when it was selected. 

### Initial Research 
Before we started the planning phase properly we took some time to experiment with the API to make sure that we could access all of the data that we needed for our project. We used insomnia to test each API end-point to make sure we could get what we needed but also to make sure we understood which format the data was in and which methods we would need to use if we needed to drill down further into the data. 

### Wireframes
**Front Page**
![front page wireframe](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620589/Readme_Pics/Project2/image9_yz5t8h.png)

**Book Index**
![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620590/Readme_Pics/Project2/image11_rgvoyf.png)

**Book Detail**
![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620589/Readme_Pics/Project2/image1_t6bp9p.png)

### Shared Planning Document 
Because of the timeframe of this project, we decided to create a planning document using tools we were both familiar with. A shared Google Doc became our main planning area. 

### Minimum Viable Product 
Together we developed the following MVP, which would be the very minimum that would fulfil the project criteria,

* Get a sample of books from a certain subject 
* Can zoom in on one book and get details 
* Can display book covers using book ID 

Once we had developed our MVP, we had some fun thinking up some interesting stretch goals which we would implement once our MVP was built. 

### Stretch Goals
* Info about author - other works
* Can add books to a reading list 
* Can link styling to keywords in the subject array e.g. the tag ‘space’ toggles a space themed background
* Option for users to enter new genres/keywords that will feed into the API url to get a different dataset back
* Multiple book covers on individual book pages (on a carousel)
* Can search by Author, Book, subject, calling different APIs
* Snazzy border around award winning books
  * gold/moving? 
  * Add as class?

### Division of work
Initially we attempted to use the VSCode Live Coding feature that allows for collaboration on the same project at the same time (similar to Google Docs). We tried for a while to get this to work but Sussie had some issues with VSCode and because of the short timeframe of the project we decided to take an alternative approach. 

In the end, we decided to code this project together, sharing a screen and both contributing whilst one person coded. This kept things nice and simple and allowed us to get up and running quickly.

### Prject Breakdown
The final part of our planning phase was to break our project down into sections, thinking of the main components and functions that we would need to fulfil the brief. 

**Data**

Book data that we will retrieve will include: 
* Name
* Author
* Date of publication
* Cover
* Description
* Subjects (main themes of book) 

**Functions**
* getBooks 
* displayBooks - in return of BooksIndex
* Get book single - data from single book key (Data.works[0].key)
* Get a new selection of books from new subject

**Components**

**Pages**
* Home - Landing page
* Navbar
* BookIndex
* BookSIngle
* Error 
**Helpers** 
* Token authentication
**CSS**
* Simple styling
* Using SCSS and bootstrap where possible 







## Build/Code Process
As I mentioned previously, our approach to this project was to code together on most parts. There was some individual work but most of the main functionality was figured out as a team. In the end, we pretty much kept to the structure we agreed on in our plan. We were using Yarn as our package manager and ran a local server in order to see the changes we were making to our code. 

Three main page components 
* Home
* BookIndex
* BookSingle 

One ‘common’ component that would appear on all pages
* PageNavbar

All styling was done with Sass in
* main.scss

### App.js
This acted like a hub for all other components. It contained our Navbar and we used the Route and Routes components to navigate between pages. For the BookIndex and BookSIngle pages we used placeholders so that we could parse the subject written by the user and the individual book id into the address bar. 

![code of app.js](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620590/Readme_Pics/Project2/image8_gmb0wp.png)

### Home.js
This acts as the landing page for our application. It's the first page that a user will see and it introduces them to the functionality of the site. For that reason, we kept it quite simple. We wanted it to be really easy for a user to determine what our site does and how they should interact with it. We did some basic styling but kept the layout very minimal with just a text input for the user to type in their desired subject. 

![homepage](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620591/Readme_Pics/Project2/image7_sbira8.png)

We used conditional logic to ensure that the user was not taken through to the index page without entering a subject. If the subject field was empty, the user would remain on the home page. 
![Book Index page](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620590/Readme_Pics/Project2/image14_ghbveu.png)

### BookIndex.js
This component displays a selection of 54 books from the larger pool of book data that we were gathering from the Open Library APIs. We chose to display 54 books because it was a large enough selection to be interesting and also worked well with the column layout of the page, dividing equally between 3 and 2 when the page was resized. 

We used the Axios HTTP client to interact with our APIs and retrieve the information that we needed. This was done within a useEffect listening for changes on the subject variable. In this component we are parsing the subject that the user has typed into the Axios https request to retrieve data about 200 books. Initially we had this limit set to 1000 but found that this caused an unacceptable delay in load time. We found a sweet spot at 200 books which took between 5 - 10 seconds to load.  

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620591/Readme_Pics/Project2/image16_bqctha.png)

We used ternaries to return the text string ’Undefined’ if the data was in an unexpected format. This attempted to prevent our app breaking if it couldn’t access data for any reason. 

### Displaying Data
Inside the map function, the data we retrieved from each book was displayed within a Card object. We felt this was a good format to display our books with the functionality to display a picture and then text beneath each entry. We used conditional logic to show a loading screen with a gif when the books were being loaded and also to display any error messages.

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620591/Readme_Pics/Project2/image12_dxyuma.png)

**Loading Graphic**

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620590/Readme_Pics/Project2/image10_eyluby.png)

The data we had deconstructed from each book object was then displayed in a flex grid that changed size depending on the size of the viewing screen. We displayed the title of the book, the author and the year of first publication. 

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620589/Readme_Pics/Project2/image5_iyi2e9.png)

### Random Selection
One functionality we really wanted to include was that the selection of books that was returned was different on every search. This ended up being quite a tricky problem to solve but was really satisfying when we did! 

The approach we took was to create an array of 54 random numbers between 0 - 200 (total number of books in Axios API request) making use of the JavaScript Math.random and floor functionality. We then used conditional logic to ensure that there were no duplicate numbers in the array. 

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620591/Readme_Pics/Project2/image18_qkprgw.png)

In a separate function, we then mapped through this array, using the numbers to return the book object that was in that location in the main array of books and create a new array of book objects. 

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620591/Readme_Pics/Project2/image15_cm4yjq.png)

This then became the array of books that we would use to populate our index page. 

### BookSingle.js
When a user clicked on a single book they were taken through to a page where there was more information about the book. A description and the main themes explored. 

On this page we used a similar Axios request to get data but we used the Works API instead of subject. We used the individual bookId that we extracted from the Subject API to make the request. 

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620591/Readme_Pics/Project2/image16_bqctha.png)

### Error Handling
We discovered that some of the book descriptions were in the form of an object and some were in the form of an array so we created a function to test the type of the data and then return the data in the appropriate form. 

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620590/Readme_Pics/Project2/image13_lxf3jm.png)

### Subjects
We also noticed that there could  be between 20 - 100 different subjects for each book so we used a function to trim them down to the first 10. 

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620589/Readme_Pics/Project2/image2_kgjgii.png)

### Display
Book data was displayed using a similar method to the index page and using conditional logic to check that the data was usable.

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620589/Readme_Pics/Project2/image3_dseyte.png)

We displayed the book cover to the left and the Title, description and subjects to the right with a button to go back to the main book index. 

![](https://res.cloudinary.com/dhjguxvm1/image/upload/v1673620590/Readme_Pics/Project2/image4_nqnwjs.png)

## Challenges
I think the main challenge for this project was the timeframe we were given. We had under 48 hours to complete our MVP so we had to be really efficient with our planning and build process. Working in a pair made this slightly more of a challenge and it meant we didn’t have much time to figure out how we could best work together but I think we ended up with a good working dynamic. 

Some other challenges we ran into were:

* Understanding and interpreting data from APIs into a form we could use 
* Adapting to building an application in a pair
* Error processing
* Ensured user input did not break the program (spaces etc)
    * Useful error messages are displayed to user 
    * Displaying a random selection of books for each request




## Wins
* Had a really enjoyable collaboration with Sussie
* Combining data from several APIs 
* I like our method for randomising books
* Our application is genuinely useful 
* We both found books we wanted to read 
* Inspired loads of conversations about books! 
* It works! 

## Key Learnings/Takeaways 
* Learnt to code in a pair 
* Solidified my knowledge of React framework
* You can never work quickly enough! 

## Bugs
* Search sometimes doesn’t return any results and there is no error message 
## Future Improvements 
Because of the time restraints imposed with this project I feel like we ended up with more of a proof of concept than a fully polished product. We didn’t get round to implementing any of our stretch goals which was a shame because I think it would have added some really interesting functionality. In addition to our stretch goals there are some future improvements we’d like to add.

* A reading list functionality which would allow users to save a list of books from the selection offered.
* If the book has multiple covers then these would be shown in a ‘carousel’ type effect. 
* Add a search bar to the Navbar so users can search for a new subject anywhere on the site. 
* Improve general styling and interface components. 
* Limit book description to 150 words and implement a  ‘read more’ button that displays the rest of the description when clicked.
* Automatically update subject placeholder text field with different suggested searches. For example ‘Have you tried Science-Fiction?’, ‘What about Romance?’
