<!DOCTYPE html>
<html lang="en">
<head>
  <style>
    body {
  font-family: Arial, sans-serif;
  line-height: 1.6;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
  color: #333;
}

.header {
  background: #4caf50;
  color: white;
  text-align: center;
  padding: 1rem;
}

.features, .usage, .example {
  padding: 1.5rem;
  background: white;
  margin: 1rem auto;
  max-width: 800px;
  border-radius: 8px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.features h2, .usage h2, .example h2 {
  color: #4caf50;
}

ul {
  list-style: circle inside;
}

pre {
  background: #f7f7f7;
  padding: 1rem;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow-x: auto;
}

.footer {
  text-align: center;
  background: #333;
  color: white;
  padding: 1rem 0;
}

#backToTop {
  background: #4caf50;
  color: white;
  border: none;
  padding: 0.5rem 1rem;
  cursor: pointer;
  border-radius: 5px;
}

#backToTop:hover {
  background: #45a049;
}

  </style>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Circular Queue Introduction</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <header class="header">
    <h1>Welcome to Circular Queue Repository</h1>
    <p>An efficient data structure for managing elements in a circular fashion.</p>
  </header>

  <section class="features">
    <h2>Features</h2>
    <ul>
      <li>Efficient space utilization with circular storage.</li>
      <li>Supports operations: Enqueue, Dequeue, Peek, Check Full/Empty.</li>
      <li>Maximum size: <code>n-1</code> elements in an array of size <code>n</code>.</li>
    </ul>
  </section>

  <section class="usage">
    <h2>How It Works</h2>
    <p>The Circular Queue uses an array with two pointers: <code>front</code> and <code>rear</code>. The operations wrap around when the end of the array is reached.</p>
    <pre>
      Full Condition: (rear + 1) % n == front
      Empty Condition: rear == front
    </pre>
  </section>

  <section class="example">
    <h2>Code Example</h2>
    <pre>
class CircularQueue:
    def __init__(self, size):
        self.size = size
        self.queue = [None] * size
        self.front = self.rear = 0

    def enqueue(self, value):
        if not self.is_full():
            self.queue[self.rear] = value
            self.rear = (self.rear + 1) % self.size

    def dequeue(self):
        if not self.is_empty():
            value = self.queue[self.front]
            self.front = (self.front + 1) % self.size
            return value
    </pre>
  </section>

  <footer class="footer">
    <p>© 2024 Circular Queue Repository</p>
    <button id="backToTop">Back to Top</button>
  </footer>

  <script src="script.js"></script>
</body>
</html>
