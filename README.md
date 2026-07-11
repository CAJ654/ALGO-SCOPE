# ALGO·SCOPE

A lab-instrument style algorithm visualizer for watching sorting, pathfinding, and search algorithms execute in real time.

Built for [Super Software Lab](https://www.youtube.com/@supersoftwarelab) — AP Computer Science, Cybersecurity, and Networking education.

## What’s Inside

Three visualization channels, each with multiple algorithms and live performance metrics:

### CH·01 Sort

Watch algorithms order arrays by value. Compare and swap counts show you the cost of each decision.

- **Bubble Sort** — O(n²) — the naive approach: adjacent pairs swap until sorted
- **Selection Sort** — O(n²) — find the minimum each time, build sorted region backward
- **Insertion Sort** — O(n²) — grow a sorted region by inserting unsorted elements
- **Merge Sort** — O(n log n) — divide-and-conquer with guaranteed performance
- **Quick Sort** — O(n log n) average — pivot-based partitioning (watch the pivot glow)

Adjust array size (10–80 bars) and animation speed on the fly. Single-step to narrate one comparison at a time.

### CH·02 Pathfind

Find the shortest path through a grid. Draw walls by dragging. Watch different algorithms explore.

- **BFS** — O(V + E) — explores in rings, guarantees shortest path
- **DFS** — O(V + E) — dives deep, finds *a* path, usually not the shortest
- **Greedy Best-First** — O(E log V) — chases the heuristic, fast but fooled by walls
- **A*** — O(E log V) — balances cost-so-far and heuristic, shortest path with fewer expansions

The readout shows cells expanded vs. path length — watch A* win by exploring less ground.

### CH·03 Search

Find a target value in a sorted array. Values miss ~20% of the time so you see both outcomes.

- **Linear Search** — O(n) — check every element left to right
- **Binary Search** — O(log n) — halve the search space each time, watch eliminated cells vanish in chunks

See why binary search is called “logarithmic” — 5 checks cover 21 elements.

## Design

Built with React (CDN-loaded for zero build step). The architecture uses 
generator functions to yield animation frames, which keeps algorithm logic 
separate from UI state management. This makes it easy to add new algorithms 
without touching React.

Chose a dark oscilloscope theme to match a "lab instrument" aesthetic 
and reduce visual noise during visualization. Color choices (hot, swap, ok, 
pivot) are designed to make state transitions obvious at a glance.

Single-step mode prioritizes education — teaching narration is much easier 
when you can pause mid-sort and explain what just happened.

## How to Use

### Online

1. Download `index.html`
1. Open in a browser — that’s it

### Deploy to GitHub Pages

1. Create a new GitHub repo (or use an existing one)
1. Drop `index.html` in the root
1. Go to **Settings → Pages** → set source to `main` branch
1. Your visualizer lives at `yourusername.github.io/repo-name`

### Local Development

The repo contains two versions:

- **`index.html`** — fully self-contained, ready to deploy. Loads React from CDN
- **`AlgoScope.jsx`** — source component if you want to import it into a larger React project

## Controls

**Play / Pause** — Run at full speed or freeze to inspect a frame

**Step** — Single-step through the algorithm like a debugger (useful for recording lessons)

**Speed** — Adjust animation delay (1–100)

**Reset / Shuffle / Clear** — Start over with new data or configuration

For **Pathfind**: drag on the grid to paint walls; click cells to toggle wall/open

## What You’ll Learn

- How sorting algorithms compare, swap, and partition
- Why some algorithms guarantee shortest paths (BFS, A*) while others don’t (DFS, Greedy)
- Why binary search is so much faster than linear search on sorted data
- The difference between best-case, average-case, and worst-case complexity
- How heuristics guide search (A*) vs. blind exploration (BFS)

## Technical Details

**Built with**

- React 18 (loaded from CDN — no build step)
- Pure CSS Grid + Flexbox for layout
- Generator functions for step-by-step execution
- Tailwind-inspired design tokens on a dark oscilloscope theme

**Browser Support**

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Responsive down to mobile (though the grids are tight)

## Tips for Teachers

- **Single-step mode** works great for recording; pause, narrate one operation, step, repeat
- **Quick Sort** shows pivot-based partitioning clearly — the pivot glows and holds steady
- **A* vs. Greedy** on a grid with a maze wall demonstrates the value of cost-so-far
- **Binary Search** on n=21 shows why O(log n) matters: max 5 checks vs. 21 checks for linear

## License

Open source. Use, modify, and share freely.

-----

Made by Super Software Lab for students building intuition around core algorithms.
