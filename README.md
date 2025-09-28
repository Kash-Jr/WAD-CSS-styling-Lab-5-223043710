WAD621S Lab 05 - Web Application Styling

Overview

This repository contains the submission for Lab 05 of the Web Application Development (WAD621S) course. The task was to style UI components, including cards, buttons, chips, forms, and others, using CSS while maintaining consistency with provided CSS variables. This document outlines the design decisions made and challenges faced during implementation.

Design Decisions

Unified Styling with CSS Variables

CSS variables (e.g., --primary, --card-shadow) were applied consistently across components to ensure a cohesive design. For example, buttons use --primary for backgrounds, transitioning to --secondary on hover. This approach simplified theme switching, such as for dark mode, and ensured uniformity. Cards use background-color: var(--body-bg) to blend with the page background.

Modern Visual Design

Components were styled with rounded corners (e.g., 10px for buttons, 30px for cards) and subtle shadows for a polished look. Hover effects, such as cards shifting with transform: translateY(-7px) and deeper shadows, enhance interactivity. Buttons use border-radius: 10px and cursor: grab for a distinct, engaging feel.

Responsive Layout

A media query for screens below 768px stacks elements like .component-grid and .nav vertically, ensuring mobile compatibility. The component grid uses grid-template-columns: 1fr for single-column card display, meeting the lab’s responsive design requirement.

Interactive Feedback

Hover, focus, and active states were styled for usability. Buttons change color on hover, form inputs gain a blue glow on focus, and chips switch to --primary when active. For example, the slider thumb scales with transform: scale(1.5) on hover, providing clear visual cues.

Dark Theme Compatibility

Dark theme styles were applied to form inputs, tables, and the code editor using --dark backgrounds and --light text. Chips in dark mode maintain readability with adjusted backgrounds, ensuring consistency across themes.

Challenges Encountered

Achieving Visual Consistency

Varying HTML structures complicated uniform styling. Initial attempts led to inconsistent border-radius and padding values. Standardizing on values like 20px padding for cards and 25px border-radius for chips, along with CSS variables, resolved this, ensuring components like cards and widgets aligned visually.

Styling Interactive Components

Styling sliders and switches for cross-browser consistency was difficult. The slider required appearance: none and a custom ::-webkit-slider-thumb, while switches used transform: translateX(20px) for animations. Browser testing refined these elements for smooth operation.

Mobile Layout Adjustments

Components like button groups and chips appeared cramped on mobile due to larger gaps (e.g., 60px for .chips-container). A media query adjusted layouts to stack vertically, with testing on smaller screens ensuring usability and proper spacing.

Dark Theme Integration

Ensuring all components adapted to the dark theme without disrupting the light theme was complex. Overrides for .dark-theme .form-input and .dark-theme .code-editor were tested with the customization panel to maintain readability and consistency.

Managing Element Positioning

Overlapping issues with modals and tooltips arose due to z-index conflicts. Setting z-index: 1000 for .modal and adjusting tooltip positioning (e.g., bottom: 125%) ensured proper layering, with the .panel-pull-tab styled at z-index: 999 to avoid conflicts.

Submission Notes





Styles are implemented in styles.css and applied to index.html.



Tested in Chrome and Firefox for responsiveness and theme functionality.



JavaScript in scripting.js manages interactivity (e.g., modals, toasts), styled to match the design system.



Core styling requirements were prioritized, with some optional features (e.g., custom theme toggle) omitted due to time constraints.
