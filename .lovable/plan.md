

# Speech Script for 12-Minute Presentation

**Important note from the assignment guide**: "Don't read from a script. If necessary, use cue cards and rehearse a few times before recording." This script will serve as detailed cue cards / rehearsal material — each speaker should internalize the points and present naturally.

## Output

A markdown document saved to `/mnt/documents/speech_script.md` containing speaker-by-speaker talking points organized by slide, with approximate timings, key phrases to hit, and transition cues.

## Structure

| Speaker | Slides | Time |
|---------|--------|------|
| Krish | 0 (Declarations) + 1 (Intro/Overview) | ~2.5 min |
| Jakub | 2 (CBS vs PBS) | ~2.5 min |
| Christian | 3 (LNS/Neural LNS) + 4 (Multi-Subset Architecture) | ~3.5 min |
| Francisco | 5 (Results) + 6 (Critical Analysis) + 7 (Course Connections) | ~3.5 min |

## Content per speaker

### Krish (Slides 0-1, ~2.5 min)
- Slide 0: Quick declarations — names, student IDs, AI tool disclosure, no collaboration
- Slide 1: Introduce the paper (title, authors, MIT, ICLR 2024), define MAPF problem formally, explain why NP-hard, state the paper's contribution (first deep architecture for LNS guidance in MAPF), explain why this paper was chosen (connects to CBS/week 7, heuristic search/weeks 1-3, multi-agent coordination/week 6, hospital domain project)

### Jakub (Slide 2, ~2.5 min)
- CBS: two-level search — high level builds constraint tree branching on conflicts, low level runs A* per agent with constraints. Optimal but exponential, scales to ~200 agents
- PBS: replaces constraints with priority orderings (A>B vs B>A), dynamically searches over orderings. Suboptimal but scalable to hundreds of agents
- Key distinction: PBS is NOT prioritized planning (PP fixes ordering upfront; PBS searches dynamically). PBS is the subproblem solver used inside the LNS framework of this paper

### Christian (Slides 3-4, ~3.5 min)
- Slide 3: LNS framework — iterative destroy-and-repair. Start with initial solution, select subset of k agents, destroy their paths, repair with PBS, accept if improved. Unguided LNS picks random subsets (most yield no improvement). Neural LNS: generate J subsets, score each with neural network f_θ, pick the best one. 1.5-4x faster convergence
- Slide 4: Multi-Subset Architecture — the main contribution. Input: H×W×T tensors (current paths, shortest paths, obstacles). Shared backbone with 8 blocks interleaving 3D convolution (local spatiotemporal interactions) and intra-path attention (global trajectory-level information flow). Per-agent features extracted, then J lightweight transformer heads score each subset. Key advantage: heavy computation done once, only lightweight heads run J times — ~2x faster than naive Per-Subset baseline

### Francisco (Slides 5-6-7, ~3.5 min)
- Slide 5: Results table — Multi-Subset consistently beats Unguided LNS across all maps. Highlight ost003d and den520d: 200/0 win/loss. 1.5-4x speedup, <0.025s neural overhead per iteration. Generalization: works across agent counts but NOT across map sizes/obstacle types
- Slide 6: Critical analysis — Strengths: novel architecture, principled design, meaningful speedup, some generalization. Weaknesses: NN only ranks predefined neighborhoods (doesn't generate them), inference overhead accumulates, simplified representation (truncated time horizons), only tested on grid benchmarks (not richer domains like hospital setting)
- Slide 7: Course connections — map to classical planning (wk 1), learned heuristics (wk 3), multi-agent decomposition (wk 6), CBS (wk 7), hospital domain project. Key takeaways + thank you + citation

## Technical details
- The script will be generated as a markdown file to `/mnt/documents/speech_script.md`
- Includes timing markers, transition phrases, and emphasis notes
- Written conversationally (not to be read verbatim) per assignment guidelines

