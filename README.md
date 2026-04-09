# 🍳 Gourmate

### The AI-Powered Kitchen & Bar Companion

Gourmate is an intelligent food and beverage assistant that combines **generative AI**, **computer vision**, and **machine learning** to transform how people cook, eat, plan meals, and entertain — all from a single web application.

Built for individuals, families, and home bartenders.

---

## The Problem

People waste food because they don't know what to cook with what they have. Families struggle to coordinate meals around everyone's dietary needs. Home entertainers wing it with no planning tools. And nobody tracks nutrition consistently because it's too much effort.

## The Solution

Gourmate brings together **AI recipe generation**, **photo-based nutrition tracking**, **family meal coordination**, **smart grocery planning**, and **cocktail crafting** into one platform — powered by GPT-4o, Gemini, and custom ML models that learn each user's preferences over time.

---

## What It Does

### 🎭 Three Modes

**Individual Mode** — Personalised cooking for one or two. AI generates recipes from your pantry, respects your dietary restrictions and allergies, tracks your nutrition automatically, and learns your taste preferences over time.

**Family Mode** — Coordinates meals for the whole household. Each family member has their own dietary profile. The app cross-checks every recipe against everyone's allergies, scales servings, assigns cooking chores, manages shared grocery budgets, and lets families create private groups with shared recipe collections and meal plans.

**Bartender Mode** — A complete home bar management system. Generate cocktails and mocktails from your available spirits, plan party drink menus with quantity calculations, track bar inventory with low-stock alerts, and get AI-suggested food pairings for any drink.

---

### 🥕 Smart Pantry Management

Add ingredients four ways — type them in, select from common items, **scan a barcode**, or **photograph your fridge/pantry/receipt** and let GPT Vision extract everything automatically. Ingredients are auto-categorised and tracked with expiry dates to reduce waste.

### 🍲 AI Recipe Generation

Recipes are generated with full context awareness — **time of day, season, weather, location, available ingredients, dietary restrictions, allergies, health goals, and personal taste history**. Each recipe shows an ingredient match percentage so you know exactly what you have and what you need. One tap tracks the meal and logs its nutrition.

### 📸 Photo-to-Nutrition

Snap a photo of any meal. GPT Vision identifies the dish and estimates **calories, protein, carbs, fat, and micronutrients**. One tap logs it. Works for any cuisine — restaurant meals, home cooking, street food.

### 📊 Nutrition Intelligence

Auto-calculated daily targets based on your body metrics (BMR/TDEE). Real-time progress bars for calories and macros. Interactive trend charts over days, weeks, and months. Water intake tracking. Custom goal setting for specific nutrients.

### 🧠 Machine Learning Insights

A custom **preference engine** learns your food patterns using K-Means clustering. It tracks your top cuisines, ingredient affinities, and flavour profiles — then predicts what you'll want to eat next. Recommendations improve with every meal you cook or log.

### 👨‍👩‍👧‍👦 Family Groups & Collaboration

Families create private groups with a join code. The group admin can:
- Set **daily meal plans** visible to all members
- Assign **cooking and cleaning chores** with due dates and completion tracking
- Manage a **shared recipe collection** the whole family contributes to
- **Transfer leadership** to another member
- View an **aggregated pantry** across all members

Allergen safety is enforced automatically — no recipe is suggested that conflicts with any member's allergies.

### 💰 Budget Control

Set a monthly food budget in any currency (auto-detected from your location). Track every grocery transaction. Get spending breakdowns by category. Receive alerts when approaching your limit. The AI prioritises **cost-efficient recipes** when budget is tight.

### 🍸 Full Bar Management

Track every bottle — spirit type, brand, quantity remaining, and cost. Get **low-stock alerts** before a party. Generate cocktails and mocktails from what you actually have. Plan entire party menus with per-guest quantity calculations and shopping lists. Collaborative **party rooms** for group planning.

### 🏆 Gamification

Cooking streaks, achievement badges (Bronze → Silver → Gold → Platinum), and a points system that rewards consistency. Milestones include first meal, 7-day streak, 50 recipes cooked, budget mastery, and more.

### 🌍 Timezone-Aware

Users set their timezone from 598 supported locations. The app auto-detects whether it's breakfast, lunch, or dinner time locally — so a user in Tokyo and a user in London both get contextually appropriate suggestions at the same moment.

---

## Technical Highlights

| Area | Detail |
|------|--------|
| **AI / LLM** | GPT-4o for recipe generation and nutrition analysis, GPT-4o Mini for lightweight prompts, Google Gemini 2.5 Flash as fallback, GPT Vision for photo analysis and barcode scanning |
| **Machine Learning** | scikit-learn (K-Means clustering) for preference learning and meal prediction, sentence-transformers for semantic recipe matching |
| **RAG Pipeline** | LangChain + FAISS for retrieval-augmented recipe recommendations |
| **Computer Vision** | YOLOv5 (Ultralytics) for ingredient detection, OpenCV + Pillow for image processing |
| **Database** | Supabase PostgreSQL — 39 tables with Row-Level Security (RLS) enforcing complete data isolation between users |
| **Security** | bcrypt password hashing, rate limiting, input sanitisation, CSRF protection, session timeout enforcement, admin-only observation panel |
| **Caching** | In-memory TTL-based cache for API responses to reduce LLM costs |
| **Frontend** | Streamlit with custom CSS theming — dark mode, per-page colour schemes, animated components, responsive mobile layout |
| **Testing** | **483 automated tests** across end-to-end flows, mode-specific logic, live CRUD operations, collaborative features, and data isolation — all passing |
| **Onboarding** | Interactive feature tour on first login, contextual help tooltips on every page |

---

## Built With

Python · Streamlit · OpenAI GPT-4o · Google Gemini · LangChain · FAISS · scikit-learn · YOLOv5 · Supabase · PostgreSQL · Plotly · OpenCV · PyTorch · bcrypt

---

## Author

**Gahan Lal**

---

*This is a private repository. Access is granted on request.*
