# 🍳 Gourmate — AI-Powered Cooking & Bar Assistant

Gourmate is a full-stack AI cooking assistant built with **Streamlit** and powered by **GPT-4o**, **Google Gemini**, and custom **ML models**. It handles everything from smart pantry management and personalised recipe generation to nutrition tracking, family meal planning, cocktail mixing, and budget control — all backed by a **Supabase PostgreSQL** database with Row-Level Security.

---

## 🎭 Three Modes, One App

| Mode | Description |
|------|-------------|
| **👤 Individual** | Personal recipes, nutrition tracking, quick meals, photo-based calorie logging |
| **👨‍👩‍👧‍👦 Family** | Scaled recipes, family member profiles, shared pantry, chore assignment, group meal plans, leftover wizard, budget planner |
| **🍸 Bartender** | Cocktail & mocktail generator, bar inventory management, party planner, drink pairings |

Each mode has its own navigation, pages, and AI prompts tailored to the context.

---

## ✨ Features

### 🥕 Smart Pantry
- Add ingredients via **manual entry**, **quick-add**, **barcode scanning**, or **photo upload**
- AI-powered **receipt & shelf photo extraction** (GPT-4o Vision) — snap a picture and ingredients are added automatically
- Automatic **ingredient categorisation** (produce, dairy, protein, grains, spices, etc.)
- Expiry date tracking to reduce food waste
- Shared family pantry in Family Mode

### 🍲 AI Recipe Generation
- Context-aware recipes based on **time of day, season, weather, location, and your profile**
- Respects **dietary restrictions, allergies, and health goals** for every household member
- Choose cuisine, serving count, cooking type (cooking/baking), and meal mode (meals/dessert)
- Recipes ranked by **ingredient match %** — highlights what you already have vs. what's missing
- One-click **meal tracking** from any generated recipe
- **Surprise Me** — random recipe generation based on your profile and pantry

### ⚡ Quick Recipes
- Timezone-aware **meal type detection** (Breakfast / Lunch / Dinner based on your local time)
- Instant recipe suggestions based on time of day, meal history, and current pantry
- No settings to fiddle with — just tap and cook

### 📸 Photo → Calories
- Upload a food photo and GPT Vision identifies the dish
- Estimates **calories, macros (protein/carbs/fat), and micronutrients**
- One-click logging to your meal tracker
- Works for any cuisine or home-cooked meal

### 📊 Meal Tracker
- Log meals with full nutritional breakdown
- Daily progress bars against personalised calorie/macro goals
- Auto-calculated **BMR/TDEE** based on your profile (age, weight, height, activity level)
- Weekly and monthly **trend charts** (Plotly interactive visualisations)
- Water intake tracking

### 🥗 Nutrition Dashboard
- Deep-dive macro split visualisation (pie charts, bar charts)
- Micronutrient tracking (vitamins, minerals, fibre)
- Custom daily targets for protein, carbs, fat, fibre, and more
- Historical nutrition trends over time
- Nutrition goal setting and progress tracking

### 🧠 AI Insights (ML-Powered)
- **User Preference Engine** — learns your food preferences over time using K-Means clustering
- Top cuisines, ingredient affinity scores, and flavour profile analysis
- **Meal prediction** — predicts what you'll want to eat next
- Personalised cooking suggestions that improve with usage
- Drink preference analysis in Bartender Mode

### 👨‍👩‍👧‍👦 Family Mode
- **Family member profiles** with individual dietary restrictions, allergies, and preferences
- **Automatic serving scaling** for the whole family
- **Allergen cross-checking** — recipes are validated against every member's allergies
- **Family Groups** — create or join a group with a shared code
  - **Shared Recipes** — save recipes to a common group cookbook
  - **Meal Plan** — group admin sets daily meal plans visible to all members
  - **Chore Assignment** — admin assigns cooking/cleaning tasks with due dates and status tracking
  - **Leadership Transfer** — admin can transfer group leadership to another member
  - **Shared Pantry** — aggregated view of all members' ingredients
- **Leftover Wizard** — tell Gourmate what's left over and get new meal ideas to reduce waste
- **Family Events** — plan meals for birthdays, holidays, and celebrations

### 💰 Budget Planner (Family Mode)
- Set monthly/weekly food budget with **multi-currency support** (auto-detected from profile location)
- Track grocery spending with transaction history
- Budget utilisation progress bars and overspend alerts
- AI-powered **cost-optimised recipe suggestions** when budget is tight
- Spending insights and category breakdown

