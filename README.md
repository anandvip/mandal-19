import matplotlib.pyplot as plt
import matplotlib.patches as patches

# Define the flow chart elements and connections
elements = [
    ("User opens the application", (0.1, 0.9)),
    ("UI displays greeting message and options", (0.5, 0.9)),
    ("User creates a new Mandal", (0.9, 0.9)),
    ("Fills in Mandal name, duration, and start date", (0.9, 0.8)),
    ("Clicks 'Create Mandal'", (0.9, 0.7)),
    ("Active Mandal is displayed", (0.5, 0.7)),
    ("Dashboard shows progress, session statistics, and options to start/stop sessions", (0.5, 0.6)),
    ("User starts a meditation session", (0.1, 0.5)),
    ("Clicks 'Start Session'", (0.1, 0.4)),
    ("Timer begins", (0.1, 0.3)),
    ("User stops a meditation session", (0.9, 0.5)),
    ("Clicks 'Stop Session'", (0.9, 0.4)),
    ("Session is recorded", (0.9, 0.3)),
    ("User embeds media", (0.1, 0.2)),
    ("Enters YouTube or SoundCloud URL", (0.1, 0.1)),
    ("Clicks 'Embed Media'", (0.1, 0)),
    ("Media is displayed", (0.5, 0.1)),
    ("User views session history", (0.5, 0.4)),
    ("Searches, sorts, and edits notes in session history", (0.5, 0.3)),
    ("User adds past sessions", (0.5, 0.2)),
    ("Opens past session modal", (0.5, 0.1)),
    ("Selects date and adds sessions", (0.5, 0)),
    ("User provides feedback", (0.9, 0.2)),
    ("Opens feedback modal", (0.9, 0.1)),
    ("Enters feedback and submits it", (0.9, 0)),
    ("Notifications", (0.5, 0.5)),
    ("Toast messages display feedback for actions", (0.5, 0.6)),
]

connections = [
    (0, 1), (1, 2), (2, 3), (3, 4), (4, 5), (5, 6),
    (6, 7), (7, 8), (8, 9), (6, 10), (10, 11), (11, 12),
    (6, 13), (13, 14), (14, 15), (15, 16), (6, 17), (17, 18),
    (6, 19), (19, 20), (20, 21), (6, 22), (22, 23), (23, 24),
    (5, 25), (25, 26)
]

# Create the flow chart
fig, ax = plt.subplots(figsize=(12, 18))
ax.set_xlim(0, 1)
ax.set_ylim(0, 1)
ax.axis('off')

# Add elements to the chart
for text, pos in elements:
    ax.text(pos[0], pos[1], text, ha='center', va='center', fontsize=10,
            bbox=dict(boxstyle='round,pad=0.3', edgecolor='black', facecolor='lightblue'))

# Add connections
for start, end in connections:
    start_pos = elements[start][1]
    end_pos = elements[end][1]
    ax.add_patch(patches.FancyArrowPatch(start_pos, end_pos, connectionstyle="arc3,rad=.5",
                                         arrowstyle='-|>', mutation_scale=10, color='black'))

plt.title("Application Flow Chart", fontsize=16)
plt.show()
