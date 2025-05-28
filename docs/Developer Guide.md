# Developer Guide

This document explains the structure, key components, and implementation details of the IdeaFlow project. It serves as a guide for developers to understand the codebase and contribute effectively.

## Project Structure

- `/`: Root directory containing the main `index.html`, `README.md`, and `LICENSE`.
- `/docs`: Contains project documentation, including this guide, the Changelog, and the Master Implementation Plan.

## Technologies Used

- **Frontend:** React (via CDN), Tailwind CSS (via CDN)
- **Export:** `html2canvas`, `jspdf`
- **Persistence:** Browser `localStorage`
- **Build Tool:** Babel (via CDN)

## Core Components

### `index.html`

This is the main entry point of the application. It includes the necessary HTML structure, links to external libraries (React, ReactDOM, Babel, Tailwind CSS, html2canvas, jspdf), and contains the main React application code within a `<script type="text/babel">` tag.

### React Components

- **`App`:** The main application component that manages the state of projects, handles adding, deleting, and updating projects, and controls the visibility of the Add Idea form. It also includes functions for exporting the board as JPG and PDF.
- **`ProjectCard`:** Displays individual project details. It handles toggling the expansion of project details, managing the completion percentage slider, and triggering project updates and deletion.
- **`AddIdeaForm`:** A modal form for adding new project ideas. It captures project details and calls the `onAddProject` function when the form is submitted.

## Data Structure

Project data is stored as an array of objects in the browser's `localStorage`. Each project object has the following structure:

```javascript
{
  id: string, // Unique identifier (timestamp)
  title: string,
  description: string, // Short description
  full_description: string, // Detailed description
  completion_percentage: number, // 0-100
  status: 'to do' | 'doing' | 'done', // Derived from completion_percentage
  tags: string[], // Array of tags
  subtasks: { name: string, completed: boolean }[] // Array of subtask objects
}
```

## Key Functionality

- **Adding Projects:** The `AddIdeaForm` collects project details and the `addProject` function in the `App` component adds the new project to the state and `localStorage`.
- **Viewing Projects:** Projects are filtered and mapped within the `App` component to display them in the "Done", "Doing", and "To Do" blocks using the `ProjectCard` component.
- **Expanding Project Details:** The `toggleExpand` function in the `App` component manages the `expandedProjects` state, controlling which `ProjectCard` components show their full details.
- **Updating Project Completion:** The `handleCompletionChange` function updates the `completion_percentage` and `status` of a project.
- **Deleting Projects:** The `deleteProject` function removes a project from the state and `localStorage`.
- **Updating Project Details:** The `updateProject` function modifies the details of an existing project.
- **Exporting Board:** The `exportAsJpg` and `exportAsPdf` functions use `html2canvas` and `jspdf` to capture the `#ideaFlowBoard` element and save it as an image or PDF.
- **Importing/Exporting JSON:** Functionality is included to export and import project data as a JSON file, allowing users to back up or share their boards.

## Styling

Tailwind CSS is used for styling, providing utility classes for layout, typography, colors, spacing, and more. Responsive design is handled through Tailwind's responsive prefixes (e.g., `sm:`, `md:`, `lg:`).

## Accessibility

Efforts are made to ensure the application is accessible. This includes using semantic HTML, providing alternative text where necessary, and ensuring interactive elements are keyboard navigable and have sufficient touch target sizes.

---

This guide will be updated as the project evolves.