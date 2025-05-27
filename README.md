# 🗺️ Traveling Salesman Problem — Brute‑Force Solver + Animated Route

Small, self‑contained demo that **finds the optimal tour for a handful of cities** and **animates the salesman’s journey**.

| Part | Highlights |
|------|------------|
| `tsp.py` | * Brute‑force search using `itertools.permutations`<br>* Euclidean distance via `math.hypot`<br>* Prints best path & total distance |
| `animate.py` | * Smoothly interpolates between city coordinates with `numpy.linspace`<br>* Draws static city markers, a growing blue route, and a red “salesman” dot<br>* Embeds directly in Google Colab (`ani.to_jshtml()`), or opens a window locally |

---

## 📦 Requirements

```bash
pip install numpy matplotlib

```
#🚀 Quick Start
# 1 – find the optimal route
python tsp.py
# ➜ Best Path: ['A', 'B', 'D', 'E', 'C', 'A']
# ➜ Total Distance: 20.19

# 2 – watch the salesman travel that path
python animate.py        # local GUI window

# Running in Colab?
Just run TSP_Code.ipynb first, and then second script – it will embed a HTML5 animation inline.

# 📝 How it works
1- Brute‑Force Search
Generates every permutation of visiting the cities, closes the loop, sums the distances, and keeps the shortest. Elegant but exponential—meant for ≤ 8 cities.

2- Animation
numpy.linspace creates fine‑grained points between each pair of cities.
matplotlib.animation.FuncAnimation iteratively:

** grows the blue poly‑line (line.set_data)

** moves the red dot (dot.set_data)
Wrapping single coordinates in [...] avoids the common “x must be a sequence” RuntimeError.

#✨ Customize

** Add/rename cities in the cities dictionary.

** Switch to a heuristic (e.g., simulated annealing) and feed its best_path into animate.py—visualization just works.

# 📄 License
MIT — free to learn from, fork, and play with!

![image](https://github.com/user-attachments/assets/fd451cfc-e5be-44b2-b437-f7424370c87c)
