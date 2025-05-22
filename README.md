# Interactive Maze Solver Visualizer

A web-based application that allows users to generate random mazes and visualize various graph traversal algorithms (BFS, DFS, A*, Dijkstra's) solving them in real-time. Built with pure HTML, CSS, and JavaScript.

**Live Demo:** [https://varshanth-c.github.io/Search_Algorithm/](https://varshanth-c.github.io/Search_Algorithm/)
*(Note: Ensure GitHub Pages is enabled for this link to work.)*

## Features

*   **Dynamic Maze Generation:**
    *   Adjustable maze width and height (5x5 to 40x40).
    *   Configurable "Wall Density" (complexity) to control maze intricacy.
    *   Uses a Recursive Backtracking algorithm for generation.
*   **Algorithm Visualization:**
    *   **Breadth-First Search (BFS):** Explores layer by layer, guarantees shortest path.
    *   **Depth-First Search (DFS):** Explores as far as possible along branches.
    *   **A\* Search:** Informed search using Manhattan distance heuristic.
    *   **Dijkstra's Algorithm:** Finds shortest paths (behaves like BFS in unweighted graphs).
*   **Real-time Animation:**
    *   Adjustable animation speed.
    *   Step-by-step execution control.
    *   Pause and Resume functionality.
*   **Interactive Maze Editing:**
    *   Toggle walls on/off.
    *   Set custom Start (Green) and End (Red) points.
    *   Supports direct click based on selected "Edit Mode" or keyboard modifiers (Shift+Click for Start, Ctrl+Click for End, Alt+Click for Wall).
*   **Visual Distinction:**
    *   Clear color coding for Start, End, Walls, Empty Paths, Visited Cells, Frontier Cells, and the Final Solution Path.
*   **User Interface:**
    *   Responsive design.
    *   Dark/Light theme toggle.
    *   Integrated algorithm information panel.
    *   Statistics display (Cells Visited, Path Length, Execution Time).
*   **Persistence:**
    *   Save current maze design to browser's localStorage.
    *   Load previously saved maze.
    *   Theme preference saved in localStorage.

## Tech Stack

*   **HTML5:** Structure of the web page.
*   **CSS3:** Styling, layout, and theme management.
*   **Vanilla JavaScript (ES6+):** All application logic, including:
    *   Maze generation algorithms.
    *   Pathfinding algorithms (BFS, DFS, A*, Dijkstra's).
    *   Canvas API for rendering the maze and animations.
    *   DOM manipulation for UI updates and interactivity.

## How to Run Locally

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/varshanth-c/Search_Algorithm.git
    ```
2.  **Navigate to the project directory:**
    ```bash
    cd Search_Algorithm
    ```
3.  **Open `index.html` in your web browser.**
    No build steps or dependencies are required as it's pure HTML, CSS, and JavaScript.

## File Structure
*(Note: The CSS and JavaScript are currently embedded within `index.html`.)*

## Key Code Concepts

The core logic is encapsulated within the `MazeSolver` class in `index.html`.

*   **`MazeSolver` Class:** Manages the maze state, rendering, UI interactions, and algorithm execution.
    *   `initialize()`: Sets up the initial maze and UI.
    *   `generateMaze()`: Implements the maze generation logic (Recursive Backtracker).
    *   `draw()`: Renders the maze on the HTML5 canvas.
    *   `runBFS()`, `runDFS()`, `runAStar()`, `runDijkstra()`: Implement the respective pathfinding algorithms. They populate an `animationQueue` with steps to visualize.
    *   `startAnimation()`, `stepAlgorithm()`, `pauseResumeAlgorithm()`: Control the animation flow from the `animationQueue`.
    *   `handleCanvasClick()`: Manages user interactions for editing the maze.
    *   `saveMaze()`, `loadSavedMaze()`: Handle localStorage operations.
    *   `toggleTheme()`: Switches between light and dark themes.
*   **Maze Representation:** A 2D array (`this.maze`) stores the state of each cell (EMPTY, WALL, START, END, VISITED, PATH, FRONTIER).
*   **Animation:** Algorithms don't draw directly. Instead, they push "step" objects (e.g., `{type: 'visit', x: col, y: row}`) onto an `animationQueue`. A separate timer (`setInterval`) processes this queue to create the visual animation at the chosen speed.

## Potential Future Enhancements

*   Implement more maze generation algorithms (e.g., Prim's, Kruskal's).
*   Add more pathfinding algorithms (e.g., Greedy Best-First Search).
*   Allow weighted paths and demonstrate algorithms like Dijkstra's more effectively.
*   Introduce "obstacles" or different terrain types.
*   Improve mobile responsiveness and touch interactions for editing.
*   Option to export/import maze designs as files.
*   Unit tests for algorithms.

## Contributing

Contributions are welcome! If you have suggestions or want to improve the visualizer, feel free to:

1.  Fork the Project.
2.  Create your Feature Branch (`git checkout -b feature/AmazingFeature`).
3.  Commit your Changes (`git commit -m 'Add some AmazingFeature'`).
4.  Push to the Branch (`git push origin feature/AmazingFeature`).
5.  Open a Pull Request.

Please ensure your code adheres to the existing style and that any new features are well-documented.

Happy Maze Solving!