### 🍸 Bartender Mode
- **Cocktail Generator** — enter your spirits, mixers, and garnishes; get AI-crafted cocktail recipes with instructions, glassware tips, and food pairings
- **Mocktail Generator** — alcohol-free creations for everyone
- **Party Planner** — enter guest count, occasion, and vibe; get a full drink menu with quantities and a shopping list
- **Bar Inventory** — track bottles, quantities, costs, and get low-stock alerts
- **Drink Pairings** — AI-suggested food pairings for any cocktail or spirit
- **Party Rooms** — collaborative real-time party planning

### 🏆 Gamification & Achievements
- **Cooking streaks** — track consecutive days of cooking/logging meals
- **Achievement badges** — unlock milestones (First Meal, 7-Day Streak, 50 Recipes, Budget Master, etc.)
- **Badge tiers** — Bronze → Silver → Gold → Platinum progression
- Points system for every meal cooked, recipe saved, or goal hit
- Animated achievement cards with confetti effects

### 📖 My Cookbook
- Bookmark any AI-generated recipe to your personal collection
- Tag recipes (quick, healthy, comfort food, etc.)
- Search and filter your saved recipes
- Re-generate variations of saved recipes
- Rate and review recipes

### 🛒 Grocery List
- Auto-generated shopping lists from missing recipe ingredients
- Check items off as you shop
- Meal-plan-based grocery aggregation
- Smart deduplication of ingredients across multiple recipes

### 🎉 Special Occasions
- **Fusion Cuisine Creator** — blend two cuisines for unique dishes
- **Holiday & Celebration Menus** — generate full menus for events
- **Seasonal Suggestions** — local, seasonal ingredient recommendations
- **Weather-Based Recipes** — comfort food for rainy days, light meals for hot weather

### 🌍 Timezone-Aware Meal Detection
- Set your timezone in your profile (598 IANA timezones supported, common ones listed first)
- App auto-detects whether it's **Breakfast, Lunch, or Dinner** based on your local time
- All meal suggestions, quick recipes, welcome greetings, and tracking adapt to your timezone

---

## 🔐 Security & Data

- **Supabase PostgreSQL** database with **Row-Level Security (RLS)** on all 39 tables
- Complete **data isolation** — users can only access their own data
- **Rate limiting** on login attempts
- **Input sanitisation** on all user inputs
- **Session security** enforcement with automatic timeout
- **bcrypt** password hashing (SHA-256 fallback)
- **CSRF protection** tokens
- **Admin observation panel** — read-only dashboard for the admin user to monitor app health

---

## 🤖 AI & ML Stack

| Technology | Usage |
|-----------|-------|
| **GPT-4o** | Primary recipe generation, nutrition analysis, food photo analysis |
| **GPT-4o Mini** | Quick suggestions, fun tips, lightweight prompts |
| **Google Gemini 2.5 Flash** | Fallback LLM, image analysis |
| **GPT Vision** | Ingredient extraction from photos, barcode scanning, food identification |
| **LangChain + FAISS** | RAG-based recipe retrieval and recommendations |
| **scikit-learn (K-Means)** | User preference clustering and meal prediction |
| **sentence-transformers** | Semantic similarity for recipe matching |
| **YOLOv5 (Ultralytics)** | Object detection for ingredient recognition |

---

## 🎨 UI/UX

- **Dark theme** with gold accent — consistent across all pages
- **Mode-specific colour themes** — Amber (Individual), Rose/Pink (Family), Teal (Bartender), Green (Budget), Dark Tech (ML Insights)
- **Animated components** — bounce, pulse, glow, confetti, fade-in effects
- **Interactive onboarding tour** — first-login walkthrough of all features per mode
- **Contextual help tooltips** on every page
- **Responsive design** — sidebar auto-collapses on mobile
- **Smart mode suggestions** — app suggests switching modes based on time, household size, and events
- **Welcome card** with timezone-aware greetings (Good Morning / Afternoon / Evening)
- **API response caching** — reduces LLM costs with TTL-based in-memory cache

---

## 🧪 Test Suite

**483 tests** across 7 test files — all passing.

| File | Tests | Type |
|------|-------|------|
| `test_e2e.py` | 156 | End-to-end mock tests covering all pages and features |
| `test_modes_and_db.py` | 168 | Mode-specific logic, DB table validation, cross-mode integration |
| `test_crud_ops.py` | 63 | Live Supabase CRUD operations and data isolation |
| `test_live_collab.py` | 25 | Live collaborative features (family groups, party rooms) |
| `test_family.py` | 3 | Family member management and allergen checking |
| `test_smoke.py` | 1 | Basic import and startup validation |
| `test_llm.py` | 2 | LLM integration (requires API keys) |

---

## 🗄️ Database

