# K Explore Events

![K Explore Events](https://images.unsplash.com/photo-1540575467063-178a50c2df87?w=1200&auto=format&fit=crop)

A modern, visually stunning, fully responsive Event Management Website built with React, Vite, Tailwind CSS, and React Router.

## 🚀 Live Demo

Check the website:https://dancing-medovik-2f97bb.netlify.app
## ✨ Features

### Core Features
- **Beautiful Homepage**: Hero section with animated background, stats strip, and featured events
- **Event Browsing**: Grid view of all events with 12+ mock events across 8 categories
- **Advanced Search**: Real-time search by name, venue, and description with debouncing
- **Category Filtering**: Filter events by Tech, Music, Sports, Art, Workshop, Business, Food, Education
- **Event Details**: Comprehensive event pages with countdown timers, pricing, and availability
- **Registration System**: Complete registration flow with form validation
- **My Registrations**: View and manage all your registrations with cancellation option
- **Responsive Design**: Mobile-first approach tested at 360px, 768px, and 1280px+

### Bonus Features
- **Dark/Light Mode**: Persisted in Local Storage, respects system preference
- **Countdown Timers**: Real-time countdowns on event cards and detail pages
- **Smooth Animations**: Framer Motion page transitions, scroll reveals, and staggered card entrances
- **Local Storage**: Registration data persisted locally
- **Duplicate Prevention**: Prevents duplicate registrations for same email + event
- **URL Sync**: Search and filter state synced with URL query params
- **Loading States**: Skeleton loaders for better UX
- **Empty States**: Friendly messages when no results found

## 🛠 Tech Stack

- **React 18** - UI library
- **Vite** - Build tool and dev server
- **Tailwind CSS 3** - Utility-first CSS framework with dark mode
- **React Router v6** - Client-side routing
- **Framer Motion** - Animation library
- **Lucide React** - Icon library
- **No Backend** - Mock data and Local Storage

## 📁 Project Structure

```
src/
├── components/
│   ├── layout/
│   │   ├── Navbar.jsx       - Glassmorphism navigation with theme toggle
│   │   ├── Footer.jsx       - Footer with links and social icons
│   │   └── ScrollToTop.jsx  - Scroll to top on route change
│   ├── home/
│   │   ├── Hero.jsx         - Hero section with animations
│   │   └── FeaturedEvents.jsx - Featured events grid
│   ├── events/
│   │   ├── EventCard.jsx    - Event card component
│   │   ├── EventGrid.jsx    - Events grid with skeleton loading
│   │   ├── SearchBar.jsx    - Search input component
│   │   ├── CategoryFilter.jsx - Category filter chips
│   │   ├── CountdownTimer.jsx - Countdown timer component
│   │   └── EmptyState.jsx   - Empty state component
│   ├── registration/
│   │   ├── RegistrationForm.jsx - Registration form with validation
│   │   └── ConfirmationModal.jsx - Success confirmation modal
│   └── ui/
│       ├── Button.jsx       - Reusable button component
│       ├── Badge.jsx        - Category badge component
│       ├── Input.jsx        - Form input with error handling
│       └── Skeleton.jsx     - Loading skeleton component
├── pages/
│   ├── Home.jsx             - Home page
│   ├── Events.jsx           - Events listing page
│   ├── EventDetails.jsx     - Event details page
│   ├── MyRegistrations.jsx  - User registrations page
│   └── NotFound.jsx         - 404 page
├── context/
│   ├── ThemeContext.jsx     - Theme management context
│   └── RegistrationContext.jsx - Registration management context
├── hooks/
│   ├── useLocalStorage.js   - Local storage hook
│   ├── useTheme.js          - Theme hook
│   └── useCountdown.js      - Countdown timer hook
├── utils/
│   ├── validators.js        - Form validation utilities
│   └── formatDate.js        - Date formatting utilities
├── data/
│   └── events.js            - Mock event data
├── App.jsx                  - Main app component with routing
├── main.jsx                 - React entry point
└── index.css                - Global styles and Tailwind imports
```

## 📦 Installation

1. **Clone the repository**
```bash
git clone https://github.com/your-username/k-explore-events.git
cd k-explore-events
```

2. **Install dependencies**
```bash
npm install
```

3. **Start development server**
```bash
npm run dev
```

4. **Build for production**
```bash
npm run build
```

5. **Preview production build**
```bash
npm run preview
```

## 🎨 Design Decisions

### Color Palette
- **Primary**: Indigo/Violet spectrum (primary-50 to primary-900)
- **Accent**: Orange spectrum for CTAs and highlights
- **Dark Mode**: Custom dark colors with proper contrast ratios
- **Semantic Colors**: Tailwind's semantic colors for success, error, warnings

### Typography
- **Headings**: Poppins (modern, geometric sans-serif)
- **Body**: Inter (clean, readable sans-serif)
- Google Fonts loaded with proper fallbacks

### UI Components
- **Glassmorphism**: Navbar with backdrop blur
- **Neumorphism-inspired**: Soft shadows and rounded corners
- **Cards**: rounded-2xl (1rem) for modern feel
- **Shadows**: Multi-layered shadows for depth

### Responsive Breakpoints
- **Mobile**: < 640px (sm)
- **Tablet**: 640px - 1024px (md, lg)
- **Desktop**: > 1024px (xl)
- Hamburger menu on mobile, full nav on desktop
- 1/2/3-column event grid based on screen size

## 🔧 Implementation Details

### Requirements Implementation

#### 1. Homepage
- Hero section with gradient background and decorative elements
- Floating animated card showing event preview
- Stats strip (500+ events, 50K+ attendees, 25+ cities)
- Featured events section with 6 event cards
- Smooth scroll to events section

#### 2. Event Cards
- Image with lazy loading and error fallback
- Event name, date, venue, category badge
- Short description (line-clamp-2)
- Countdown timer overlay (compact version)
- Hover lift/scale animations
- "View Details" button

#### 3. Events Page
- Grid of all 12 events
- Live search with debouncing
- Category filter chips (8 categories + All)
- Sort by date (automatic)
- Empty state when no matches
- Skeleton loaders on initial load
- URL query params sync

#### 4. Event Details Page
- Large hero image with category badge
- Complete event information (date, time, venue, organizer, price, seats)
- Full countdown timer (days/hours/minutes/seconds)
- Registration form pre-filled with event
- Handle invalid IDs with friendly 404

#### 5. Registration Form
- Fields: Name, Email, Phone, Event (dropdown if not pre-selected)
- Validation:
  - Name: min 3 chars, letters/spaces only
  - Email: valid email regex
  - Phone: 10 digits
  - Event: required
- Validate on blur and submit
- Inline error messages with aria-live
- Disable submit while invalid
- Loading state during submission
- Success confirmation modal with registration ID
- Duplicate prevention check

#### 6. My Registrations Page
- List all user registrations
- Show registration ID, event name, date
- Cancel registration option
- Empty state if no registrations

### Bonus Features Implementation

#### Dark/Light Mode
- Toggle in navbar
- Persisted in Local Storage
- Respects system preference on first load
- Smooth CSS transitions
- Proper dark mode colors for all components

#### Countdown Timers
- Custom useCountdown hook
- Compact version on cards (days/hours)
- Full version on details page
- Shows "Event has ended" when past
- Real-time updates every second

#### Animations
- Framer Motion for all animations
- Page transitions on route change
- Scroll reveal on sections
- Staggered card entrance
- Modal animations
- Button hover/tap effects
- Hero floating card animation

#### Local Storage
- useLocalStorage custom hook
- Theme persistence
- Registration data persistence
- Duplicate check using stored data

## ♿ Accessibility

- Semantic HTML5 elements
- Labels linked to inputs
- aria-live for form errors
- focus-visible styles
- Keyboard navigable modal (Esc to close, focus trap)
- Good color contrast ratios (WCAG AA)
- Alt text on all images
- Error fallback images
- Screen reader friendly

## 🧪 Testing

### Responsive Testing
- Tested at: 360px (mobile), 768px (tablet), 1280px+ (desktop)
- No horizontal scroll on mobile
- Touch-friendly targets (min 44px)
- Hamburger menu works on mobile

### Theme Testing
- Light mode works correctly
- Dark mode works correctly
- Theme toggle functional
- Local storage persistence verified
- System preference respected

### Form Testing
- All validations work
- Error messages display correctly
- Submit button disables appropriately
- Duplicate registration prevented
- Success modal shows correctly

## 🚀 Deployment

### Vercel Deployment
1. Push code to GitHub
2. Import repository in Vercel
3. Vercel auto-detects Vite config
4. Deploy
5. SPA routing configured via vercel.json

### Netlify Deployment
1. Push code to GitHub
2. Import repository in Netlify
3. Add build command: `npm run build`
4. Add publish directory: `dist`
5. Add redirect rule for SPA routing

## 📈 Future Improvements

- [ ] Backend API integration
- [ ] User authentication
- [ ] Payment gateway integration
- [ ] Event calendar view
- [ ] Social sharing features
- [ ] Email notifications
- [ ] Admin dashboard
- [ ] Event creation for organizers
- [ ] Multi-language support
- [ ] Advanced filtering (date range, price range)
- [ ] Map integration for venues
- [ ] Reviews and ratings
- [ ] Waitlist for sold-out events

## 📝 License

This project is open source and available for educational purposes.

## 👨‍💻 Author

Built for the "K Explore – Web Designing" task

## 🙏 Acknowledgments

- Images from Unsplash
- Icons from Lucide React
- Design inspiration from modern UI trends
- React Router documentation
- Tailwind CSS documentation
- Framer Motion documentation

---

**Note**: This project demonstrates professional React development practices including component architecture, state management, custom hooks, context API, responsive design, accessibility, and modern UI/UX patterns.
