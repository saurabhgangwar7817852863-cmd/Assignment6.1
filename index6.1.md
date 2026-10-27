File 1: index.htmlHTML<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Assignment 6.1 - Box Model Inspection</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

  <header class="header">
    <h1>CSS Box Model Inspection</h1>
    <p>Exploring padding, borders, margins, and <code>box-sizing</code> behavior.</p>
  </header>

  <main class="container">

    <!-- Box 1: content-box -->
    <div class="box box-content-box">
      <h2>Box 1: Content-Box</h2>
      <p>This box uses <code>box-sizing: content-box</code>. Padding and borders are added <em>outside</em> the specified width, making the total element wider than set.</p>
    </div>

    <!-- Box 2: border-box -->
    <div class="box box-border-box">
      <h2>Box 2: Border-Box</h2>
      <p>This box uses <code>box-sizing: border-box</code>. Padding and borders are included <em>inside</em> the specified width, keeping total element dimensions predictable.</p>
    </div>

    <!-- Box 3: Custom Spacing -->
    <div class="box box-custom">
      <h2>Box 3: Custom Spacing</h2>
      <p>This box demonstrates distinct padding, thick borders, and outer margins to highlight spacing differences in DevTools.</p>
    </div>

  </main>

  <footer>
    <p>&copy; 2026 Web Development Assignment — Box Model</p>
  </footer>

</body>
</html>
File 2: styles.cssCSS/* Global Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: system-ui, -apple-system, sans-serif;
  background-color: #f4f6f8;
  color: #333;
  line-height: 1.6;
  padding: 30px;
}

.header {
  text-align: center;
  margin-bottom: 40px;
}

.header h1 {
  color: #1e3a8a;
  margin-bottom: 8px;
}

.container {
  max-width: 700px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 25px;
}

/* Base Box Style */
.box {
  background-color: #ffffff;
  border-radius: 8px;
}

/* 1. Content-Box Demonstration */
.box-content-box {
  box-sizing: content-box; /* Default behavior */
  width: 400px;
  padding: 30px;
  border: 10px solid #2563eb;
  margin: 10px auto;
}

/* 2. Border-Box Demonstration */
.box-border-box {
  box-sizing: border-box; /* Included in width */
  width: 400px;
  padding: 30px;
  border: 10px solid #0d9488;
  margin: 10px auto;
}

/* 3. Custom Box Demonstration */
.box-custom {
  box-sizing: border-box;
  width: 100%;
  padding: 20px;
  border: 4px dashed #d97706;
  margin: 20px 0;
  background-color: #fffbeb;
}

.box h2 {
  font-size: 1.25rem;
  margin-bottom: 10px;
}

code {
  background-color: #e2e8f0;
  padding: 2px 6px;
  border-radius: 4px;
  font-size: 0.9rem;
  color: #1e293b;
}

footer {
  text-align: center;
  margin-top: 40px;
  color: #64748b;
  font-size: 0.9rem;
}
Box Model Explanation & DevTools GuideContent: The innermost area where text and images appear (controlled by width and height).Padding: The space between the content and the border. It clears an area around the content inside the box.Border: A line that goes around the padding and content.Margin: The outermost space that separates the element from other neighboring elements.Difference between content-box and border-box:content-box: If you set width: 400px, padding and borders are added on top of that width. Total element width = $400px + 30px(padding) + 30px(padding) + 10px(border) + 10px(border) = 480px$.border-box: If you set width: 400px, the padding and borders are internalized within that 400px width. The content area shrinks automatically to accommodate them, making layout calculations much easier.