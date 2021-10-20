# Cow List Alternative (Books To Read)

## Copyright

These instructions are copyrighted material and may not be distributed without permission. If you did not get a link to this document _directly from your Hack Reactor/Galvanize instructor_, please ask whoever sent it to you to stop sharing this link.

## Instructions

Read this entire document before starting your work. Complete the work in order.

## Goal

This is an alternative assignment to Cow List. Essentially you will be creating a very similar application of your choice, as long as you complete the basic requirements. These instructions will give an example of an application that you could make that meets those requirements, or you are free to be creative and make your own that fulfills the requirements.

The example we will be using is for a Books To Read application. This application will keep track of what books you want to read this year and a section displaying what book you are currently reading.

Create a CRUD app using React (without Redux) that interfaces with a RESTful API powered by Node (with Express) and a database (MySQL) from scratch.

Don't use anything that writes code for you (like `create-react-app`). Don't forget to commit regularly and upload your work to GitHub!

Stick to using only the official documentation and StackOverflow. Limit your use of video and blog post tutorials. Whenever you find a solution on StackOverflow, always find where in the official documentation you can find the same answer.

### Permitted technlogies

1. For server: Node.js with [Express](https://www.npmjs.com/package/express) and [nodemon](https://www.npmjs.com/package/nodemon)
1. For frontend: [React](https://www.npmjs.com/package/react) with JSX
1. For AJAX requests: [jQuery](https://www.npmjs.com/package/jquery), [axios](https://www.npmjs.com/package/axios),or fetch
1. For database: MySQL (with [mysql](https://www.npmjs.com/package/mysql))

Do not use jQuery for any DOM manipulations.

## Bare Minimum Requirements

### Backend Requirements

Create a RESTful API for a resource that responds to GET and POST requirements. In our Books To Read Example it would look like this:

| intention           | request type | request url | request body                              | side effect                    | response body                                                                    |
| ------------------- | :----------: | ----------- | ----------------------------------------- | ------------------------------ | -------------------------------------------------------------------------------- |
| read all books data   |     GET      | `/api/books` | none                                      | none                           | `[{name: 'The Great Gatsby', description: '...'}, {name: 'Gone With The Wind', description: '...'}]` |
| create new book data |     POST     | `/api/books` | `{name: 'War and Peace', description: '...'}` | creates new record in database | `{name: 'War and Peace', description: '...'}`                                        |

Your web server should 100% be interfacing with a database for this phase. Confirm this functionality is working properly with Postman (recommended) or via the `curl` command in your terminal.

### Frontend Requirements

Build the `Create` and `Read` functionality of a CRUD app using React. The frontend should make use of the already created, in the previous section, RESTful API endpoints to accomplish the following user stories:

1. When the user loads the page, the user should see a list of all names of previously created data (in our example, books).

1. When the user types the name and description of a new datum (in our example, book) they want to input into the database and presses the `[Submit]` button, the newly created datum's information should be displayed in the list from the previous step **only after the data has been successfully written to the database**.

1. When the user clicks on an item in the list, another component should update with information. For example, when the user clicks on an item in the list, it can be displayed at the top of the page as the book you are currently reading (with more information like author, genre, description, etc.). Be creative but make sure to follow the main point of two components controlled by a parent where an event fired from the first component updates data in the second component. When another item is clicked, that second component should update again.

### Example Data:

| id  | name      | author  | description |
| --- | --------- | --------| ------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1   | War and Peace | Leo Tolstoy | Following Napoleon's invasion of Russia... |
| 2   | Gone With the Wind    | Margaret Mitchell | An epic Civil War drama... |
| 3   | The Great Gatsby | F. Scott Fitzgerald | Set in the American Jazz Era... |                                                     |

Note: This data should be inserted via your SQL script.

```
This is the end of the Bare Minimum Requirements section.
```

## More Practice

Add the backend functionality that allows users to update existing records and delete existing records. The response from the RESTful API should be that of the updated (or deleted) record.

| intention             | request type | request url     | request body          | side effect                                                  | response body                             |
| --------------------- | :----------: | --------------- | --------------------- | ------------------------------------------------------------ | ----------------------------------------- |
| update one book's data |     PUT      | `/api/books/:id` | `{name: 'War and Peace - Wishbone Version'}` | updates record for specified id with new name of `War and Peace - Wishbone Version` | `{name: 'War and Peace - Wishbone Version', description: '...'}` |
| delete one book's data |    DELETE    | `/api/books/:id` | none                  | deletes record for specified id                              | `{name: 'War and Peace - Wishbone Version', description: '...'}` |

Confirm this functionality is working properly with Postman (recommended) or via the `curl` command in your terminal.

Next, add the frontend functionality that allows users to edit existing records and delete existing records (via your RESTful API).
