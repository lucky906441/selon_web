# Product Requirements Document (PRD)
# Mehak's Makeover Unisex Salon — Premium Website

---

> **Version:** 1.0  
> **Date:** July 30, 2026  
> **Stack:** HTML5 + CSS3 + Vanilla JavaScript + Firebase Web SDK  
> **Type:** Premium 3D Modern Salon Website with Admin Panel  

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Business Information](#2-business-information)
3. [Technology Stack](#3-technology-stack)
4. [Design System & Visual Identity](#4-design-system--visual-identity)
5. [Website Architecture](#5-website-architecture)
6. [Page-by-Page Specifications](#6-page-by-page-specifications)
7. [Online Booking System](#7-online-booking-system)
8. [Firebase Backend Integration](#8-firebase-backend-integration)
9. [Admin Panel (Mobile-First)](#9-admin-panel-mobile-first)
10. [3D & Animation Specifications](#10-3d--animation-specifications)
11. [Responsive Design Specifications](#11-responsive-design-specifications)
12. [Social Media & Map Integration](#12-social-media--map-integration)
13. [SEO & Performance](#13-seo--performance)
14. [Image Assets](#14-image-assets)
15. [File Structure](#15-file-structure)
16. [Deployment & Hosting](#16-deployment--hosting)

---

## 1. Project Overview

### 1.1 Vision
Build a **world-class, ultra-premium, 3D-animated salon website** for **Mehak's Makeover Unisex Salon** that delivers a luxury brand experience. The website must feel like a high-end international salon portal — with smooth 3D transitions, glassmorphism UI, cinematic hero sections, and a seamless online booking experience.

### 1.2 Goals
| Goal | Description |
|------|-------------|
| **Brand Elevation** | Position Mehak's Makeover as the premier salon in Brahmapur with a digital presence that rivals international brands |
| **Online Booking** | Enable customers to book appointments 24/7 with a premium, intuitive booking flow |
| **Admin Control** | Provide a mobile-friendly admin panel to manage all content, bookings, URLs, and salon operations |
| **Performance** | Achieve 90+ Lighthouse score on both mobile & desktop |
| **Responsiveness** | Pixel-perfect on all devices from 320px mobile to 4K desktop |

### 1.3 Target Audience
- Local customers in Brahmapur, Odisha looking for premium salon services
- Walk-in and appointment-based clients (men, women, unisex)
- Age group: 16–55 years

---

## 2. Business Information

| Field | Value |
|-------|-------|
| **Salon Name** | Mehak's Makeover |
| **Full Name** | Mehak's Makeover Unisex Salon |
| **Address** | 4th floor, Janata City Centre, Telephone Bhawan Rd, near KFC, Godavarish Nagar, Brahmapur, Odisha 760001 |
| **Contact Number** | 94386 62612 |
| **Type** | Unisex Salon |
| **Location City** | Brahmapur, Odisha, India |

---

## 3. Technology Stack

### 3.1 Frontend
| Technology | Purpose |
|------------|---------|
| **HTML5** | Semantic structure, SEO-optimized markup |
| **CSS3** | Custom properties, Grid, Flexbox, animations, glassmorphism, 3D transforms |
| **Vanilla JavaScript (ES6+)** | Interactivity, booking logic, Firebase integration, 3D effects |
| **Three.js** (CDN) | 3D background effects, particle systems, floating elements |
| **GSAP** (CDN) | Premium scroll-triggered animations, page transitions |
| **ScrollTrigger** (GSAP Plugin) | Scroll-based animation triggers |
| **Swiper.js** (CDN) | Premium touch-enabled image carousels/sliders |
| **Lottie Web** (CDN) | Micro-animations for icons and loading states |

### 3.2 Backend (Firebase Web SDK)
| Service | Purpose |
|---------|---------|
| **Firebase Authentication** | Admin login/authentication |
| **Cloud Firestore** | Bookings database, services catalog, content management |
| **Firebase Storage** | Image uploads from admin panel |
| **Firebase Hosting** | Website deployment |
| **Firebase Cloud Messaging** | Booking notifications (optional) |

### 3.3 Firebase Configuration Placeholder
```javascript
// Firebase Configuration — REPLACE WITH YOUR ACTUAL CONFIG
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_PROJECT.appspot.com",
  messagingSenderId: "YOUR_SENDER_ID",
  appId: "YOUR_APP_ID",
  measurementId: "YOUR_MEASUREMENT_ID"
};

// Initialize Firebase
firebase.initializeApp(firebaseConfig);
const db = firebase.firestore();
const auth = firebase.auth();
const storage = firebase.storage();
```

> **IMPORTANT:** Firebase config must be replaced with actual project credentials before deployment. All config keys above are placeholders.

---

## 4. Design System & Visual Identity

### 4.1 Color Palette

| Token | Hex | Usage |
|-------|-----|-------|
| `--primary` | `#D4A373` | Gold/warm accent — buttons, highlights, premium feel |
| `--primary-light` | `#E8C9A0` | Light gold — hover states, soft accents |
| `--primary-dark` | `#B8864E` | Deep gold — active states, borders |
| `--secondary` | `#1A1A2E` | Deep navy/black — primary backgrounds |
| `--secondary-light` | `#16213E` | Slightly lighter navy — card backgrounds |
| `--accent` | `#E94560` | Rose/pink accent — CTAs, alerts, highlights |
| `--accent-soft` | `#FF6B81` | Soft pink — hover on accent elements |
| `--bg-dark` | `#0F0F1A` | Darkest background — body, hero sections |
| `--bg-card` | `rgba(255, 255, 255, 0.05)` | Glassmorphism card backgrounds |
| `--bg-glass` | `rgba(255, 255, 255, 0.08)` | Glass effect panels |
| `--text-primary` | `#FFFFFF` | Primary text on dark backgrounds |
| `--text-secondary` | `#B8B8CC` | Muted text, descriptions |
| `--text-gold` | `#D4A373` | Highlighted text, labels |
| `--gradient-primary` | `linear-gradient(135deg, #D4A373 0%, #E94560 100%)` | Primary gradient for buttons/accents |
| `--gradient-hero` | `linear-gradient(180deg, #0F0F1A 0%, #1A1A2E 50%, #16213E 100%)` | Hero background gradient |
| `--shadow-gold` | `0 0 30px rgba(212, 163, 115, 0.3)` | Glow effect on premium elements |
| `--shadow-card` | `0 8px 32px rgba(0, 0, 0, 0.4)` | Card elevation shadow |

### 4.2 Typography

| Element | Font Family | Weight | Size (Desktop) | Size (Mobile) |
|---------|-------------|--------|----------------|---------------|
| **Headings (H1)** | 'Playfair Display', serif | 700 | 64px / 4rem | 36px / 2.25rem |
| **Headings (H2)** | 'Playfair Display', serif | 600 | 48px / 3rem | 28px / 1.75rem |
| **Headings (H3)** | 'Playfair Display', serif | 600 | 32px / 2rem | 22px / 1.375rem |
| **Body** | 'Inter', sans-serif | 400 | 16px / 1rem | 14px / 0.875rem |
| **Body Large** | 'Inter', sans-serif | 400 | 18px / 1.125rem | 16px / 1rem |
| **Button Text** | 'Inter', sans-serif | 600 | 16px / 1rem | 14px / 0.875rem |
| **Caption** | 'Inter', sans-serif | 300 | 14px / 0.875rem | 12px / 0.75rem |
| **Nav Links** | 'Inter', sans-serif | 500 | 15px / 0.9375rem | 16px / 1rem |
| **Price** | 'Outfit', sans-serif | 700 | 24px / 1.5rem | 20px / 1.25rem |

Google Fonts Import:
```
Playfair Display:wght@400;600;700
Inter:wght@300;400;500;600;700
Outfit:wght@400;500;600;700
```

### 4.3 Spacing System
| Token | Value |
|-------|-------|
| `--space-xs` | 4px |
| `--space-sm` | 8px |
| `--space-md` | 16px |
| `--space-lg` | 24px |
| `--space-xl` | 32px |
| `--space-2xl` | 48px |
| `--space-3xl` | 64px |
| `--space-4xl` | 96px |
| `--space-section` | 120px |

### 4.4 Border Radius
| Token | Value |
|-------|-------|
| `--radius-sm` | 8px |
| `--radius-md` | 12px |
| `--radius-lg` | 16px |
| `--radius-xl` | 24px |
| `--radius-full` | 9999px |

### 4.5 Glassmorphism Specifications
```css
.glass-card {
  background: rgba(255, 255, 255, 0.06);
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  border: 1px solid rgba(255, 255, 255, 0.1);
  border-radius: var(--radius-lg);
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
}

.glass-card-hover:hover {
  background: rgba(255, 255, 255, 0.1);
  border-color: rgba(212, 163, 115, 0.3);
  box-shadow: 0 8px 32px rgba(212, 163, 115, 0.15);
  transform: translateY(-4px);
}
```

---

## 5. Website Architecture

### 5.1 Site Map

```
Homepage (index.html)
├── Services Page (services.html)
├── Gallery Page (gallery.html)
├── Booking Page (booking.html)
│   ├── Step 1: Service Selection
│   ├── Step 2: Date & Time Picker
│   ├── Step 3: Personal Details
│   └── Step 4: Booking Confirmation
├── About Page (about.html)
├── Contact Page (contact.html)
└── Admin Panel (admin.html)
    ├── Dashboard
    ├── Manage Bookings
    ├── Manage Services
    ├── Manage Gallery
    ├── Manage Content/URLs
    └── Settings
```

### 5.2 Navigation Structure

**Main Navigation (Desktop - Sticky Glassmorphism Navbar)**
```
[Logo] | Home | Services | Gallery | Book Now | About | Contact | [Phone Icon + Number]
```

**Mobile Navigation (Hamburger → Full-screen Overlay)**
```
[Logo] .............. [Hamburger Icon]

── Full Screen Overlay ──
    Home
    Services
    Gallery
    Book Now (Highlighted)
    About
    Contact
    ─────────────
    Call Now
    Get Directions
    Follow Us (Social Icons)
```

---

## 6. Page-by-Page Specifications

### 6.1 Homepage (index.html)

#### Hero Section
| Element | Specification |
|---------|---------------|
| **Layout** | Full viewport height (100vh), centered content |
| **Background** | 3D particle animation (Three.js) with floating golden particles + subtle salon-themed 3D objects |
| **Overlay** | Dark gradient overlay for text readability |
| **Logo** | Main logo (animated entrance — scale + fade from top) |
| **Headline** | "Mehak's Makeover" — Playfair Display, 64px, gold gradient text, 3D text shadow |
| **Subheadline** | "Where Beauty Meets Perfection" — Inter, 20px, white with typewriter animation |
| **Tagline** | "Unisex Salon - Brahmapur" — subtle fade-in |
| **CTA Button** | "Book Your Appointment" — Large premium button with gradient background, glow effect, subtle pulse animation, gold border |
| **Scroll Indicator** | Animated bouncing chevron at bottom |
| **3D Effect** | Parallax mouse-tracking on background particles |

#### About Preview Section
| Element | Specification |
|---------|---------------|
| **Layout** | Two-column (image left, text right) — stacks on mobile |
| **Image** | Salon interior photo with 3D tilt effect on hover (perspective transform) |
| **Content** | Brief about text, years of experience, tagline |
| **Animation** | GSAP scroll-triggered slide-in from left (image) and right (text) |
| **CTA** | "Learn More About Us" link |

#### Services Highlight Section
| Element | Specification |
|---------|---------------|
| **Layout** | Section heading + horizontal scrolling cards (desktop: 4-column grid) |
| **Cards** | Glassmorphism cards with service icon (Lottie animation), name, brief description, starting price |
| **Card Hover** | 3D flip/tilt effect, gold border glow, scale up |
| **Categories** | Hair Styling, Makeup & Beauty, Skin Care, Bridal Packages, Men's Grooming, Nail Art |
| **Animation** | Staggered fade-up on scroll |
| **CTA** | "View All Services" button |

#### Gallery Preview Section
| Element | Specification |
|---------|---------------|
| **Layout** | Masonry grid (3 columns desktop, 2 tablet, 1 mobile) showing 6 best photos |
| **Images** | From provided photo URLs |
| **Hover Effect** | 3D perspective tilt + overlay with "View" icon |
| **Lightbox** | Click to open full-screen lightbox with swipe support |
| **Animation** | GSAP staggered reveal on scroll |
| **CTA** | "View Full Gallery" button |

#### Testimonials Section
| Element | Specification |
|---------|---------------|
| **Layout** | Swiper.js carousel with 3D coverflow effect |
| **Cards** | Glassmorphism testimonial cards with star rating, quote, customer name/photo |
| **Auto-play** | Yes, with pause on hover |
| **Data Source** | Firestore testimonials collection (admin-manageable) |

#### Booking CTA Banner
| Element | Specification |
|---------|---------------|
| **Layout** | Full-width gradient banner with 3D floating decorative elements |
| **Content** | "Ready for a Stunning Transformation?" heading |
| **Button** | Ultra-premium "BOOK NOW" button — Large (min 220px wide), gradient background (gold to rose), animated shimmer/shine effect across button surface, 3D depth shadow, icon (calendar), pulse glow animation, hover: scale 1.08 + intense glow |
| **Animation** | Continuous subtle floating animation on decorative elements |

#### Google Map Section
| Element | Specification |
|---------|---------------|
| **Layout** | Full-width embedded Google Map with glass overlay info card |
| **Map** | Google Maps iframe showing salon location |
| **Info Card** | Address, phone, working hours — glassmorphism card overlaid on map |
| **Buttons** | "Get Directions" (opens Google Maps), "Call Now" (tel: link) |

#### Footer
| Element | Specification |
|---------|---------------|
| **Layout** | 4-column layout (About, Quick Links, Services, Connect) |
| **Social Icons** | Instagram, Facebook — animated hover effects |
| **Contact Info** | Address, phone, email |
| **Copyright** | 2026 Mehak's Makeover. All Rights Reserved. |
| **Back to Top** | Floating button with smooth scroll |

---

### 6.2 Services Page (services.html)

#### Layout & Features
| Element | Specification |
|---------|---------------|
| **Hero** | Parallax header with "Our Services" title + decorative 3D elements |
| **Filter Tabs** | Category filter tabs (All, Hair, Makeup, Skin, Bridal, Men's, Nails) with smooth tab switching animation |
| **Service Cards** | Detailed glass cards with: service image, name, description, duration, price, "Book This Service" button |
| **Card Interaction** | 3D tilt on hover, expand on click for full details |
| **Pricing** | Displayed in Outfit font, gold color |
| **Book Button** | Each service card has a "Book Now" mini-button that pre-selects this service in booking flow |
| **Animation** | Filter transition with GSAP flip animation |

#### Service Categories & Items (Default Data)

**Hair Services**
| Service | Duration | Price Range |
|---------|----------|-------------|
| Haircut & Styling (Women) | 45-60 min | Rs.300 - Rs.1,500 |
| Haircut (Men) | 30 min | Rs.200 - Rs.500 |
| Hair Coloring | 90-120 min | Rs.1,500 - Rs.8,000 |
| Hair Spa & Treatment | 60-90 min | Rs.800 - Rs.3,000 |
| Keratin Treatment | 120-180 min | Rs.3,000 - Rs.12,000 |
| Hair Straightening/Smoothening | 120-180 min | Rs.2,500 - Rs.10,000 |
| Hair Extensions | 60-120 min | Rs.2,000 - Rs.8,000 |

**Makeup & Beauty**
| Service | Duration | Price Range |
|---------|----------|-------------|
| Party Makeup | 60-90 min | Rs.1,500 - Rs.5,000 |
| Bridal Makeup | 120-180 min | Rs.8,000 - Rs.25,000 |
| Engagement Makeup | 90-120 min | Rs.5,000 - Rs.15,000 |
| HD/Airbrush Makeup | 90-120 min | Rs.3,000 - Rs.10,000 |
| Eye Makeup | 30-45 min | Rs.500 - Rs.2,000 |

**Skin Care**
| Service | Duration | Price Range |
|---------|----------|-------------|
| Basic Facial | 45-60 min | Rs.500 - Rs.1,500 |
| Advanced Facial (Gold/Diamond) | 60-90 min | Rs.1,500 - Rs.5,000 |
| Chemical Peel | 30-45 min | Rs.1,000 - Rs.4,000 |
| De-Tan Treatment | 45-60 min | Rs.800 - Rs.2,500 |
| Anti-Aging Treatment | 60-90 min | Rs.2,000 - Rs.6,000 |
| Cleanup | 30-45 min | Rs.400 - Rs.1,000 |
| Threading & Waxing | 15-60 min | Rs.50 - Rs.2,000 |

**Bridal Packages**
| Service | Duration | Price Range |
|---------|----------|-------------|
| Complete Bridal Package | Full Day | Rs.15,000 - Rs.50,000 |
| Pre-Bridal Package (7 Sessions) | Multiple Days | Rs.10,000 - Rs.30,000 |
| Mehndi Day Package | 3-4 hrs | Rs.5,000 - Rs.12,000 |
| Reception Look | 2-3 hrs | Rs.5,000 - Rs.15,000 |

**Men's Grooming**
| Service | Duration | Price Range |
|---------|----------|-------------|
| Beard Styling & Trim | 20-30 min | Rs.150 - Rs.500 |
| Men's Facial | 45-60 min | Rs.500 - Rs.2,000 |
| Hair Color (Men) | 45-60 min | Rs.500 - Rs.2,000 |
| Head Massage | 20-30 min | Rs.200 - Rs.500 |
| Men's Grooming Package | 90-120 min | Rs.1,500 - Rs.4,000 |

**Nail Art & Care**
| Service | Duration | Price Range |
|---------|----------|-------------|
| Manicure | 30-45 min | Rs.300 - Rs.1,500 |
| Pedicure | 45-60 min | Rs.400 - Rs.2,000 |
| Nail Art | 30-60 min | Rs.500 - Rs.2,500 |
| Gel/Acrylic Nails | 60-90 min | Rs.1,000 - Rs.4,000 |

> **NOTE:** All services, prices, and durations are admin-editable from the admin panel. The above are default/suggested values. Admin can add, edit, delete, and reorder services.

---

### 6.3 Gallery Page (gallery.html)

| Element | Specification |
|---------|---------------|
| **Hero** | Parallax "Our Gallery" header |
| **Filter** | Category tabs: All, Hair Transformations, Makeup, Bridal, Salon Interior, Events |
| **Grid** | Masonry/Pinterest-style grid layout with varying card sizes |
| **Images** | All provided photo URLs (see Section 14) |
| **Hover** | 3D perspective tilt + dark overlay + zoom icon + category tag |
| **Lightbox** | Full-screen lightbox with swipe navigation, zoom, share buttons |
| **Animation** | GSAP staggered reveal, filter animations |
| **Admin** | Gallery fully manageable from admin panel (add/delete/reorder/categorize) |

---

### 6.4 Booking Page (booking.html)

> **IMPORTANT:** This is the most critical page. The booking experience must feel ultra-premium, smooth, and intuitive.

#### Premium Booking Button (Floating/Fixed)
This button appears on **EVERY page** (fixed position, bottom-right on desktop, bottom-center on mobile):

```
+-------------------------------------------+
|  BOOK YOUR APPOINTMENT                    |
|     [Calendar Icon]                        |
|     Animated shimmer effect                |
|     Gold gradient background               |
|     Subtle continuous pulse glow           |
|     3D depth/shadow                        |
|     Hover: Scale 1.1 + intense glow        |
+-------------------------------------------+
```

**Button Specifications:**
| Property | Value |
|----------|-------|
| **Position** | Fixed, bottom-right (desktop), bottom-center full-width (mobile) |
| **Size** | Min 200px x 56px (desktop), full-width with 16px padding (mobile) |
| **Background** | linear-gradient(135deg, #D4A373, #E94560) |
| **Border** | 2px solid rgba(255,255,255,0.2) |
| **Border Radius** | 28px (desktop), 16px (mobile) |
| **Text** | "BOOK APPOINTMENT" or "Book Now", Inter 600, 16px, white |
| **Icon** | Calendar/sparkle SVG icon |
| **Shadow** | 0 4px 30px rgba(212, 163, 115, 0.5) |
| **Animation** | CSS shimmer keyframe (moving gradient highlight), subtle pulse (box-shadow expand/contract) |
| **Hover** | transform: scale(1.08); box-shadow: 0 6px 40px rgba(212, 163, 115, 0.7) |
| **Z-index** | 9999 |
| **Click Action** | Navigates to booking page or opens booking modal |

#### Booking Flow (Multi-Step Wizard)

**Step 1: Service Selection**
| Element | Specification |
|---------|---------------|
| **Layout** | Category tabs at top, service cards below |
| **Cards** | Selectable cards with radio/checkbox behavior |
| **Multi-select** | Users can book multiple services |
| **Info** | Each card shows: service name, duration, price |
| **Animation** | Selected card gets gold border glow + checkmark |
| **Progress** | Step indicator bar at top (Step 1 of 4) |

**Step 2: Date & Time Selection**
| Element | Specification |
|---------|---------------|
| **Calendar** | Custom-styled premium calendar (current + next month) |
| **Date Selection** | Selectable dates with unavailable dates grayed out |
| **Time Slots** | Grid of available time slots (30-min intervals, 9 AM - 8 PM) |
| **Time Display** | Glass cards for each slot, selected = gold highlight |
| **Data** | Available slots from Firestore (admin sets availability) |

**Step 3: Personal Details**
| Element | Specification |
|---------|---------------|
| **Form Fields** | Full Name*, Phone Number*, Email (optional), Gender (Male/Female/Other), Notes/Special Requests |
| **Styling** | Premium floating label inputs with gold focus borders |
| **Validation** | Real-time validation with smooth error animations |
| **Phone** | Auto-format Indian phone numbers, validation |

**Step 4: Booking Summary & Confirmation**
| Element | Specification |
|---------|---------------|
| **Summary Card** | Glass card showing: all selected services, total duration, total price, date & time, customer details |
| **Terms** | Checkbox for salon terms/cancellation policy |
| **Confirm Button** | Large premium "Confirm Booking" button with loading state |
| **Success** | Animated success screen with confetti/sparkle animation, booking ID, "Add to Calendar" option |
| **Data** | Booking saved to Firestore bookings collection |

#### Booking Data Schema (Firestore)
```javascript
// Collection: bookings
{
  bookingId: "auto-generated",
  customerName: "String",
  customerPhone: "String",
  customerEmail: "String (optional)",
  customerGender: "male | female | other",
  services: [
    {
      serviceId: "String",
      serviceName: "String",
      price: Number,
      duration: Number // in minutes
    }
  ],
  totalPrice: Number,
  totalDuration: Number,
  appointmentDate: Timestamp,
  appointmentTime: "String (HH:MM)",
  notes: "String",
  status: "pending | confirmed | completed | cancelled | no-show",
  createdAt: Timestamp,
  updatedAt: Timestamp
}
```

---

### 6.5 About Page (about.html)

| Element | Specification |
|---------|---------------|
| **Hero** | Parallax header with salon logo and "Our Story" |
| **Story Section** | Two-column layout with salon photos and narrative text |
| **Team Section** | Team member cards with 3D flip effect (photo front, details back) |
| **Stats Counter** | Animated number counters: Years of Experience, Happy Clients, Services, Awards |
| **Values** | Glassmorphism cards with salon values/philosophy |
| **Timeline** | Visual timeline of salon milestones (optional) |

---

### 6.6 Contact Page (contact.html)

| Element | Specification |
|---------|---------------|
| **Hero** | "Get in Touch" header |
| **Contact Cards** | Glass cards for: Phone, Email, Address, Working Hours |
| **Contact Form** | Name, Phone, Email, Subject, Message — saves to Firestore |
| **Google Map** | Full-width embedded map with custom styled marker |
| **Social Links** | Large social media buttons (Instagram, Facebook) |
| **Quick Actions** | "Call Now", "WhatsApp", "Get Directions" buttons |

---

## 7. Online Booking System

### 7.1 Features Checklist

- Multi-step booking wizard (4 steps)
- Service category filtering
- Multi-service selection
- Custom premium date picker
- Time slot selection with availability
- Real-time form validation
- Booking summary with price calculation
- Firestore database storage
- Booking confirmation with animation
- Unique booking ID generation
- Booking status tracking (pending -> confirmed -> completed)
- Admin notification for new bookings
- Customer-facing booking reference
- Cancellation policy display
- Working hours enforcement
- Premium floating "Book Now" button on all pages

### 7.2 Booking Button Behavior

| Page | Button Style | Action |
|------|-------------|--------|
| **Homepage** | Hero CTA + Floating button | Navigate to booking page |
| **Services** | Per-service "Book" + Floating button | Pre-select service -> booking page |
| **Gallery** | Floating button only | Navigate to booking page |
| **About** | Floating button only | Navigate to booking page |
| **Contact** | Floating button only | Navigate to booking page |
| **Booking** | Floating button hidden (already on page) | — |

---

## 8. Firebase Backend Integration

### 8.1 Firestore Collections

```
firestore/
├── bookings/           # All customer bookings
├── services/           # All salon services (admin-managed)
│   └── {serviceId}/
│       ├── name
│       ├── category
│       ├── description
│       ├── duration
│       ├── priceMin
│       ├── priceMax
│       ├── image
│       ├── isActive
│       └── order
├── gallery/            # Gallery images (admin-managed)
│   └── {imageId}/
│       ├── url
│       ├── category
│       ├── caption
│       ├── order
│       └── isActive
├── testimonials/       # Customer reviews (admin-managed)
│   └── {testimonialId}/
│       ├── name
│       ├── rating
│       ├── text
│       ├── photo
│       └── date
├── siteConfig/         # Website configuration (admin-managed)
│   └── general/
│       ├── salonName
│       ├── salonFullName
│       ├── address
│       ├── phone
│       ├── email
│       ├── workingHours
│       ├── instagramUrl
│       ├── facebookUrl
│       ├── googleMapUrl
│       ├── googleMapEmbedUrl
│       ├── aboutText
│       ├── heroTagline
│       ├── heroSubtitle
│       └── logoUrl
├── availability/       # Time slot availability (admin-managed)
│   └── {date}/
│       ├── slots: [{time, isAvailable}]
│       └── isClosed
└── contactMessages/    # Contact form submissions
    └── {messageId}/
        ├── name
        ├── phone
        ├── email
        ├── subject
        ├── message
        ├── isRead
        └── createdAt
```

### 8.2 Firebase Security Rules (Recommended)
```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    // Public read access for site content
    match /services/{doc} { allow read: if true; }
    match /gallery/{doc} { allow read: if true; }
    match /testimonials/{doc} { allow read: if true; }
    match /siteConfig/{doc} { allow read: if true; }
    match /availability/{doc} { allow read: if true; }
    
    // Public write for bookings and contact messages
    match /bookings/{doc} { 
      allow create: if true;
      allow read, update, delete: if request.auth != null;
    }
    match /contactMessages/{doc} {
      allow create: if true;
      allow read, update, delete: if request.auth != null;
    }
    
    // Admin-only write for all content
    match /{document=**} {
      allow write: if request.auth != null;
    }
  }
}
```

---

## 9. Admin Panel (Mobile-First)

### 9.1 Overview
The admin panel is a **separate HTML page** (admin.html) designed **mobile-first** for managing the entire website from a phone. It must be responsive, touch-friendly, and fully functional on mobile screens.

### 9.2 Admin Authentication
| Feature | Specification |
|---------|---------------|
| **Login** | Email + Password via Firebase Auth |
| **Security** | Protected route — redirect to login if not authenticated |
| **Session** | Persistent login with Firebase auth state observer |
| **Logout** | Logout button in admin sidebar/header |

### 9.3 Admin Dashboard

```
+----------------------------------+
|  Mehak's Admin Panel             |
|  =============================== |
|                                  |
|  Dashboard                       |
|  +--------+  +--------+         |
|  | Today  |  | Total  |         |
|  |Bookings|  |Bookings|         |
|  |   5    |  |  247   |         |
|  +--------+  +--------+         |
|  +--------+  +--------+         |
|  |Pending |  |Messages|         |
|  |   3    |  |   12   |         |
|  +--------+  +--------+         |
|                                  |
|  Recent Bookings                 |
|  +-- Priya S. | Bridal | Today   |
|  +-- Rahul K. | Haircut | Today  |
|  +-- Neha M. | Facial | Tomorrow |
|                                  |
|  ------------------------------  |
|  [Bookings] [Services]          |
|  [Gallery]  [Settings]          |
|  [Messages] [URLs/Social]       |
+----------------------------------+
```

### 9.4 Admin Sections

#### 9.4.1 Booking Management
| Feature | Description |
|---------|-------------|
| **View All** | List all bookings with filters (date, status, search) |
| **Status Update** | Change booking status: Pending -> Confirmed -> Completed / Cancelled / No-show |
| **Details View** | Full booking details modal |
| **Calendar View** | Visual calendar showing bookings per day |
| **Quick Actions** | Call customer, WhatsApp customer, delete booking |
| **Notifications** | Badge count for pending bookings |

#### 9.4.2 Service Management
| Feature | Description |
|---------|-------------|
| **Add Service** | Form: Name, Category, Description, Duration, Price Min/Max, Image URL, Active/Inactive |
| **Edit Service** | Inline editing or modal form |
| **Delete Service** | With confirmation dialog |
| **Reorder** | Drag-and-drop (touch-friendly) service ordering |
| **Toggle Active** | Enable/disable services without deleting |
| **Categories** | Manage service categories |

#### 9.4.3 Gallery Management
| Feature | Description |
|---------|-------------|
| **Add Image** | Upload image (Firebase Storage) or paste URL |
| **Edit** | Change category, caption, order |
| **Delete** | With confirmation |
| **Categories** | Manage gallery categories |
| **Reorder** | Drag-and-drop reordering |

#### 9.4.4 Content & URL Management
| Feature | Description |
|---------|-------------|
| **Salon Info** | Edit salon name, address, phone, email |
| **Working Hours** | Set opening/closing hours per day |
| **Social URLs** | Edit Instagram URL, Facebook URL |
| **Google Map** | Edit map embed URL and directions URL |
| **Hero Content** | Edit hero section tagline, subtitle |
| **About Content** | Edit about page text |
| **Logo** | Change logo URL |

> **IMPORTANT:** All URLs (Instagram, Facebook, Google Map) must be editable from admin panel. Any change in admin panel should reflect immediately on the main website.

#### 9.4.5 Contact Messages
| Feature | Description |
|---------|-------------|
| **View All** | List all contact form submissions |
| **Mark Read/Unread** | Toggle read status |
| **Reply** | Quick reply via WhatsApp/Phone |
| **Delete** | Remove messages |

#### 9.4.6 Availability Management
| Feature | Description |
|---------|-------------|
| **Weekly Schedule** | Set default weekly working hours |
| **Block Dates** | Mark specific dates as closed/unavailable |
| **Custom Slots** | Override time slots for specific dates |
| **Holiday Management** | Set holidays/off days |

### 9.5 Admin Panel Design Specifications

| Property | Specification |
|----------|---------------|
| **Theme** | Dark theme matching main site (with option for light mode) |
| **Layout** | Bottom tab navigation on mobile, sidebar on desktop |
| **Touch Targets** | Minimum 44px x 44px for all interactive elements |
| **Font Size** | Minimum 14px for body text, 16px for inputs |
| **Loading States** | Skeleton screens for data loading |
| **Offline** | Graceful offline handling with error messages |
| **Pull to Refresh** | Pull-down-to-refresh on booking list (mobile) |
| **Swipe Actions** | Swipe on booking cards for quick actions (mobile) |
| **Toast Notifications** | Success/error notifications at bottom of screen |

---

## 10. 3D & Animation Specifications

### 10.1 Three.js 3D Elements

| Element | Location | Description |
|---------|----------|-------------|
| **Particle Background** | Hero section | Floating golden particles that respond to mouse/touch movement, creating a luxury ambiance |
| **3D Floating Objects** | Hero section | Subtle floating salon-themed shapes (scissors silhouette, mirror, comb) with gentle rotation |
| **3D Text** | Hero heading | Slight 3D extrusion effect on the salon name |
| **Parallax Depth** | Throughout | Multi-layer parallax scrolling creating depth |

### 10.2 GSAP Animations

| Animation | Trigger | Description |
|-----------|---------|-------------|
| **Hero Entrance** | Page load | Staggered reveal: logo -> heading -> subtitle -> CTA -> scroll indicator |
| **Scroll Reveal** | Scroll into view | Elements fade up + slide with stagger (0.1s between elements) |
| **Counter Animation** | Scroll into view | Numbers count up from 0 to target value |
| **Card Hover Tilt** | Mouse move on card | 3D perspective tilt following mouse position (max 10deg) |
| **Page Transition** | Navigation click | Smooth fade/slide transition between pages |
| **Gallery Filter** | Filter click | GSAP Flip animation for grid rearrangement |
| **Booking Steps** | Step change | Slide left/right transition between booking steps |
| **Navbar Hide/Show** | Scroll direction | Slide up to hide on scroll down, reveal on scroll up |
| **Image Parallax** | Scroll | Images move at different speeds creating depth |
| **Text Split** | Scroll into view | Letter-by-letter or word-by-word reveal for headings |

### 10.3 CSS Animations

| Animation | Property | Description |
|-----------|----------|-------------|
| **Button Shimmer** | background-position | Moving gradient highlight across button surface |
| **Pulse Glow** | box-shadow | Expanding/contracting glow on booking button |
| **Float** | transform: translateY() | Subtle up/down floating for decorative elements |
| **Gradient Shift** | background-position | Slowly moving gradient backgrounds |
| **Skeleton Loading** | background-position | Loading placeholder shimmer effect |
| **Fade In Up** | opacity, transform | Basic scroll reveal animation (CSS-only fallback) |
| **Rotate** | transform: rotate() | Slow rotation for decorative circles/shapes |

### 10.4 Micro-Interactions

| Interaction | Element | Effect |
|-------------|---------|--------|
| **Button Press** | All buttons | Scale down 0.95 + slight darken on press |
| **Input Focus** | Form inputs | Gold border animation, label float up |
| **Checkbox** | Booking checkboxes | Animated checkmark with bounce |
| **Toggle Switch** | Admin toggles | Smooth slide with color transition |
| **Card Select** | Booking service cards | Border glow + checkmark + subtle bounce |
| **Success** | Booking confirmation | Confetti/sparkle particle burst |
| **Error** | Form validation | Shake animation + red highlight |
| **Loading** | Data fetching | Pulsing logo or spinning gradient circle |

---

## 11. Responsive Design Specifications

### 11.1 Breakpoints

| Breakpoint | Name | Width Range | Columns |
|------------|------|-------------|---------|
| **xs** | Mobile Small | 320px – 374px | 1 |
| **sm** | Mobile | 375px – 575px | 1 |
| **md** | Tablet Portrait | 576px – 767px | 2 |
| **lg** | Tablet Landscape | 768px – 991px | 2-3 |
| **xl** | Desktop | 992px – 1199px | 3-4 |
| **2xl** | Large Desktop | 1200px – 1399px | 4 |
| **3xl** | Extra Large | 1400px+ | 4-6 |

### 11.2 Mobile-Specific Adaptations

| Element | Desktop | Mobile |
|---------|---------|--------|
| **Navigation** | Horizontal nav bar | Hamburger -> full-screen overlay menu |
| **Hero Font** | 64px | 36px |
| **Service Cards** | 4-column grid | Single column, horizontal scroll option |
| **Gallery Grid** | 3-column masonry | 1-2 column, vertical stack |
| **Booking Wizard** | Side-by-side layout | Full-width stacked layout |
| **Footer** | 4-column | Single column, accordion sections |
| **Booking Button** | Fixed bottom-right (200px) | Fixed bottom, full-width |
| **Admin Panel** | Sidebar navigation | Bottom tab navigation |
| **Map** | 60% width + info card | Full-width stacked |
| **Testimonials** | 3 visible slides | 1 visible slide |

### 11.3 Touch Optimization
- All interactive elements: minimum 44px x 44px touch target
- Swipe gestures for carousels, gallery lightbox, admin booking cards
- Pull-to-refresh on admin booking list
- No hover-only interactions (all have tap equivalents)
- Smooth momentum scrolling with -webkit-overflow-scrolling: touch

---

## 12. Social Media & Map Integration

### 12.1 Social Media Links (Admin-Controllable)

| Platform | Integration | Admin Control |
|----------|-------------|---------------|
| **Instagram** | Profile link button, embed feed widget (optional), icon in footer/nav | URL editable from admin panel |
| **Facebook** | Page link button, icon in footer/nav | URL editable from admin panel |
| **WhatsApp** | Quick chat button (wa.me link with pre-filled message) | Number editable from admin panel |
| **Google Maps** | Embedded map iframe, "Get Directions" button | Embed URL and directions URL editable from admin |

### 12.2 Social Media Display
- Footer: Icon row (Instagram, Facebook, WhatsApp)
- Contact page: Large social button cards
- Mobile nav overlay: Social icons section
- Floating WhatsApp chat button (bottom-left, optional)

### 12.3 Google Map Integration
```html
<!-- Google Map Embed (URL from Firestore siteConfig) -->
<iframe 
  src="{googleMapEmbedUrl from admin}"
  width="100%" 
  height="450" 
  style="border:0;" 
  allowfullscreen="" 
  loading="lazy" 
  referrerpolicy="no-referrer-when-downgrade">
</iframe>
```

The map embed URL and directions link are stored in Firestore siteConfig/general and fully editable from the admin panel.

---

## 13. SEO & Performance

### 13.1 SEO Requirements

| Element | Implementation |
|---------|----------------|
| **Title Tag** | "Mehak's Makeover Unisex Salon - Best Salon in Brahmapur, Odisha" |
| **Meta Description** | "Premium unisex salon in Brahmapur offering haircuts, makeup, bridal packages, skin care & more. Book your appointment online at Mehak's Makeover." |
| **Open Graph Tags** | Full OG tags for social sharing (title, description, image, URL) |
| **Schema Markup** | LocalBusiness structured data (JSON-LD) with salon details |
| **Canonical URLs** | Proper canonical tags on all pages |
| **Heading Hierarchy** | Single H1 per page, proper H2-H6 nesting |
| **Alt Tags** | Descriptive alt text on all images |
| **Semantic HTML** | header, nav, main, section, article, footer |
| **Sitemap** | XML sitemap for search engines |
| **Robots.txt** | Proper robots.txt with admin panel excluded |

### 13.2 Performance Targets

| Metric | Target |
|--------|--------|
| **Lighthouse Performance** | 90+ (mobile & desktop) |
| **First Contentful Paint** | < 1.5s |
| **Largest Contentful Paint** | < 2.5s |
| **Cumulative Layout Shift** | < 0.1 |
| **Time to Interactive** | < 3.5s |

### 13.3 Performance Optimizations
- Lazy loading for images (loading="lazy")
- WebP image format (already provided via wsrv.nl)
- CSS/JS minification for production
- Critical CSS inlining for above-the-fold content
- Deferred loading for Three.js, GSAP (non-critical)
- Font display swap for Google Fonts
- Preconnect to CDNs and Firebase
- Image dimension attributes to prevent layout shift
- Intersection Observer for scroll animations (fallback for GSAP)

---

## 14. Image Assets

### 14.1 Logo Images

| ID | Type | URL |
|----|------|-----|
| logo-main | Main Logo | https://wsrv.nl/?url=https://i.ibb.co/Tx15Hqrz/mehaks-makeover-main-logo.png&w=1080&q=95&output=webp&we |
| logo-secondary | Secondary Logo | https://wsrv.nl/?url=https://i.ibb.co/Fq6RTBLs/mehaks-makeover-second-logo.png&w=1080&q=95&output=webp&we |

### 14.2 Salon Photos

| ID | URL |
|----|-----|
| photo-1 | https://wsrv.nl/?url=https://i.ibb.co/xqXPHrqH/mehaks-makeover-photo-1.jpg&w=1080&q=95&output=webp&we |
| photo-2 | https://wsrv.nl/?url=https://i.ibb.co/j9VWbyhw/mehaks-makeover-photo-2.jpg&w=1080&q=95&output=webp&we |
| photo-3 | https://wsrv.nl/?url=https://i.ibb.co/gbCY1NCW/mehaks-makeover-photo-3.jpg&w=1080&q=95&output=webp&we |
| photo-4 | https://wsrv.nl/?url=https://i.ibb.co/ynMJZphw/mehaks-makeover-photo-4.jpg&w=1080&q=95&output=webp&we |
| photo-5 | https://wsrv.nl/?url=https://i.ibb.co/CXMD2qq/mehaks-makeover-photo-5.jpg&w=1080&q=95&output=webp&we |
| photo-6 | https://wsrv.nl/?url=https://i.ibb.co/Z1Vv42y7/mehaks-makeover-photo-6.jpg&w=1080&q=95&output=webp&we |
| photo-7 | https://wsrv.nl/?url=https://i.ibb.co/mFd1Kx6R/mehaks-makeover-photo-7.jpg&w=1080&q=95&output=webp&we |
| photo-8 | https://wsrv.nl/?url=https://i.ibb.co/JRtX3RjD/mehaks-makeover-photo-8.jpg&w=1080&q=95&output=webp&we |
| photo-10 | https://wsrv.nl/?url=https://i.ibb.co/SGdGFfM/mehaks-makeover-photo-10.jpg&w=1080&q=95&output=webp&we |
| photo-11 | https://wsrv.nl/?url=https://i.ibb.co/VcxwCdTr/mehaks-makeover-photo-11.webp&w=1080&q=95&output=webp&we |
| photo-12 | https://wsrv.nl/?url=https://i.ibb.co/SXZj1X8d/mehaks-makeover-photo-12.webp&w=1080&q=95&output=webp&we |
| photo-13 | https://wsrv.nl/?url=https://i.ibb.co/FkGdpRVP/mehaks-makeover-photo-13.webp&w=1080&q=95&output=webp&we |
| photo-14 | https://wsrv.nl/?url=https://i.ibb.co/wNpgnchz/mehaks-makeover-photo-14.webp&w=1080&q=95&output=webp&we |
| photo-15 | https://wsrv.nl/?url=https://i.ibb.co/99tZKW9M/mehaks-makeover-photo-15.jpg&w=1080&q=95&output=webp&we |
| photo-16 | https://wsrv.nl/?url=https://i.ibb.co/YB7BYnmL/mehaks-makeover-photo-16.jpg&w=1080&q=95&output=webp&we |
| photo-17 | https://wsrv.nl/?url=https://i.ibb.co/mC830rg8/mehaks-makeover-photo-17.jpg&w=1080&q=95&output=webp&we |
| photo-18 | https://wsrv.nl/?url=https://i.ibb.co/cSpdvRCG/mehaks-makeover-photo-18.jpg&w=1080&q=95&output=webp&we |
| photo-19 | https://wsrv.nl/?url=https://i.ibb.co/hJTxC8Xx/mehaks-makeover-photo-19.jpg&w=1080&q=95&output=webp&we |
| photo-20 | https://wsrv.nl/?url=https://i.ibb.co/HDcskCNR/mehaks-makeover-photo-20.jpg&w=1080&q=95&output=webp&we |
| photo-21 | https://wsrv.nl/?url=https://i.ibb.co/2773YxyY/mehaks-makeover-photo-21.jpg&w=1080&q=95&output=webp&we |

> **NOTE:** All image URLs use the wsrv.nl image proxy for optimized WebP delivery at 1080px width, 95% quality. The &we parameter enables WebP error handling fallback.

---

## 15. File Structure

```
mehaks-makeover-website/
│
├── index.html                  # Homepage
├── services.html               # Services page
├── gallery.html                # Gallery page
├── booking.html                # Booking page
├── about.html                  # About page
├── contact.html                # Contact page
├── admin.html                  # Admin Panel (mobile-first)
│
├── css/
│   ├── variables.css           # CSS custom properties (design tokens)
│   ├── reset.css               # CSS reset/normalize
│   ├── base.css                # Base typography, body styles
│   ├── components.css          # Reusable components (cards, buttons, inputs)
│   ├── layout.css              # Grid systems, containers, responsive layouts
│   ├── animations.css          # All CSS keyframe animations
│   ├── hero.css                # Hero section styles
│   ├── navbar.css              # Navigation styles
│   ├── footer.css              # Footer styles
│   ├── booking.css             # Booking page specific styles
│   ├── gallery.css             # Gallery page specific styles
│   ├── admin.css               # Admin panel styles
│   └── responsive.css          # All media queries consolidated
│
├── js/
│   ├── config.js               # Firebase config + app constants (PLACEHOLDER)
│   ├── firebase-init.js        # Firebase initialization
│   ├── auth.js                 # Firebase authentication (admin)
│   ├── db.js                   # Firestore CRUD operations
│   ├── app.js                  # Main app initialization + common functionality
│   ├── navbar.js               # Navigation behavior (scroll, mobile menu)
│   ├── hero.js                 # Hero section 3D effects (Three.js)
│   ├── animations.js           # GSAP animations initialization
│   ├── booking.js              # Booking wizard logic
│   ├── gallery.js              # Gallery filtering + lightbox
│   ├── services.js             # Services page filtering
│   ├── contact.js              # Contact form handling
│   ├── admin/
│   │   ├── admin-app.js        # Admin panel main app
│   │   ├── admin-auth.js       # Admin login/logout
│   │   ├── admin-dashboard.js  # Dashboard stats & charts
│   │   ├── admin-bookings.js   # Booking management
│   │   ├── admin-services.js   # Service management
│   │   ├── admin-gallery.js    # Gallery management
│   │   ├── admin-content.js    # Content & URL management
│   │   ├── admin-messages.js   # Contact message management
│   │   └── admin-availability.js # Availability management
│   └── utils/
│       ├── helpers.js          # Utility functions
│       ├── validators.js       # Form validation functions
│       └── date-utils.js       # Date/time utility functions
│
├── assets/
│   ├── icons/                  # SVG icons
│   ├── lottie/                 # Lottie animation JSON files
│   └── favicon/                # Favicon files (multiple sizes)
│
├── sitemap.xml                 # XML Sitemap
├── robots.txt                  # Robots.txt
├── manifest.json               # Web App Manifest (PWA-ready)
├── firebase.json               # Firebase hosting config
├── firestore.rules             # Firestore security rules
├── .firebaserc                 # Firebase project settings
└── README.md                   # Project documentation
```

---

## 16. Deployment & Hosting

### 16.1 Firebase Hosting Setup
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login to Firebase
firebase login

# Initialize Firebase project
firebase init

# Select: Hosting, Firestore, Storage, Authentication

# Deploy
firebase deploy
```

### 16.2 Pre-Deployment Checklist

- Replace Firebase config placeholders with actual values
- Set up Firebase Authentication (Email/Password for admin)
- Create initial admin user in Firebase Console
- Initialize Firestore collections with default service data
- Upload default gallery images
- Set up siteConfig document with all salon information
- Configure Instagram URL in admin panel
- Configure Facebook URL in admin panel
- Configure Google Map embed URL in admin panel
- Set working hours/availability
- Test booking flow end-to-end
- Test admin panel on mobile device
- Run Lighthouse audit
- Test all responsive breakpoints
- Verify all social links work
- Set up Firestore security rules
- Set up Firebase Storage security rules

### 16.3 Post-Deployment
- Submit sitemap to Google Search Console
- Set up custom domain (if applicable)
- Monitor Firebase usage/billing
- Train salon staff on admin panel usage

---

## Appendix A: CDN Links

```html
<!-- Google Fonts -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Outfit:wght@400;500;600;700&family=Playfair+Display:wght@400;600;700&display=swap" rel="stylesheet">

<!-- Three.js -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>

<!-- GSAP + ScrollTrigger -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>

<!-- Swiper.js -->
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.css">
<script src="https://cdn.jsdelivr.net/npm/swiper@10/swiper-bundle.min.js"></script>

<!-- Firebase Web SDK (Compat v10+) -->
<script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-auth-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-firestore-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/10.7.0/firebase-storage-compat.js"></script>

<!-- Lottie Web -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/lottie-web/5.12.2/lottie.min.js"></script>
```

---

## Appendix B: JSON-LD Structured Data

```json
{
  "@context": "https://schema.org",
  "@type": "BeautySalon",
  "name": "Mehak's Makeover Unisex Salon",
  "image": "https://wsrv.nl/?url=https://i.ibb.co/Tx15Hqrz/mehaks-makeover-main-logo.png&w=1080&q=95&output=webp&we",
  "telephone": "+91-94386-62612",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "4th floor, Janata City Centre, Telephone Bhawan Rd, near KFC, Godavarish Nagar",
    "addressLocality": "Brahmapur",
    "addressRegion": "Odisha",
    "postalCode": "760001",
    "addressCountry": "IN"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "19.3150",
    "longitude": "84.7941"
  },
  "url": "https://mehaksmakeover.com",
  "priceRange": "$$",
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday","Tuesday","Wednesday","Thursday","Friday","Saturday","Sunday"],
      "opens": "09:00",
      "closes": "20:00"
    }
  ],
  "sameAs": [],
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Salon Services",
    "itemListElement": [
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Hair Styling"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Makeup & Beauty"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Skin Care"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Bridal Packages"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Men's Grooming"}},
      {"@type": "Offer", "itemOffered": {"@type": "Service", "name": "Nail Art"}}
    ]
  }
}
```

---

## Appendix C: Quick Reference — Admin Panel Features

| # | Feature | Admin Action | Reflects On |
|---|---------|-------------|-------------|
| 1 | Salon Name | Edit | All pages (header, footer, meta tags) |
| 2 | Address | Edit | Contact page, footer, map info card |
| 3 | Phone Number | Edit | All pages (nav, footer, contact) |
| 4 | Instagram URL | Edit | Footer, contact page, mobile nav |
| 5 | Facebook URL | Edit | Footer, contact page, mobile nav |
| 6 | Google Map URL | Edit | Contact page, homepage map section |
| 7 | Logo | Upload/Change URL | All pages (navbar, footer, hero) |
| 8 | Hero Content | Edit tagline/subtitle | Homepage hero section |
| 9 | About Content | Edit text | About page, homepage about preview |
| 10 | Services | Add/Edit/Delete/Reorder | Services page, booking wizard, homepage |
| 11 | Gallery Images | Add/Delete/Categorize/Reorder | Gallery page, homepage gallery preview |
| 12 | Testimonials | Add/Edit/Delete | Homepage testimonials section |
| 13 | Bookings | View/Update Status/Delete | Admin only |
| 14 | Contact Messages | View/Mark Read/Delete | Admin only |
| 15 | Working Hours | Set per-day hours | Booking time slots, contact page |
| 16 | Availability | Block dates/custom slots | Booking calendar |
| 17 | WhatsApp Number | Edit | Floating WhatsApp button, contact page |

---

> **TIP:** This PRD is designed to be a complete A-to-Z blueprint. A developer following this document should be able to build the entire website without needing additional specifications. Every feature, design token, animation, database schema, and admin panel requirement is documented.

---

**End of PRD**  
*Mehak's Makeover Unisex Salon — Premium Website PRD v1.0*
