

| No. | Language | 
| ----- |-----|
| 1 |  [JavaScript](#JavaScript)   | 
| 2 |  [ReactJS](#ReactJS)   | 
| 3 |  [NodeJS](#NodeJS)   | 
| 4 |  [NextJS](#NextJS)   | 
| 5 |  [TypeScript](#TypeScript)   | 
| 6 |  [MySQL](#MySQL)   | 
| 7 |  [NestJS](#NestJS)   |

## JavaScript
| No. | Question | Answer |
| --- |-----| ----------- |
| 1 | What is V8 Engine? | V8 is Google’s JavaScript engine that compiles JavaScript into machine code using JIT compilation, enabling fast execution in Chrome and Node.js. |
| 2 | Difference between  let, const and var |Hoisting in JavaScript is a behavior where variable and function declarations are moved to the top of their scope during the compilation phase before code execution.<br>Important<br>● Declaration is hoisted<br>● Initialization is NOT hoisted<br>Scope<br>&nbsp;&nbsp;&nbsp;&nbsp;● `var:-` Function-scoped<br>&nbsp;&nbsp;&nbsp;&nbsp;● `let:-` Block-scoped<br>&nbsp;&nbsp;&nbsp;&nbsp;● `const:-` Block-scoped<br>Redeclaration<br>&nbsp;&nbsp;&nbsp;&nbsp;● `var:-` ✅ Allowed <br>&nbsp;&nbsp;&nbsp;&nbsp;● `let:-` ❌ Not allowed<br>&nbsp;&nbsp;&nbsp;&nbsp;● `const:-` ❌ Not allowed<br>Reassignment<br>&nbsp;&nbsp;&nbsp;&nbsp;● `var:-` ✅ Allowed<br>&nbsp;&nbsp;&nbsp;&nbsp;● `let:-` ✅ Allowed <br>&nbsp;&nbsp;&nbsp;&nbsp;● `const:-` ❌ Not allowed<br>Hoisting<br>&nbsp;&nbsp;&nbsp;&nbsp;● `var:-` ✅ Yes (initialized as undefined)<br>&nbsp;&nbsp;&nbsp;&nbsp;● `let:-` ✅ Yes (but in TDZ)<br>&nbsp;&nbsp;&nbsp;&nbsp;● `const:-` ✅ Yes (but in TDZ)<br>Temporal Dead Zone (TDZ)<br>&nbsp;&nbsp;&nbsp;&nbsp;● `var:-` ❌ No<br>&nbsp;&nbsp;&nbsp;&nbsp;● `let:-` ✅ Yes<br>&nbsp;&nbsp;&nbsp;&nbsp;● `const:-` ✅ Yes |
| 3 | what is Temporal Dead Zone? | Temporal Dead Zone is the time between variable hoisting and initialization where accessing a let or const variable results in a ReferenceError.<br>Declared but not initialized = Dead Zone |
| 4 | What is Debounce? | Debouncing ensures that a function is executed only after a certain delay has passed since the last time it was triggered. |
| 5 | What is Throttling? | Throttling ensures that a function is executed at most once in a fixed time interval, no matter how many times the event occurs. |
| 6 | difference between async and defer | Loading <br>&nbsp;&nbsp;&nbsp;&nbsp;● `async:-` Script is downloaded asynchronously (in parallel)<br>&nbsp;&nbsp;&nbsp;&nbsp;● `defer:-` Script is also downloaded in parallel<br>Execution time<br>&nbsp;&nbsp;&nbsp;&nbsp;● `async:-` Executes immediately after download, even if HTML parsing is not finished<br>&nbsp;&nbsp;&nbsp;&nbsp;● `defer:-` Executes after HTML parsing is complete<br>Order of execution<br>&nbsp;&nbsp;&nbsp;&nbsp;● `async:-` Not guaranteed (scripts may run in any order)<br>&nbsp;&nbsp;&nbsp;&nbsp;● `defer:-` Maintains order (runs in sequence as written)<br>Blocking HTML parsing<br>&nbsp;&nbsp;&nbsp;&nbsp;● `async:-` Yes (execution pauses HTML parsing)<br>&nbsp;&nbsp;&nbsp;&nbsp;● `defer:-` No (waits until parsing finishes)<br>Best use case<br>&nbsp;&nbsp;&nbsp;&nbsp;● `async:-` Independent scripts (e.g., analytics, ads)<br>&nbsp;&nbsp;&nbsp;&nbsp;● `defer` Scripts that depend on DOM or need order <br><h4>Short Interview Answer (2–3 lines)</h4>● Async scripts load in parallel and execute as soon as they’re ready, without guaranteeing order.<br>● Defer scripts also load in parallel but execute only after the HTML is fully parsed, preserving order.<br>Example<br>&nbsp;&nbsp;&nbsp;&nbsp;<script async src="script1.js"></script><br>&nbsp;&nbsp;&nbsp;&nbsp;<script defer src="script2.js"></script> |


## ReactJS
| No. | Question | Answer |
| --- |-----| ----------- |
|  | Scenario | ````` ``` ````` |
| 1 | What is DOM? | DOM (Document Object Model) is a programming interface for HTML/XML documents.It represents the webpage as a tree structure of objects, where<br>each element `(like <div>, <p>)` is a node. <br>The DOM is a tree-like structure representing HTML elements.<>In React, a Virtual DOM is used, which is a lightweight copy of the real DOM. React updates the Virtual DOM first, compares changes, and efficiently updates only the required parts of the real DOM.|
|  | Difference between useEffect and useLayoutEffect | <h3>useEffect</h3>● Runs after the browser paints the screen<br>● Doesn’t block user seeing UI<br>● Ideal for:<br>● Fetching data<br>● Logging<br>● Setting timers<h3>useLayoutEffect</h3>● Runs after render but before painting<br>● Blocks painting until effect finishes<br>● Ideal for:<br>● Reading layout or size of DOM elements<br>● Synchronously updating DOM to avoid flicker |
| 2 | useMemo VS useCallback | <h3> useMemo</h3>● Use it to cache the result of a calculation.<br>● React only recalculates when dependencies change.<h3>useCallback</h3>● useCallback is a hook that memoizes a function so it doesn’t get recreated on every render, which helps prevent unnecessary child component re-renders.<br>●  Use it to cache a function.<br>● Prevents child components from re-rendering unnecessarily when the parent renders. |
| 3 | useMemo VS React.memo | <h3>useMemo</h3>● Memoizes the result of a computation.<br>● Only recomputes if dependencies change.<h3>React.memo</h3>● Memoizes a component, preventing it from re-rendering if props don’t change.<br>● Without React.memo: Child re-renders on every parent render.<br>● With React.memo: Child only re-renders if name prop changes.<h4>useMemo memoizes a value to avoid recalculation, while React.memo memoizes a component to prevent unnecessary re-renders when props haven’t changed.</h4> |
| 9 | What is an Interceptor? | An interceptor is a function that intercepts and modifies HTTP requests or responses before they are handled by the application.|
| 10 | How to prevent duplicate form submissions | 1. Client-Side Prevention<br>&nbsp;&nbsp;&nbsp;&nbsp;● Disable the submit button immediately after click<br>&nbsp;&nbsp;&nbsp;&nbsp;● Show loading spinner to indicate processing<br>&nbsp;&nbsp;&nbsp;&nbsp;● Debounce clicks so multiple clicks in short time are ignored <br>2. Server-Side Prevention<br>&nbsp;&nbsp;&nbsp;&nbsp;● Check for duplicate requests using a unique token (idempotency key)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Store token in DB/session and reject if reused<br>3. Use POST-Redirect-GET Pattern<br>&nbsp;&nbsp;&nbsp;&nbsp;● After form submission, redirect to a success page<br>&nbsp;&nbsp;&nbsp;&nbsp;● Prevents browser resending POST on refresh<br>4. Database-Level Constraints<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use unique constraints to prevent duplicate entries<br>&nbsp;&nbsp;&nbsp;&nbsp;●Example: UNIQUE(email) for newsletter signups<br>5. Idempotent APIs (for REST)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Assign idempotency keys to requests (e.g., payments)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Multiple identical requests will result in only one action |
| 11 | Difference Between Website and Web Application | A website is mainly a collection of web pages designed to provide information to users, whereas a web application is a software that runs in a browser and allows users to perform specific tasks and interact with data.<br><img width="912" height="315" alt="image" src="https://github.com/user-attachments/assets/3bd6c308-bd26-41cc-8805-4d5261d2c5e7" /> |
| 12 | How to Optimize React Application | To optimize a React application, I focus on minimizing unnecessary re-renders, reducing bundle size, and improving perceived performance using techniques like memoization, code splitting, and efficient state management. | 
| 13 | Explanation of debouncing vs throttling | ● Debounce → Execute after user stops triggering events<br>● Throttle → Execute at a fixed interval while events continue <img width="816" height="306" alt="image" src="https://github.com/user-attachments/assets/693ff7e9-2368-4152-98d3-6728624891c1" /> |
| 14 | Difference Between State and Props | ● State is used to manage dynamic data inside a component. It is mutable, meaning we can update it using setState or hooks like useState.<br>● Props are used to pass data from parent component to child component. Props are immutable, meaning child components cannot modify them. Extra Point (Important for Experienced Candidates) <h4>You can also add:</h4>● State changes can trigger component re-rendering.<br>● Props help make components reusable.<br>● Data flow in React is unidirectional (parent to child).|
| 15 | Difference Between useEffect and useMemo |<h3>useEffect:</h3>● It is used to handle side effects like API calls, subscriptions, timers, or DOM updates.<br>● It runs after the component renders.<br>● It does not return a value, but it can return a cleanup function.<h3>useMemo:</h3>● It is used to optimize performance by memoizing a computed value.<br>● It runs during render and returns a cached value unless dependencies change.<br>● It prevents expensive calculations on every render. |


| No. | Question | Answer |
| --- | -------- | ------ |
| 1   | Scenario | <pre><code>console.log("Line 1");console.log("Line 2");console.log("Line 3");</code></pre> |


## NodeJS
| No. | Question | Answer |
| --- |-----| ----------- |
| 1 | explanation of Cluster and Fork in Node.js | Fork is used to create a separate Node.js process for running tasks independently, while Cluster is used to create multiple worker processes that share the same server port to utilize multi-core systems and improve performance. |
| 2| explanation of Cluster and Fork in Node.js |1. Fork in Node.js<br>●It creates a new Node.js process.<br>● Each forked process has its own memory space (V8 instance).<br>● Communication between parent and child happens via IPC (Inter-Process Communication).<br>● Useful for running tasks in parallel.<br>● Example<br>const { fork } = require('child_process'); const child = fork('child.js'); child.send({ message: 'Hello from parent' }); child.on('message', (msg) => { console.log('Message from child:', msg); });<br>2. Cluster in Node.js<br>● Uses multiple processes to take advantage of multi-core CPUs.● One master (primary) process manages multiple workers.● All workers share the same port (load-balanced by Node.js).● Improves scalability and performance of web servers.<br>● Example<br>const cluster = require('cluster');const http = require('http');const os = require('os');if (cluster.isPrimary) {const numCPUs = os.cpus().length;for(let i = 0; i < numCPUs; i++) {cluster.fork();}} else {http.createServer((req, res) => {res.end('Handled by worker ' + process.pid);}).listen(3000);};<br>`● Fork = Create a new process to run tasks independently.`<br>`● Cluster = Use multiple forked processes to handle incoming requests efficiently across CPU cores.`|
| 3 | What is Emitter in NodeJS? | An emitter is an object or component that generates and dispatches events or messages, which other parts of the system can subscribe to and react to. <br>● emitter.emit() → sends the event <br>● emitter.on() → listens for it|
| 4 | what is idempotency in node js ? |Idempotency means that making the same API request multiple times results in the same outcome as making it once, which helps prevent duplicate operations and ensures safe retries in Node.js applications.|
| 5 |Difference Between Authorization and Authentication | Authentication = Who are you?<br>Authorization = What are you allowed to do?<br>Authentication verifies who the user is, while authorization determines what the user is allowed to access or perform after they are authenticated. |
| 6 | what is event-loop in node js | The Event Loop is a mechanism in JavaScript that handles asynchronous operations by managing the execution of the call stack and callback queue.<br>Microtasks (Promises) are executed before macrotasks (setTimeout) in the event loop. |
| 7 | what is cors | CORS (Cross-Origin Resource Sharing) is a security mechanism in browsers that allows or restricts requests from one origin to another. |
| 8  | What is Middleware | Middleware is a function in Node.js/Express that has access to the request (req), response (res), and next function (next) and can execute code, modify requests/responses, or end the request-response cycle. <br>Middleware is a function that executes during the request-response cycle in Node.js/Express, capable of modifying requests/responses, performing tasks, or ending the cycle. Types include application-level, router-level, built-in, third-party, and error-handling middleware.|
| 9 | Difference Between Middleware and interceptor |  Middleware is a server-side function that handles requests and responses during the Node.js request-response cycle, while an interceptor is a function that intercepts HTTP requests or responses to modify or handle them before they reach the application or client. |
| 10 | What is Guard? | A guard is a mechanism that decides whether a user can access a particular route or resource, typically based on authentication or authorization.<br>● A guard is something that protects, controls access, or prevents unwanted actions. |
| 11 | What is Horizontal vs Vertical Scaling | 1. Vertical Scaling (Scaling Up)<br>Vertical scaling means increasing the power of a single machine.<br>👉 You upgrade:<br>&nbsp;&nbsp;● CPU<br>&nbsp;&nbsp;● RAM<br>&nbsp;&nbsp;● Storage<br>2. Horizontal Scaling (Scaling Out)<br>● Horizontal scaling means adding more machines/servers to handle the load.<br>👉 You distribute traffic across multiple servers.<br>Example:<br>&nbsp;&nbsp;●Adding more servers behind a load balancer |
| 12 | What is Connection Pooling?| Connection pooling is a technique where a pool (group) of pre-created database connections is maintained and reused, instead of creating a new connection every time a request is made.<br>Benefits<br>&nbsp;&nbsp;● Improves performance 🚀<br>&nbsp;&nbsp;● Reduces latency<br>&nbsp;&nbsp;● Saves resources<br>&nbsp;&nbsp;● Handles multiple requests efficiently |
| 13 | What is Rate limiting? | Rate limiting is a technique used to control the number of requests a user or client can make to a server in a given time period.<br> It prevents:<br>&nbsp;&nbsp;●Overloading the server<br>&nbsp;&nbsp;●Abuse of APIs<br>&nbsp;&nbsp;●Denial-of-Service (DoS) attacks |
| 14 | What is a Message Queue? | A message queue is a system where producers send messages to a queue, and consumers read from it asynchronously. It enables decoupling, reliability, and scalability between application components. | 
| 15 | Difference Between POST, PUT, and PATCH  | POST is used to create new resources, PUT is used to completely replace an existing resource, and PATCH is used to partially update a resource. PUT is idempotent, POST is not, and PATCH is usually idempotent. |
| 16 | What is a Race Condition? How to Avoid .| A race condition occurs when two or more threads or processes access shared data at the same time, and the final outcome depends on the order of execution.<br>Example:<br>&nbsp;&nbsp;● Two users try to withdraw $100 from a bank account with $150 at the same time:<br>&nbsp;&nbsp;● Both read balance = $150<br>&nbsp;&nbsp;● Both deduct $100<br>● Final balance = $-50 (incorrect!)<br><h3>Avoid Race Condition</h3>1. Use Locks / Mutexes<br>&nbsp;&nbsp;&nbsp;&nbsp;● Ensure only one thread can access the critical section at a time.<br>2. Use Atomic Operations<br>&nbsp;&nbsp;&nbsp;&nbsp;● Perform read-modify-write as a single atomic step<br>&nbsp;&nbsp;&nbsp;&nbsp;● Many databases and languages provide atomic increment/decrement<br>3. Transactions in Databases<br>&nbsp;&nbsp;&nbsp;&nbsp;● Wrap operations in transactions<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use ACID properties to ensure consistency<br>4. Optimistic Locking<br>&nbsp;&nbsp;&nbsp;&nbsp;● Check if the data has changed before updating<br>&nbsp;&nbsp;&nbsp;&nbsp;● Often uses version numbers or timestamps<br>5. Avoid Shared State (if possible)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use immutable objects or message queues to decouple processes |
| 17 | How to Optimize API Latency? | 1. Database Optimization<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use indexes on frequently queried fields<br>&nbsp;&nbsp;&nbsp;&nbsp;● Optimize slow queries using EXPLAIN or query profiling<br>&nbsp;&nbsp;&nbsp;&nbsp;● Avoid N+1 queries (use joins or eager loading)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Cache frequent query results (Redis, Memcached)<br>2. Caching<br>&nbsp;&nbsp;&nbsp;&nbsp;● Response caching: Store API responses temporarily<br>&nbsp;&nbsp;&nbsp;&nbsp;● CDN caching: For static or semi-static data (images, JSON)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Cache headers: Use ETag, Cache-Control<br>3. Reduce Payload Size<br>&nbsp;&nbsp;&nbsp;&nbsp;● Return only required fields (avoid SELECT *)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use JSON compression (Gzip, Brotli)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Paginate large responses (limit, offset)<br>4. Asynchronous Processing<br>&nbsp;&nbsp;&nbsp;&nbsp;● Move heavy tasks to background jobs / message queues<br>&nbsp;&nbsp;&nbsp;&nbsp;● Respond quickly with status accepted, process later<br>Example: Sending email or generating reports asynchronously<br>5. Use Connection Pooling<br>&nbsp;&nbsp;&nbsp;&nbsp;● Maintain reusable DB connections to avoid overhead of opening/closing connections<br>&nbsp;&nbsp;&nbsp;&nbsp;● Reduces request-response time<br>6. Optimize Network<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use HTTP/2 for multiplexing<br>&nbsp;&nbsp;&nbsp;&nbsp;● Reduce round-trips (batch requests, minimize redirects)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Keep API server close to DB or use regional deployment<br>7. Load Balancing & Horizontal Scaling<br>&nbsp;&nbsp;&nbsp;&nbsp;● Distribute requests across multiple servers<br>&nbsp;&nbsp;&nbsp;&nbsp;● Auto-scale during peak load<br>8. Profile & Monitor<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use APM tools (New Relic, Datadog) to find bottlenecks<br>&nbsp;&nbsp;&nbsp;&nbsp;● Log latency per endpoint and optimize hotspots|
| 18 | What is a Background Job? and how to handle it | A background job is a task that runs outside the main request-response flow of an application.<br>1. Use a Message Queue / Job Queue<br>&nbsp;&nbsp;&nbsp;&nbsp;● Tasks are sent to a queue<br>&nbsp;&nbsp;&nbsp;&nbsp;● A worker process consumes tasks and executes them asynchronously<br>2. Use Cron Jobs / Scheduled Jobs<br>&nbsp;&nbsp;&nbsp;&nbsp;● For periodic tasks like cleanup, reports, or notifications<br>Example: 0 0 * * * runs daily at midnight<br>3. Threading / Async Workers<br>&nbsp;&nbsp;&nbsp;&nbsp;● Run tasks on separate threads or processes if supported<br>Example: Node.js worker threads<br>4. Ensure Reliability<br>&nbsp;&nbsp;&nbsp;&nbsp;● Retry failed jobs<br>&nbsp;&nbsp;&nbsp;&nbsp;● Log errors<br>&nbsp;&nbsp;&nbsp;&nbsp;● Persist jobs in database or message broker to prevent data loss|
| 19 |How to Secure APIs | 1. Authentication<br>&nbsp;&nbsp;&nbsp;&nbsp;● Verify the identity of the client<br>&nbsp;&nbsp;&nbsp;&nbsp;Common methods:<br>&nbsp;&nbsp;&nbsp;&nbsp;● API Keys – simple, but not very secure<br>&nbsp;&nbsp;&nbsp;&nbsp;● OAuth 2.0 / JWT – secure token-based authentication<br>&nbsp;&nbsp;&nbsp;&nbsp;● Basic Auth / Digest Auth – for internal or simple APIs<br>2. Authorization<br>&nbsp;&nbsp;&nbsp;&nbsp;● Control what an authenticated user can do <br>&nbsp;&nbsp;&nbsp;&nbsp;● Role-based access control (RBAC) or attribute-based access control (ABAC)<br>3. Input Validation<br>&nbsp;&nbsp;&nbsp;&nbsp;● Always validate incoming data<br>&nbsp;&nbsp;&nbsp;&nbsp;● Prevent SQL injection, XSS, and command injection<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use schema validation libraries like Joi (Node.js)<br>4. Rate Limiting & Throttling<br>&nbsp;&nbsp;&nbsp;&nbsp;● Limit the number of requests per client/IP<br>&nbsp;&nbsp;&nbsp;&nbsp;● Protects against DoS attacks<br>&nbsp;&nbsp;&nbsp;&nbsp;● Tools: Nginx, API Gateway, Redis-based rate limiter<br>5. Use HTTPS<br>&nbsp;&nbsp;&nbsp;&nbsp;● Encrypt traffic using TLS/SSL<br>&nbsp;&nbsp;&nbsp;&nbsp;● Prevents man-in-the-middle attacks and data sniffing<br>6. API Gateway / Reverse Proxy<br>&nbsp;&nbsp;&nbsp;&nbsp;● Acts as a security layer<br>&nbsp;&nbsp;&nbsp;&nbsp;Can enforce:<br>&nbsp;&nbsp;&nbsp;&nbsp;● Authentication<br>&nbsp;&nbsp;&nbsp;&nbsp;● Rate limiting<br>&nbsp;&nbsp;&nbsp;&nbsp;● Logging & monitoring<br>&nbsp;&nbsp;&nbsp;&nbsp;Examples: Kong, AWS API Gateway, Nginx<br>7. Data Encryption<br>&nbsp;&nbsp;&nbsp;&nbsp;● Encrypt sensitive data at rest and in transit<br>&nbsp;&nbsp;&nbsp;&nbsp;Examples: AES for storage, TLS for transport<br>8. Prevent Common Attacks<br>&nbsp;&nbsp;&nbsp;&nbsp;● SQL Injection: Use prepared statements or ORM<br>&nbsp;&nbsp;&nbsp;&nbsp;● Cross-Site Scripting (XSS): Sanitize output<br>&nbsp;&nbsp;&nbsp;&nbsp;● Cross-Site Request Forgery (CSRF): Use tokens for state-changing requests<br>9. Logging and Monitoring<br>&nbsp;&nbsp;&nbsp;&nbsp;● Track failed authentication attempts<br>&nbsp;&nbsp;&nbsp;&nbsp;● Log suspicious activity<br>&nbsp;&nbsp;&nbsp;&nbsp;● Set alerts for unusual request patterns<br>10. Versioning & Deprecation<br>&nbsp;&nbsp;&nbsp;&nbsp;● Keep older API versions secure<br>&nbsp;&nbsp;&nbsp;&nbsp;● Deprecate insecure endpoints|
| 20 | Difference between npm vs npx | ● npm → Installs & manages packages<br>● npx → Executes packages without installing<img width="881" height="376" alt="image" src="https://github.com/user-attachments/assets/30e61a2a-6ed7-4e91-948f-00acd8d691c8" /><br>● npm is used to install and manage dependencies, whereas npx is used to execute packages without installing them globally.<br>● npm → Installing an app on your phone 📲<br>● npx → Using a web app without installing 🌐|
| 21 | Difference Between Promise vs Async/Await |  Async/await is built on top of Promises and provides a cleaner, more readable way to handle asynchronous operations without chaining .then() calls.<br><img width="829" height="419" alt="image" src="https://github.com/user-attachments/assets/43673587-614b-4e6a-a26c-edfae5cb8f9b" /> <br>● Promise → Handles async operations using .then() and .catch()<br>● async/await → Cleaner syntax to write Promise-based code like synchronous code|
| 22 | types of Promises in JavaScript | 1. Promise.all() <br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● Runs multiple promises in parallel<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● ✅ Returns when all succeed<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● ❌ Fails if any one fails<br>2. Promise.allSettled()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● Waits for all promises<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● Doesn’t fail if one fails<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● Returns status of each<br>3. Promise.race()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● Returns the first completed promise<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;● Could be success OR failure<br>4. Promise.any()<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;●Returns the first successful promise<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;●Ignores failures unless all fail |
| 23 | Difference Between Monolithic and Microservices Architecture | ● Monolith → Entire application built as one single codebase & deployed together<br>● Microservices → Application is split into multiple small independent services<br><img width="883" height="489" alt="image" src="https://github.com/user-attachments/assets/feaaea50-58dc-4abb-a210-7f8e0730b995" />| 
| 24 | Explain JWT (JSON Web Token), its payload and Algorithm | A JWT is a compact, self-contained token used for authentication and authorization between client and server.<h3>JWT Architecture</h3>A JWT has 3 parts separated by dots (.) <br><code>HEADER.PAYLOAD.SIGNATURE</code> <br>1️⃣ Header Contains metadata about token <br>```{"alg": "HS256",```<br>&nbsp;&nbsp;&nbsp;&nbsp;```"typ": "JWT"}```<br>● Type of token (JWT)<br>● Algorithm used for signing<br>2️⃣ Payload (🔥 MOST IMPORTANT PART)<br>📌 Types of Claims in Payload <br>1. Registered Claims (standard)<br>&nbsp;&nbsp;&nbsp;&nbsp;● iss → issuer<br>&nbsp;&nbsp;&nbsp;&nbsp;● sub → subject (user ID)<br>&nbsp;&nbsp;&nbsp;&nbsp;● aud → audience<br>&nbsp;&nbsp;&nbsp;&nbsp;● exp → expiration<br>&nbsp;&nbsp;&nbsp;&nbsp;● iat → issued at<br>2. Public Claims<br>&nbsp;&nbsp;&nbsp;&nbsp;● Custom but standardized names (shared use)<br>3. Private Claims<br>&nbsp;&nbsp;&nbsp;&nbsp;● App-specific data (like role, permissions)<br>3️⃣ Signature (Security Layer 🔐)<br>Used to verify token integrity<br><h3>JWT Algorithm (VERY IMPORTANT)</h3>🔹 1. Symmetric Algorithms (HS256)<br>👉 HS256 (HMAC + SHA-256)<br>Same secret key used for:<br>&nbsp;&nbsp;&nbsp;&nbsp;● Signing<br>&nbsp;&nbsp;&nbsp;&nbsp;● Verification<br>🔹 2. Asymmetric Algorithms (RS256 / ES256)<br>👉 RS256 (RSA + SHA-256)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Uses public/private key pair <br><img width="653" height="156" alt="image" src="https://github.com/user-attachments/assets/09185bb7-a279-49a9-8487-50213b8344b0" /><br>🔹 3. ES256 (ECDSA)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Uses elliptic curve cryptography<br>&nbsp;&nbsp;&nbsp;&nbsp;● Faster + smaller keys than RSA|
|  | How do you handle error logs in production in microservices? |  |




## Level 5: NextJS
| No. | Question | Answer |
| --- |-----| ----------- |
| 1 | What is App Layout and Page Layout? | In Next.js, page layout means we manually wrap each page with a layout component in the pages folder, while app layout means we define a layout file in the app folder that automatically wraps all pages. |
| 2 | What is DTOs | A DTO (Data Transfer Object) is a simple object used to transfer data between layers of an application without containing business logic. It improves security, performance, and decouples application layers. |
| 3 | Difference Between Client-Side and Server-Side | Client-side handles what users see and interact with, while server-side handles data processing and business logic.<br><img width="930" height="381" alt="image" src="https://github.com/user-attachments/assets/add06ca6-fd96-42c6-8918-e3ed97dbe723" />|



## TypeScript
| No. | Question | Answer |
| --- |-----| ----------- |
| 01 | What is Interface? | An interface is a set of rules that a class must follow.<br>● An interface is a blueprint that defines a set of methods without implementing them. Any class that implements the interface must provide definitions for those methods. |


## MySQL
| No. | Question | Answer |
| --- | -------- | ------ |
| 1 | What are types of indexing in MySQL | <span style="font-weight:600;">1. Primary Index (Primary Key)</span><br>- Automatically created when you define a PRIMARY KEY.<br><br><span style="font-weight:600;">2. Unique Index</span><br>- Ensures all values in the indexed column are unique.<br>- Allows NULL values (depending on configuration, multiple NULLs may be allowed).<br><br><span style="font-weight:600;">3. Normal Index (Secondary Index)</span><br>- Improves search performance but does not enforce uniqueness.<br>- Can be created on one or multiple columns.<br><br><span style="font-weight:600;">4. Composite Index (Multi-column Index)</span><br>- Useful for queries that filter on more than one column.<br>- Order of columns matters (leftmost prefix rule).<br><br><span style="font-weight:600;">5. Full-Text Index</span><br>- Used for text searching (especially large text fields like TEXT or VARCHAR).<br><br><span style="font-weight:600;">6. Spatial Index</span><br>- Used for geometric/spatial data types.<br>- Helps in location-based queries (e.g., coordinates).<br><br><span style="font-weight:600;">7. Clustered Index</span><br>- In MySQL (InnoDB), the primary key is the clustered index.<br>- Only one clustered index per table.<br><br><span style="font-weight:600;">8. Non-Clustered Index</span><br>- Stores a separate structure from the actual table data.<br>- Points to the location of data rows.<br>- You can have multiple non-clustered indexes. |
| 2 | In Mysql how many Joins are there?|<h2>There are 5 types of Join </h2><h3>1. INNER JOIN</h3>●Returns only matching rows from both tables.<h3>2. LEFT JOIN (LEFT OUTER JOIN)</h3>● All rows from left table<br>● Matching rows from right table<br>● Non-matching → NULL<h3>3. RIGHT JOIN (RIGHT OUTER JOIN)</h3>● All rows from right table<br>● Matching from left<br>● Non-matching → NULL<h3>4. FULL JOIN (FULL OUTER JOIN)</h3>● Returns all rows from both tables:<br>●Matching + non-matching from both sides<h4>❗ In MySQL:</h4>● Not directly supported<br>● You simulate it using UNION <h3> 5. CROSS JOIN</h3>●Returns Cartesian product<br>● Every row of A × every row of B <br>Example:- ●Table A has 3 rows <br>● Table B has 2 rows<br>● Result = 3 × 2 = 6 rows <h3>Bonus (sometimes asked)<br>SELF JOIN</h3>● A table joins with itself|
| 3 | What is Indexing | Indexing is a database optimization technique that improves query performance by allowing faster data retrieval using a separate lookup structure.| 
| 4 | what is Normalization? | Normalization is the process of structuring a database to eliminate redundancy and ensure data consistency by dividing data into related tables.<br>● Normalization is a process used in database management to organize data in a table efficiently. It helps to reduce data redundancy (duplicate data) and improve data integrity (accuracy and consistency).<br>[Type Of Normalization](#database-normalization)|
| 5 | What is ORM | ORM (Object-Relational Mapping) is a technique that lets us interact with a database using objects instead of SQL queries. It’s commonly used in languages like Java, Python, and JavaScript through tools like Hibernate, Django ORM, and Sequelize.<br>● It maps database tables → classes and rows → objects, so you can work with data as objects in your code. | 
| 6 | How to Prevent SQL Injection? | 1:- Use Prepared Statements (Parameterized Queries) ✅ (Most Important)<br>2:- Use ORM (Object Relational Mapping)<br>3:- Input Validation & Sanitization<br>&nbsp;&nbsp;&nbsp;&nbsp;● Allow only expected formats (e.g., email, numbers)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Reject suspicious characters<br>4:- Escape User Inputs<br>5:- Use Stored Procedures<br>&nbsp;&nbsp;&nbsp;&nbsp;● If prepared statements are not used, escape special characters.<br>6:- Apply Least Privilege Principle<br>&nbsp;&nbsp;&nbsp;&nbsp;● Give database users only required permissions<br>&nbsp;&nbsp;&nbsp;&nbsp;● Avoid using admin/root access in applications<br>7:- Use Web Application Firewalls (WAF) <br>&nbsp;&nbsp;&nbsp;&nbsp;● Helps detect and block SQL injection attacks|
| 7 | What is N + 1 Problem? | The N + 1 problem occurs when one query fetches N records and then N additional queries are executed to fetch related data, causing performance issues. It can be solved using joins or eager loading. |
| 8 | What is Eventual Consistency? | Eventual consistency is a model where updates to data are propagated across all nodes asynchronously, so all replicas will eventually be consistent. It favors availability and scalability over immediate consistency.<br>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; And <br>Eventual consistency is a consistency model used in distributed systems where:<br>● All replicas of data will eventually become consistent, but not necessarily immediately.<br>● Updates may propagate asynchronously across nodes<br>● Reads may temporarily return stale or old data |
| 9 | How to Optimize a Slow Query | 1. Analyze the Query<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use EXPLAIN (MySQL, PostgreSQL) or EXPLAIN PLAN (Oracle)<br>&nbsp;&nbsp;&nbsp;&nbsp;● Check how the database executes the query<br>&nbsp;&nbsp;&nbsp;&nbsp;● Look for full table scans, large joins, or missing indexes<br>3. Avoid SELECT <br>&nbsp;&nbsp;&nbsp;&nbsp;● Only select the columns you need<br>4. Optimize Joins<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use INNER JOIN instead of CROSS JOIN when possible<br>&nbsp;&nbsp;&nbsp;&nbsp;● Ensure joined columns are indexed<br>&nbsp;&nbsp;&nbsp;&nbsp;● Avoid joining unnecessary tables<br>5. Use LIMIT and Pagination<br>&nbsp;&nbsp;&nbsp;&nbsp;● For large datasets, fetch only what you need at a time<br>6. Cache Frequent Queries<br>&nbsp;&nbsp;&nbsp;&nbsp;● Use Redis, Memcached, or application-level caching<br>&nbsp;&nbsp;&nbsp;&nbsp;● Avoid repeated database hits for the same data<br>7. Optimize Subqueries<br>&nbsp;&nbsp;&nbsp;&nbsp;● Replace subqueries with JOINs if possible<br>&nbsp;&nbsp;&nbsp;&nbsp;● Or use CTE (Common Table Expressions) for readability and performance<br>8. Partitioning and Sharding<br>&nbsp;&nbsp;&nbsp;&nbsp;● Split large tables using horizontal partitioning or sharding<br>&nbsp;&nbsp;&nbsp;&nbsp;● Helps for very large datasets<br>9. Denormalization (if necessary)<br>&nbsp;&nbsp;&nbsp;&nbsp;● For read-heavy systems, duplicate some data to avoid complex joins<br>&nbsp;&nbsp;&nbsp;&nbsp;● Trade-off: more storage, simpler queries<br>10. Monitor and Tune Database Settings<br>&nbsp;&nbsp;&nbsp;&nbsp;● Check query cache, buffer pool size, and other DB configs<br>&nbsp;&nbsp;&nbsp;&nbsp;● For PostgreSQL: work_mem, shared_buffers<br>&nbsp;&nbsp;&nbsp;&nbsp;● For MySQL: innodb_buffer_pool_size, query_cache_size |
| 10 | What is Data Sharding | Data sharding is the process of splitting a large database into smaller, independent pieces called shards, each on a separate server. It improves performance, scalability, and availability but adds complexity in querying and maintaining data.<br>Benefits of Sharding<br>1:- Improved Performance: Smaller datasets per shard → faster queries<br>2:- Better Scalability: Add more shards as data grows<br>3:- High Availability: One shard failing doesn’t affect others<br>4:- Reduced Load: Distributes writes and reads across servers |



## NestJS 

| No. | Question | Answer |
| --- | -------- | ------ |
| 01 | What is Decorator? | A decorator is a function that adds extra functionality to another function without changing its original code.<br>● Decorators in NestJS are used to define routes, inject dependencies, and configure classes. They make the code clean and easy to understand.<br>● Decorators in NestJS are used to add metadata and define behavior like routing, dependency injection, and request handling.<br>💻 Common Examples<br>● @Controller() → defines a controller<br>● @Get() → handles GET requests<br>● @Post() → handles POST requests<br>● @Injectable() → marks a service for dependency injection|
| 02 | How they are communicating each other internally in your app |  | 
| 03 | Explain Modules, Controllers and Providers |Client → Controller → Provider → Response<br><br>🧱 1. Modules in NestJS<br>A Module is the organizational unit of a NestJS application. It groups related components (controllers, providers, etc.) together.<br>Key Points:<br>&nbsp;&nbsp;&nbsp;&nbsp;● Defined using @Module() decorator<br>&nbsp;&nbsp;&nbsp;&nbsp;● Acts as a container for application structure<br>&nbsp;&nbsp;&nbsp;&nbsp;● Helps in scalability and separation of concerns<br>🎮 2. Controllers<br>A Controller handles incoming HTTP requests and returns responses to the client.<br>Key Points:<br>&nbsp;&nbsp;&nbsp;&nbsp;● Defined using @Controller() decorator<br>&nbsp;&nbsp;&nbsp;&nbsp;● Responsible for routing<br>&nbsp;&nbsp;&nbsp;&nbsp;● Calls providers (services) to process data<br>⚙️ 3. Providers (Services)<br>A Provider is a class that contains business logic and can be injected into other classes.<br>Key Points:<br>&nbsp;&nbsp;&nbsp;&nbsp;● Defined using @Injectable()<br>&nbsp;&nbsp;&nbsp;&nbsp;● Handles logic, database calls, computations<br>&nbsp;&nbsp;&nbsp;&nbsp;● Uses Dependency Injection (DI)<br><img width="891" height="360" alt="image" src="https://github.com/user-attachments/assets/272b554d-376b-4066-8b9c-30c353b61c78" />
 | 


## Question 

| No. | Question | Answer |
| --- | -------- | ------ |
| 1 | 1 <br>1 1 <br>1 1 2 <br>1 1 2 3 <br>1 1 2 3 5 | let rows = 5;<br>let fib = [1, 1];<br>for (let i = 2; i < rows; i++) {<br>fib[i] = fib[i - 1] + fib[i - 2];<br>}<br>for (let i = 0; i < rows; i++) {<br>let line = "";<br>for (let j = 0; j <= i; j++) {<br>line += fib[j] + " ";<br>}<br>console.log(line.trim());<br>} |



## Database Normalization

## ✅ First Normal Form (1NF)
**Rule:** Each column must contain atomic (indivisible) values.

### ❌ Before
| Student | Phone Numbers |
|--------|--------------|
| A      | 123, 456     |
| B      | 789          |

### ✅ After
| Student | Phone Number |
|--------|-------------|
| A      | 123         |
| A      | 456         |
| B      | 789         |

---

## ✅ Second Normal Form (2NF)
**Rule:** Must be in 1NF and remove **partial dependency**.

### ❌ Before
| StudentID | CourseID | StudentName |
|----------|----------|------------|
| 1        | C1       | Rahul      |
| 2        | C2       | Aman       |

### ✅ After

**Students Table**
| StudentID | StudentName |
|----------|------------|
| 1        | Rahul      |
| 2        | Aman       |

**Courses Table**
| StudentID | CourseID |
|----------|----------|
| 1        | C1       |
| 2        | C2       |

---

## ✅ Third Normal Form (3NF)
**Rule:** Must be in 2NF and remove **transitive dependency**.

### ❌ Before
| StudentID | DeptID | DeptName |
|----------|--------|----------|
| 1        | D1     | IT       |

### ✅ After

**Student Table**
| StudentID | DeptID |
|----------|--------|
| 1        | D1     |

**Department Table**
| DeptID | DeptName |
|--------|----------|
| D1     | IT       |

---

## ✅ Boyce-Codd Normal Form (BCNF)
**Rule:** Every determinant must be a candidate key.

### ❌ Before
| Teacher | Subject | Room |
|--------|--------|------|
| A      | Math   | 101  |
| B      | Math   | 101  |

### ✅ After

**Subject Table**
| Subject | Room |
|--------|------|
| Math   | 101  |

**Teacher Table**
| Teacher | Subject |
|--------|--------|
| A      | Math   |
| B      | Math   |

---

## ✅ Fourth Normal Form (4NF)
**Rule:** Remove **multi-valued dependencies**.

### ❌ Before
| Student | Hobby | Language |
|--------|-------|----------|
| A      | Music | English  |
| A      | Music | Hindi    |
| A      | Dance | English  |

### ✅ After

**Student-Hobby**
| Student | Hobby |
|--------|-------|
| A      | Music |
| A      | Dance |

**Student-Language**
| Student | Language |
|--------|----------|
| A      | English  |
| A      | Hindi    |

---

## ✅ Fifth Normal Form (5NF)
**Rule:** Remove **join dependency**.

### Example Decomposition:
- Supplier–Product  
- Product–Project  
- Supplier–Project  

---

## 🔑 Summary

| Normal Form | Concept |
|------------|--------|
| 1NF | Remove repeating groups |
| 2NF | Remove partial dependency |
| 3NF | Remove transitive dependency |
| BCNF | Every determinant is a candidate key |
| 4NF | Remove multi-valued dependency |
| 5NF | Remove join dependency |

---

## ✨ Tip
Use normalization to:
- Reduce data redundancy  
- Improve data integrity  
- Make databases easier to maintain  


