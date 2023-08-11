# Module 25.2 - Full-Stack Holy Grail Application:

## Learning Outcomes Addressed:

4. Create a **Redis database**
5. Build a **full stack application** with a **Redis database**

## Instructions:

So far, **you’ve been able** to **create both** a **front end** for your **Holy Grail application** and an **API layer** using `Express`. Now, it’s **time to add** a **database** to complete the **full stack**.

Your **tasks** in this **activity** are to **set up** a **Redis database** using **Docker** and then **update** your **Express endpoints** to **connect** to the **Redis database**.

To **accomplish** this **task**, you need to do the **following**:

* **Set up** the **Redis Docker container** **locally**. 
* **Install** the **Redis npm package**.
* **Update** the `index.js` file to **include** the following:
  * `"header", 0, "left", 0, "article", 0, "right", 0, "footer", 0`
  * Create a **Redis client**. 
  * Use the **Redis client** to **initialize values** for `header`, `left`, `article`, `right`, and `footer`. These **values** should be

```text
"header", 0, "left", 0, "article", 0, "right", 0, "footer", 0
```

* Implement the `data()` **method** to use `Promises` to **get the values** for `header`, `left`, `right`, `article` and `footer` using the **Redis client**. 
* Implement the `/update/:key/:value` **endpoint** by using the **Redis client** to **update** a given **key-value pair**. You should first **locate the records** matching the **provided key** and then **update it** to the **new provided value**. 

The [starter code](/Starter_Code) includes an `index.js` file that **contains** some **helpful comments**.

Once done, **upload screenshots** showing the following:

* The running **Redis Docker container** 
* The **front end**, showing the **Holy Grail application**

You can also **submit a link** to the **GitHub repo** that **contains** your **solution’s source file**.