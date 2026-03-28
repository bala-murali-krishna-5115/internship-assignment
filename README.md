# Internship Assignment — GSAP Scroll Hero Animation

A React component featuring a GSAP-powered scroll-triggered hero section animation.

## Features

- **Character-by-character text animation** — headline letters animate in with stagger using GSAP
- **Stat counters fade-in** — statistics animate in with a delayed stagger
- **Scroll-pinned car animation** — a car image drives across the screen driven by scroll position using `ScrollTrigger`

## Tech Stack

- React
- [GSAP](https://gsap.com/) + ScrollTrigger plugin
- Tailwind CSS (utility classes)

## Usage

1. Install dependencies:
   ```bash
   npm install gsap
   ```

2. Import and use the component:
   ```jsx
   import App from './internshipAssignment';
   ```

## Component: `internshipAssignment.jsx`

The main export is an `App` component that renders a full-screen hero section with:
- A pinned scroll section with a headline, stats, and an animated car image
- A secondary "scroll to see animation" section below

## Author

bala-murali-krishna-5115
