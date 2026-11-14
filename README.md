# AI College Advisor — Landing Page

The marketing landing page for **AI College Advisor**, a platform to simplify college admissions by connecting students and universities in one place.

> This repo is the **landing page** (a React single-page site). It's the front door to the product — students learn how it works and browse universities; universities partner and manage applications.

## What's on the page

- **For Students** — How It Works, Browse Universities, Application Guide
- **For Universities** — Partner With Us, Admin Portal
- **Resources** and **About Us**
- Responsive hero, feature grid, and call-to-action sections
- An **AI admissions advisor** section (see below)

The call-to-action buttons ("Start Your Application", "For Universities", "Create Your Account", "Learn More") are placeholders: they are not wired to anything yet.

## AI advisor

`src/components/AIAdvisor.js` is a Claude-powered widget on the landing page. A student describes their profile in free text, and the widget sends it to the Anthropic Messages API and shows a reach / match / safety university shortlist with next steps.

- **Bring your own key:** users enter their own Anthropic API key in the widget. No key is bundled with the app.
- The key is stored in the browser's `localStorage` (`anthropic_api_key`) and sent directly from the browser to the Anthropic API; there is no backend. Anyone with access to that browser profile can read it, so use a key you can revoke.
- The model is set by the `MODEL` constant at the top of `AIAdvisor.js`.

## Tech stack

- [React 18](https://react.dev/) via [Create React App](https://create-react-app.dev/) (`react-scripts`)
- [Tailwind CSS](https://tailwindcss.com/) for styling
- [lucide-react](https://lucide.dev/) for icons

## Getting started

```bash
npm install
npm start        # dev server at http://localhost:3000
npm run build    # production build to ./build
```

## Project structure

```
src/
├── components/
│   ├── LandingPage.js   # the full landing page (hero, features, CTA, footer)
│   └── AIAdvisor.js     # Claude admissions advisor widget (bring your own key)
├── App.js               # renders LandingPage
├── index.js             # entry point
└── index.css            # Tailwind directives + globals
public/
└── index.html
```
