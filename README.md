
Here’s a simpel concept to visualize project ideas.
The app will display projects in a vertical, block-based layout—**Done** on top, **Doing** below, and **To Do** at the bottom.
Each block will show project details in a clear and visually engaging way, with the ability to expand projects for more information and an option to share the entire list publicly.


# Vision

IdeaFlow is a web app designed to empower anyone to organize, visualize, and share their project ideas with clarity and creativity. Our ambition is to create a simple, intuitive platform where users can capture their ideas, track their progress, and present them in a visually engaging way—without complexity or barriers. We envision IdeaFlow as a tool that inspires action, fosters productivity, and allows users to share their creative journeys publicly, making it accessible to dreamers, planners, and doers worldwide.

The app’s core philosophy is simplicity and accessibility:
- **Organize**: Add and categorize project ideas effortlessly.
- **Visualize**: See your progress in a clear, colorful, block-based layout—Done (green), Doing (vibrant), and To Do (ready to start).
- **Share**: Export your board as a JPG to showcase your ideas or share them with others.

Our long-term goal is to evolve IdeaFlow into a collaborative platform where users can save their boards online, share them via unique URLs, and inspire others, all while keeping the experience seamless and delightful.

# Core Features

- **Vertical Block Layout**: Projects are organized into three blocks:
  - **Done**: Green-themed, showing completed projects (100% progress).
  - **Doing**: Colorful, with projects in progress (1%-90%), colored by tags.
  - **To Do**: Neutral, for ideas ready to start (0% progress).
- **Add Ideas**: Click “Add Idea” to enter a project’s name, short description, full description, tags, subtasks, and completion percentage (0% to 100% in 10% increments).
- **Expandable Details**: Click a project to view its full description and subtasks.
- **Export as JPG**: Download your board as a JPG image for sharing or printing.
- **Local Persistence**: Projects are saved in your browser’s local storage, so your board persists across sessions.


# Web App Concept

## Layout
The app uses a single-column, vertical layout with three distinct blocks stacked on top of each other:

- **Done Block** (Top):
  - Positioned at the top of the page.
  - Styled with a green theme (e.g., green background or header) to indicate completion.
  
- **Doing Block** (Middle):
  - Placed directly below the Done block.
  - Features projects in various colors to reflect their status or categories, making them visually distinct.

- **To Do Block** (Bottom):
  - Located at the bottom, styled in a neutral tone (e.g., gray) to suggest readiness for action.

Each block contains a list of project cards, arranged vertically within its section.

## Project Cards
Each project is displayed as a card with the following details:

- **Done Block**:
  - **Name**: The project’s title.
  - **Description**: A short summary of the project.
  - **Completion Percentage**: Shown as 100% (e.g., text like “100%” or a full progress bar).
  - Styled with a green accent (e.g., border or checkmark).

- **Doing Block**:
  - **Name**: The project’s title.
  - **Description**: A short summary.
  - **Completion Percentage**: A number (e.g., “75%”) or a progress bar showing progress.
  - **Colors**: Each project card uses a distinct color, possibly based on a category (e.g., work, personal) or tag, to make this block visually lively.

- **To Do Block**:
  - **Name**: The project’s title.
  - **Description**: A short summary.
  - **No Percentage**: No completion percentage is displayed, keeping it simple and focused on readiness.

## Expandable Details
- Clicking a project card expands it inline (below the card) to reveal additional details:
  - **Full Description**: A longer explanation of the project.
  - **Subtasks**: A list of tasks with their completion status (e.g., “Task 1 - Done,” “Task 2 - Pending”).
- The expanded section can be collapsed by clicking again, maintaining a clean interface.

## Visual Design
- **Done Block**: Green header or background for the block, with project cards possibly having green accents (e.g., a checkmark icon).
- **Doing Block**: A neutral header (e.g., light blue), with each project card colored based on its category or primary tag (e.g., red for urgent, blue for personal).
- **To Do Block**: A neutral header (e.g., light gray), with project cards in a default style (e.g., white or gray borders).
- **Colors in Doing**: The “in colors” requirement is interpreted as each project having a unique color, likely tied to a category or tag, making this block vibrant and easy to scan.

## Public Sharing
- Users can share their entire project list publicly.
- A “Share Publicly” option generates a unique URL (e.g., `/public/username`).
- The public view displays the same vertical block layout and expandable details but is read-only, ensuring viewers can explore without editing.

## Additional Considerations
- **Tags**: Projects can include tags (e.g., “urgent,” “hobby”) displayed as colored badges on the card. Colors could be generated dynamically from the tag name for consistency.
- **Completion Percentage**: For “Doing” projects, this could be calculated from completed subtasks (e.g., 3/5 tasks done = 60%). For “Done,” it’s always 100%. “To Do” omits it entirely.
- **No Overcomplication**: The focus is on visualization—no Kanban boards, no drag-and-drop, just a straightforward, expandable list.

---

## Sample Wireframe
```
[Header: App Name | Share Publicly Button]

[Done Block - Green Header]
  - Project 1: Name, Description, 100% [Expand]
  - Project 2: Name, Description, 100% [Expand]

[Doing Block - Neutral Header]
  - Project 3: Name, Description, 75% (Red) [Expand]
  - Project 4: Name, Description, 20% (Blue) [Expand]

[To Do Block - Gray Header]
  - Project 5: Name, Description [Expand]
  - Project 6: Name, Description [Expand]
```

## Expanded Example
```
[Doing Block]
  - Project 3: Name, Description, 75% (Red) [Collapse]
    - Full Description: Lorem ipsum...
    - Subtasks:
      - Task 1: Done
      - Task 2: Pending
      - Task 3: Done
```

# Why This Works
- **Meets Requirements**: Delivers a block-based, vertical layout (no columns) with Done (green), Doing (colored), and To Do (neutral) sections.
- **Visual Clarity**: Uses colors, progress indicators, and expandable cards to make project status and details easy to grasp.
- **Simplicity**: Avoids complex features like Kanban or drag-and-drop, focusing solely on visualization and sharing.
- **Flexibility**: Allows public sharing while keeping the design intuitive for both users and viewers.


---

# Technical Details
- **Frontend**: Single-page React app using CDNs for React, Tailwind CSS, and `html2canvas`.
- **Persistence**: Browser `localStorage` for saving projects.
- **Export**: `html2canvas` captures the board as a JPG.
- **No Backend**: Client-side only for simplicity, suitable for Milestone 1.

# Future Roadmap
- **Public Sharing**: Add a backend to store boards and generate shareable, read-only URLs.
- **User Accounts**: Allow users to save boards online with authentication.
- **Enhanced Features**: Support project editing/deletion, PDF export, and collaborative boards.
- **Improved Export**: Offer options for board-only or full-page JPG exports.

# Contributing
We welcome contributions to make IdeaFlow even better! To contribute:
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-name`).
3. Commit changes (`git commit -m "Add feature"`).
4. Push to the branch (`git push origin feature-name`).
5. Open a pull request.

# License
MPL2 License.
See `LICENSE` for details.

---

*Built with ❤️ to inspire creativity and productivity.*