**39 tables** in Supabase PostgreSQL, managed via `scripts/schema.sql` (single source of truth).

Key tables include: `users`, `profiles`, `ingredients`, `tracked_meals`, `nutrition_goals`, `recipes`, `favorite_recipes`, `family_members`, `family_events`, `family_groups`, `family_group_recipes`, `family_group_chores`, `family_group_meal_plans`, `cooking_chores`, `chore_rotation_settings`, `meal_plans`, `bartender_profiles`, `cocktails`, `cocktail_menus`, `bar_inventory`, `party_plans`, `party_rooms`, `party_room_members`, `grocery_lists`, `budget_settings`, `spending_transactions`, `user_gamification`, `user_achievements`, `photo_analysis`, `fitness_sync`, `ingredient_categories`, `drink_pairings`, and more.

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Frontend** | Streamlit (Python) |
| **Backend** | Python 3.11 |
| **Database** | Supabase (PostgreSQL) with RLS |
| **AI / LLM** | OpenAI GPT-4o, Google Gemini 2.5 Flash |
| **ML** | scikit-learn, sentence-transformers, FAISS |
| **Vision** | YOLOv5 (Ultralytics), OpenCV, Pillow |
| **Charts** | Plotly, Matplotlib |
| **Security** | bcrypt, PyJWT, CSRF tokens |
| **Caching** | In-memory TTL cache |
| **Testing** | pytest |

---

## 📁 Project Structure

```
Gourmate/
├── app.py                    # Main Streamlit application (1900+ lines)
├── backend.py                # Core backend — all DB ops, AI calls, auth (1700+ lines)
├── config.py                 # Configuration management
├── supabase_db.py            # Supabase client initialisation
├── run.py                    # Application launcher
├── requirements.txt          # Python dependencies
├── views/                    # Page modules
│   ├── onboarding.py         # Cinematic login/signup with fun AI tips
│   ├── mode.py               # Smart mode selection & suggestions
│   ├── profiles.py           # User/Family/Bartender profiles + timezone picker
│   ├── individual.py         # Individual mode home page
│   ├── family.py             # Family mode — members, groups, chores, shared recipes
│   ├── ingredients_new.py    # Smart pantry management
│   ├── recipes.py            # Full AI recipe generation
│   ├── photo_analysis.py     # Photo → calorie analysis
│   ├── tracking.py           # Meal tracking & daily progress
│   ├── nutrition.py          # Nutrition dashboard & goals
│   ├── ml_insights.py        # ML-powered preference insights
│   ├── cocktail.py           # Cocktail & mocktail generation
│   ├── bar_inventory.py      # Bar stock management
│   ├── budget.py             # Budget tracking & spending insights
│   ├── gamification.py       # Achievements, badges & streaks
│   ├── cookbook.py            # Saved recipe collection
│   ├── grocery.py            # Smart grocery lists
│   ├── special.py            # Special occasions & fusion cuisine
│   ├── community.py          # Community recipe sharing
│   └── admin.py              # Admin observation panel
├── utils/                    # Utility modules
│   ├── helpers.py            # Timezone detection, seasonal produce, weather
│   ├── llm.py                # LLM wrapper (OpenAI + Gemini)
│   ├── db.py                 # Database utilities
│   ├── db_connection.py      # Supabase REST adapter
│   ├── security.py           # Auth, hashing, rate limiting, CSRF
│   ├── cache.py              # API response caching
│   ├── ml_preferences.py     # ML preference engine (K-Means)
│   ├── gamification.py       # Achievement & badge logic
│   ├── budget_tracking.py    # Budget & spending logic
│   ├── nutrition_tracking.py # Nutrition goal calculations
│   ├── bar_inventory.py      # Bar stock management logic
│   ├── family_management.py  # Family group utilities
│   ├── ingredient_categorizer.py # Auto-categorisation
│   ├── ui_enhancements.py    # Animated UI components
│   ├── page_themes.py        # Per-page CSS theming
│   └── feature_tour.py       # Interactive onboarding system
├── scripts/
│   └── schema.sql            # Single source of truth — 39 tables + indexes + RLS + seed
└── tests/
    ├── test_e2e.py           # 156 end-to-end tests
    ├── test_modes_and_db.py  # 168 mode & DB tests
    ├── test_crud_ops.py      # 63 live CRUD tests
    ├── test_live_collab.py   # 25 collaboration tests
    ├── test_family.py        # Family feature tests
    ├── test_smoke.py         # Smoke test
    └── test_llm.py           # LLM integration tests
```

---

## 📝 License

This project is for personal and educational use.

---

**Made with ❤️ and lots of 🍕**
