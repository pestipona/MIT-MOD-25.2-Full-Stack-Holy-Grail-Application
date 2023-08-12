# Module 25.2 - Full-Stack Holy Grail Application:

![Screen-Shot-1](https://github.com/pestipona/MIT-MOD-25.2-Full-Stack-Holy-Grail-Application/blob/main/Screen_Shots/Screen_Shots_01.png)

## Project Description:

This project demonstrates a **full-stack application** that **synchronizes communication** between the **client**, **server**, and the **data store**. This brings together all the different components that make up a **full-stack application**. It also demonstrates the **synchronization** of **data** on the the different **routes** between the **backend server** and the `Redis` **data store**. The same thing is also done on the **front-end** side, the **synchronization code** that will be calling the **backend server** and synchronizing the updates on the **UI** on the **front-end**.

This **project** is called **Holy Grail** because it makes use of the **design concept** called the [Holy Grail of web design](https://en.wikipedia.org/wiki/Holy_grail_(web_design)) for its **front-end UI**. The **front end** will have a `header`, a `footer`, a `main article`, and `panes` on the **right** and **left** sides. There's a **great deal** of **design decisions** that go into **creating an application**. And the **holy grail web design** makes it easier to design the **front-end UI**.

### Technical Stack:

* **Frontend:** The frontend `index.js` is developed using modern web technologies like `React.js`. We also added **one more package** which would be `Superagent`. And this is **used to handle** the **low-level communication** of **HTTP** between the **front end** and the **HTTP server**.


* **Backend:** The backend is an **http server** which we will be using a `Node.js` runtime and on top of that, a **package** called `Express`, which facilitates our **creation of routes** in our **API** that we will make **public**. Now, in addition to that, we also have a **small package** for `Redis`. And that is because we have selected `Redis` to be the **back-end database**.


* **Database:** We will be using `Redis` on top of a `Docker runtime`. So, we will run `Node` on our own machine, but we will run `Redis` on top of `Docker`.

## Installation:

Click on the https url of the project repository and depending on which IDE you are using paste the URL in your git clone command in your terminal and within your project directory.

```shell
git clone <github url>
```

After successfully cloning the repository. Make sure you first have `Node.js` installed.

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew install node
node -v
npm -v
```

Then run the package.json file by running npm install to install all dependencies.

```shell
npm install
```

## Usage:

### Setting up your Local Database:

Set up [Redis](https://redis.io/) as a **database** and run it **on top** of a **Docker container**. Install [Redis](https://hub.docker.com/_/redis) using `npm` and create **read/write functionality** for the **database** in `node`.

But first make sure that your **Docker daemon** is **up and running** by starting your **Docker Hub application**.

**Note:**

The **latest version** of **redis** is **no longer compatible** with the **example** so an **older version** will need to be **downloaded** to follow along.

```shell
docker run -p 6379:6379 –-name some-redis -d redis:4.0.1
```

### Opening the Application:

In your IDE open up a terminal and navigate to the project directory and enter nodemon `index.js`

```shell
nodemon index.js
```

The application will **now start listening** on `port 3000`, open up a **web browser** and go to the default path http://localhost:3000/. It will display the **Holy Grail Application**.

![Screen_Shots_02.png](Screen_Shots%2FScreen_Shots_02.png)

If you click on the `plus` or `minus` buttons on **each section** of the **Holy Grail Application** you would see the **values update** in all of the **sections**.

![Screen_Shots_04.png](Screen_Shots%2FScreen_Shots_04.png)

### Accessing Routes:

There are two main **routes** or **endpoints** in this **application**. The **first one** is `/data` and the second is `/update`. As the names suggest the **first one** is for **getting data** while the **second route** is for **updating data**.

To access the **first route** type in http://localhost/data in the address of your **web browser**. This shows the values on each section of the UI.

![Screen_Shots_05.png](Screen_Shots%2FScreen_Shots_05.png)

To **update the values** in the **database** the **second route** can be used. Open up a n**ew tab** in the **browser** and type in http://localhost:3000/update/Header/100 the path after http://localhost:3000/update/ is the `key` and the `value`, in this case `Header` is the **key** and `100` is the **value**. This follows the **format** of the **path** in the `index.js` file which is `"/update/:key/:value"`.

![Screen_Shots_06.png](Screen_Shots%2FScreen_Shots_06.png)

### Synchronization Calls to the Database:

As you can see in the following console log output, calls to the database from the front-end to the back-end server, and then finally to the database are printed out in the console.

![Screen_Shots_07.png](Screen_Shots%2FScreen_Shots_07.png)

When done don't forget to stop your docker container in the terminal.

```shell
docker ps

docker stop <container ID>
```

## Future Improvements:

**Modifying** the **front-end UI** to display more **interactive sections** other than `plus` or `minus` **buttons**.

## License:

MIT License

Copyright (c) 2023 Paul Estipona

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
