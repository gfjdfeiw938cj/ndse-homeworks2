- Запросы для вставки данных о двух книгах в коллекцию `books`:

```
db.books.insertOne({
	title: "Beginning Node.js, Express & MongoDB Development",
	description: "",
	authors: ""
})

db.books.insertOne({
	title: "Node.js is an open source cross-platform JavaScript server runtime that runs on the JavaScript engine (i.e. V8 engine)",
	description: "Node.js allows developers to use JavaScript to write command-line tools and to create server—side scripts - running server-side scripts to create dynamic web page content before sending the page to the user's web browser. Hence, Node.js is a "JavaScript everywhere" paradigm[6] that unites the development of web applications around a single programming language, rather than different languages for server and client scenarios...",
	authors: "Nazarenko Artur"
})
```

- Запрос для поиска полей документов коллекции `books` по полю `title`:

```
db.books.find(
	{ title: /^Mongo/ },
	{ title: 1, description: 1, authors: 1}
)
```

- Запрос для редактирования полей `description` и `authors` коллекции `books` по `_id` записи:

```
db.books.updateOne(
	{ _id: 1 }
	{ $set: { authors: "Alex Young, Mike Cantelon", description: "Given the close interaction with command-line objects, the book contains sections that describe these two parameters: Node js and Electron technology. The book also teaches the creation and testing of web applications based on Express." } }
)
```
