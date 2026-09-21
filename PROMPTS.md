# 🤖 AI Ecommerce Assistant — Master Prompt Engineering Log

<div align="center">

![Angular 22](https://img.shields.io/badge/Angular-22-DD0031?style=for-the-badge&logo=angular&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-0.115+-009688?style=for-the-badge&logo=fastapi&logoColor=white)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?style=for-the-badge&logo=python&logoColor=white)
![SQL Server](https://img.shields.io/badge/SQL_Server-LocalDB-CC292B?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![SQLAlchemy](https://img.shields.io/badge/SQLAlchemy-2.0-D71F00?style=for-the-badge&logo=sqlalchemy&logoColor=white)
![Web Speech API](https://img.shields.io/badge/Web_Speech_API-Voice_Shopping-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white)
![Status](https://img.shields.io/badge/Architecture-Enterprise_Edition-success?style=for-the-badge)

<p align="center">
  <strong>Comprehensive prompt engineering methodology, structured prompt sequences, and execution logs used to build the autonomous AI-powered e-commerce assistant from scratch.</strong>
</p>

</div>

---

> [!NOTE]
> **Project Context:**  
> The **AI Ecommerce Assistant** is an enterprise-grade retail platform combining traditional transactional e-commerce (catalog browsing, shopping cart mutations, atomic checkout, live order tracking) with an autonomous conversational **AI Shopping Agent** supporting hands-free voice shopping, side-by-side product comparisons, budget advising, order management, and one-click reordering.

> [!TIP]
> **Prompt Engineering Methodology:**  
> This project followed a **Tiered Chain-of-Thought (CoT)** and **Role-Based Persona Prompting** framework. Each prompt strictly defines the architectural constraints, type contracts, relational schemas, and expected outputs before generating source code.

---

## 📑 Table of Contents

- [📊 Prompt Execution & Architecture Matrix](#-prompt-execution--architecture-matrix)
- [🏗️ Phase 1: Architecture, Requirements & Low-Level Design (LLD)](#-phase-1-architecture-requirements--low-level-design-lld)
  - [Prompt 1.1: System Architecture & Requirements Definition](#prompt-11-system-architecture--requirements-definition)
  - [Prompt 1.2: Enterprise LLD Document Generation](#prompt-12-enterprise-lld-document-generation)
- [🗄️ Phase 2: Database Schema & SQLAlchemy Models](#-phase-2-database-schema--sqlalchemy-models)
  - [Prompt 2.1: Database Engine & LocalDB Connection Configuration](#prompt-21-database-engine--localdb-connection-configuration)
  - [Prompt 2.2: 3NF Relational SQLAlchemy ORM Models](#prompt-22-3nf-relational-sqlalchemy-orm-models)
  - [Prompt 2.3: Pydantic Validation Schemas (DTO Contracts)](#prompt-23-pydantic-validation-schemas-dto-contracts)
- [⚡ Phase 3: Backend FastAPI REST Endpoints & Authentication](#-phase-3-backend-fastapi-rest-endpoints--authentication)
  - [Prompt 3.1: Cryptographic Authentication & Password Hashing](#prompt-31-cryptographic-authentication--password-hashing)
  - [Prompt 3.2: E-Commerce CRUD Routers (Products, Cart, Orders)](#prompt-32-e-commerce-crud-routers-products-cart-orders)
- [🧠 Phase 4: AI Shopping Assistant & Intent Orchestration Engine](#-phase-4-ai-shopping-assistant--intent-orchestration-engine)
  - [Prompt 4.1: Domain Catalog Knowledge Base & Spec Advantages](#prompt-41-domain-catalog-knowledge-base--spec-advantages)
  - [Prompt 4.2: 23-Capability Natural Language Intent Pipeline](#prompt-42-23-capability-natural-language-intent-pipeline)
  - [Prompt 4.3: FastAPI Chatbot Router Endpoint](#prompt-43-fastapi-chatbot-router-endpoint)
- [🎨 Phase 5: Frontend Single Page Application (Angular 22)](#-phase-5-frontend-single-page-application-angular-22)
  - [Prompt 5.1: Angular Reactive Core & Signals Architecture](#prompt-51-angular-reactive-core--signals-architecture)
  - [Prompt 5.2: Material Storefront Views (Catalog, Cart, Orders, Auth)](#prompt-52-material-storefront-views-catalog-cart-orders-auth)
- [💬 Phase 6: Floating Chatbot Component & Material UI Integration](#-phase-6-floating-chatbot-component--material-ui-integration)
  - [Prompt 6.1: Floating Chat Window & Interactive Controls](#prompt-61-floating-chat-window--interactive-controls)
  - [Prompt 6.2: Dynamic Product Cards, Bundle Cards & State Sync](#prompt-62-dynamic-product-cards-bundle-cards--state-sync)
- [🎙️ Phase 7: Native Voice Shopping & Web Speech API](#-phase-7-native-voice-shopping--web-speech-api)
  - [Prompt 7.1: Client-Side Speech Recognition Integration](#prompt-71-client-side-speech-recognition-integration)
- [🧪 Phase 8: Conversational Evaluation Test Suite](#-phase-8-conversational-evaluation-test-suite)
  - [Evaluation Test Prompts Matrix](#evaluation-test-prompts-matrix)

---

## 📊 Prompt Execution & Architecture Matrix

| Phase | Milestone / Domain | Primary Artifact | Target Tech Stack | Status |
|:---:|:---|:---|:---|:---:|
| **01** | Architecture & LLD Specification | `docs/LLD_AI_Ecommerce_Assistant.md` | Architecture, Mermaid | `COMPLETED` ✅ |
| **02** | Relational Database & Models | `backend/app/models.py`, `database.py` | SQLAlchemy 2.0, MSSQL | `COMPLETED` ✅ |
| **03** | FastAPI Backend & Crypto Auth | `backend/app/routers/` (auth, products, cart, orders) | FastAPI, PBKDF2, Uvicorn | `COMPLETED` ✅ |
| **04** | AI Shopping Intent Engine | `backend/app/services/ai_service.py` | Python NLU, Regex, Knowledge Base | `COMPLETED` ✅ |
| **05** | Angular 22 SPA Frontend | `frontend/src/app/pages/` (catalog, cart, orders) | Angular Signals, Material | `COMPLETED` ✅ |
| **06** | Floating Chatbot UI Widget | `frontend/src/app/components/chatbot/` | Angular Material, CSS3, DOM | `COMPLETED` ✅ |
| **07** | Voice Shopping Engine | `chatbot.ts` (`toggleVoiceInput`) | Web Speech API, Chromium | `COMPLETED` ✅ |
| **08** | Conversational Testing Suite | Live Chatbot Validation Logs | E2E Conversational Testing | `COMPLETED` ✅ |

---

## 🏗️ Phase 1: Architecture, Requirements & Low-Level Design (LLD)

### Prompt 1.1: System Architecture & Requirements Definition

> **Role / Persona:** Enterprise Solution Architect  
> **Output Artifact:** System Architecture Plan & Functional Requirements  
> **Target:** System Design & Technical Specifications

```markdown
Act as an Enterprise Solution Architect. We need to build a full-stack, enterprise-grade e-commerce application named "AI Ecommerce Assistant". 

Key architectural requirements:
1. Frontend: Angular 22 Single Page Application (SPA) using standalone components, Angular Signals for fine-grained reactive state, and Angular Material design.
2. Backend: Python FastAPI providing asynchronous non-blocking REST endpoints with strict Pydantic validation.
3. Database: Microsoft SQL Server LocalDB via SQLAlchemy 2.0 ORM normalized to 3NF.
4. Core Differentiator: An autonomous conversational "AI Shopping Assistant" integrated with the transactional database to execute live cart updates, order tracking, order cancellations, side-by-side product comparisons, budget advising, and multi-product concierge bundles.

Provide a comprehensive Low-Level Design (LLD) document including Functional Requirements (FRs), Non-Functional Requirements (NFRs), System Architecture Diagram (Mermaid), Component Diagram, Database ERD, Security Considerations, and Sequence Diagrams for key AI workflows.
```

---

### Prompt 1.2: Enterprise LLD Document Generation

> **Role / Persona:** Lead Technical Documentation Engineer  
> **Output Artifact:** `docs/LLD_AI_Ecommerce_Assistant.md`  
> **Target:** Full Technical LLD Document

```markdown
Create a detailed, production-ready markdown file `docs/LLD_AI_Ecommerce_Assistant.md` structured as follows:

1. Executive Summary & Project Objectives:
   - High-reliability, sub-200ms REST response latency, sub-500ms AI inference.
2. Functional Requirements (FRs):
   - Auth & Session (FR-AUTH-01 to 04: signup, PBKDF2 hash, login session, X-User-Id context).
   - E-Commerce Storefront (FR-ECOMM-01 to 07: catalog, cart, atomic checkout, order tracking, cancellation, reorder).
   - AI Shopping Agent (FR-AI-01 to 11: search, compare, cart mutations, concierge, budget advisor, voice).
3. Non-Functional Requirements (NFRs) Table.
4. Layered Clean Architecture Flowchart (Presentation, API Gateway, Service Tier, Data Tier).
5. Component Diagram (Angular components/services vs FastAPI routers/services).
6. Entity Relationship Diagram (ERD):
   - Exactly 5 tables: Users, Products, CartItems, Orders, OrderItems.
7. API Design Table & JSON Payload Examples.
8. Authentication Sequence Diagram (PBKDF2 validation).
9. AI Assistant Workflow Flowchart & Sequence Diagrams (Product Comparison, Real-time Order Cancellation).
10. Security & Logging Strategy (PBKDF2-HMAC-SHA256, SQLi prevention, CORS, audit trails).
11. Deployment Architecture & Future Enhancements.
```

---

## 🗄️ Phase 2: Database Schema & SQLAlchemy Models

### Prompt 2.1: Database Engine & LocalDB Connection Configuration

> **Role / Persona:** Database & Backend Infrastructure Specialist  
> **Output Artifact:** `backend/app/database.py` & `backend/app/test_connection.py`  
> **Target:** Microsoft SQL Server Connection

```markdown
In `backend/app/database.py`, configure a SQLAlchemy engine and session factory for Microsoft SQL Server LocalDB:
- Connection String: `mssql+pyodbc://@(localdb)\MSSQLLocalDB/AI_ECOMMERCE?driver=ODBC+Driver+18+for+SQL+Server&trusted_connection=yes`
- Implement declarative Base and SessionLocal factory with autocommit=False, autoflush=False.
- Provide a connection verification script `backend/app/test_connection.py` to test connectivity, query the Products table, and verify active schema state.
```

---

### Prompt 2.2: 3NF Relational SQLAlchemy ORM Models

> **Role / Persona:** Senior Data Engineer  
> **Output Artifact:** `backend/app/models.py`  
> **Target:** 3NF Database Models

```markdown
In `backend/app/models.py`, implement declarative SQLAlchemy 2.0 ORM models normalized to Third Normal Form (3NF):

1. Product:
   - Table: "Products"
   - ProductId (Integer, primary_key=True)
   - Name (String), Category (String), Price (Numeric), Stock (Integer)
2. CartItem:
   - Table: "CartItems"
   - CartItemId (Integer, primary_key=True)
   - ProductId (Integer), Quantity (Integer), UserId (Integer, nullable=True)
3. Order:
   - Table: "Orders"
   - OrderId (Integer, primary_key=True)
   - UserId (Integer, nullable=True), TotalAmount (Numeric), Status (String), CreatedAt (DateTime, default=utcnow)
4. OrderItem:
   - Table: "OrderItems"
   - OrderItemId (Integer, primary_key=True)
   - OrderId (Integer), ProductId (Integer), Quantity (Integer)
5. User:
   - Table: "Users"
   - UserId (Integer, primary_key=True, autoincrement=True)
   - FirstName (String 100), LastName (String 100), Email (String 255, unique, index)
   - PasswordHash (String 255), Role (String 50, default="Customer"), Interests (String 500, nullable=True), CreatedAt (DateTime, default=utcnow)
```

---

### Prompt 2.3: Pydantic Validation Schemas (DTO Contracts)

> **Role / Persona:** API Contract Specialist  
> **Output Artifact:** `backend/app/schemas.py`  
> **Target:** Type-Safe Data Transfer Objects

```markdown
In `backend/app/schemas.py`, define Pydantic v2 schemas for all API payloads:
- Products: ProductResponse, ProductCreateRequest, ProductUpdateRequest
- Cart: AddToCartRequest (ProductId, Quantity, UserId), UpdateCartQuantityRequest (Quantity)
- Orders: CreateOrderRequest (TotalAmount, UserId)
- Authentication: SignupRequest, LoginRequest, UserResponse (including interests: List[str])
- Conversational Chatbot:
  - ChatRequest: message (str), user_name (Optional[str]), interests (Optional[List[str]]), user_id (Optional[int])
  - ChatResponse: response (str), intent (Optional[str]), action_taken (Optional[str]), products (Optional[List]), cart_items (Optional[List]), orders (Optional[List]), order_details (Optional[Any]), comparison (Optional[Any]), bundle (Optional[Any]), suggested_prompts (Optional[List[str]])
```

---

## ⚡ Phase 3: Backend FastAPI REST Endpoints & Authentication

### Prompt 3.1: Cryptographic Authentication & Password Hashing

> **Role / Persona:** Application Security Engineer  
> **Output Artifact:** `backend/app/routers/auth.py`  
> **Target:** Secure Salted Authentication

```markdown
In `backend/app/routers/auth.py`:
1. Implement secure password hashing:
   - Function: `hash_password(password: str) -> str` using PBKDF2-HMAC-SHA256 with 100,000 iterations and a 16-byte random salt (`os.urandom(16)`). Format: `<salt_hex>$<key_hex>`.
   - Function: `verify_password(plain_password: str, hashed_password: str) -> bool` recalculating the key with the stored salt.
2. Endpoints:
   - `POST /auth/signup`: Validates email regex, enforces strong password complexity (8+ chars, uppercase, lowercase, digit, special char), checks email uniqueness, stores interests as comma-separated string, returns UserResponse.
   - `POST /auth/login`: Authenticates email and password hash, returns authenticated profile.
   - `GET /auth/users`: Retrieves registered user accounts for inspection.
3. Seeding Utility:
   - `seed_demo_users_if_needed(db)`: Automatically creates default demo account `satyam@example.com` on startup if not already present.
```

---

### Prompt 3.2: E-Commerce CRUD Routers (Products, Cart, Orders)

> **Role / Persona:** Full-Stack Backend Developer  
> **Output Artifact:** `backend/app/routers/` (products, cart, orders)  
> **Target:** Transactional Commerce Endpoints

```markdown
Create the following FastAPI routers with database dependency injection (`Depends(get_db)`):

1. `backend/app/routers/products.py`:
   - `GET /products/`: Retrieve all catalog items.
   - `GET /products/{id}`: Retrieve product details or return 404.
   - `POST /`, `PUT /{id}`, `DELETE /{id}`: Catalog administration operations.
2. `backend/app/routers/cart.py`:
   - `POST /cart/add`: Check if item already exists in cart for the user; if so, increment quantity, else create new `CartItem`.
   - `GET /cart/`: Join `CartItems` with `Products`, calculate subtotals and grand total.
   - `PUT /cart/{cart_item_id}`: Update specific item quantity; delete if quantity <= 0.
   - `DELETE /cart/{cart_item_id}`: Remove specific line item.
   - `DELETE /cart/clear`: Flush active user cart.
3. `backend/app/routers/orders.py`:
   - `POST /orders/`: Atomic transaction creating `Order`, bulk inserting `OrderItems` from active cart, and flushing `CartItems`.
   - `GET /orders/`: Retrieve past orders ordered by CreatedAt descending.
   - `GET /orders/{order_id}`: Retrieve order details and line items.
   - `PUT /orders/cancel/{id}`: Validate order status; allow cancellation if 'PLACED' or 'PROCESSING', disallow if 'DELIVERED' or 'CANCELLED'.
   - `POST /orders/{id}/reorder`: Duplicate past order items and batch-insert them into the active user cart.
```

---

## 🧠 Phase 4: AI Shopping Assistant & Intent Orchestration Engine

### Prompt 4.1: Domain Catalog Knowledge Base & Spec Advantages

> **Role / Persona:** Conversational AI & E-Commerce Knowledge Engineer  
> **Output Artifact:** `backend/app/services/ai_service.py` (Knowledge Dictionaries)  
> **Target:** In-Memory Catalog Intelligence

```markdown
In `backend/app/services/ai_service.py`, build an extensive domain catalog knowledge dictionary:

1. `PRODUCT_KNOWLEDGE`:
   - Define specs, strengths, suitable workloads, pros, cons, and verdict for:
     - Mobiles: "Samsung M35" (6000mAh battery, Super AMOLED 120Hz), "OnePlus Nord CE" (Sony 50MP, 67W SuperVOOC), "Redmi Note 14" (Best budget under ₹20k).
     - Laptops: "Acer Aspire 7" (Dedicated GPU under ₹50k for coding/gaming), "HP Victus" (144Hz, OMEN thermal cooling, creator/AAA gaming), "Lenovo IdeaPad Gaming" (Ergonomic keyboard, Rapid Charge Pro).
     - Accessories: "Boat Airdopes 311" (₹1,299, 40H battery, punchy bass), "Noise Smart Watch" (₹2,499, Bluetooth calling, 7-day battery).
2. `UNAVAILABLE_CATALOG_ALTERNATIVES`:
   - Map commonly queried out-of-stock brands ("iPhone", "Apple", "MacBook", "Pixel", "AirPods") to verified in-stock catalog alternatives with clear reasoning.
```

---

### Prompt 4.2: 23-Capability Natural Language Intent Pipeline

> **Role / Persona:** Natural Language Processing (NLP) Specialist  
> **Output Artifact:** `AIService.process_message(...)` in `ai_service.py`  
> **Target:** 5-Level Autonomous AI Shopping Agent

```markdown
Implement `AIService.process_message(message, db, user_name, interests, user_id)` orchestrating 23 capabilities across 5 distinct intelligence levels:

- Level 1 (Core Commerce):
  - Onboarding & Greeting: Acknowledge user interests from profile.
  - Search & Filter: Price ceilings (e.g. "Show mobiles under ₹30,000").
  - Recommendations with explicit "Reason:" block.
  - Add to Cart with quantity extraction ("Add 2 Boat Airdopes").
  - View Cart with subtotal and grand total breakdown.
  - Place Order / Direct Checkout with atomic DB mutation.
  - View Order History with dates and status badges.
- Level 2 (Comparison & Alternatives):
  - Product Comparison Matrix ⭐: Compare two items (e.g. "Compare Samsung M35 and OnePlus Nord CE") across battery, camera, display, and price, with a definitive recommendation pick.
  - Smart Budget Recommendations with "Why?" rationale.
  - Out-of-Stock Alternatives: Propose substitutes for unavailable items.
  - Explain Product: Detailed pros, cons, and target workloads.
- Level 3 (Order & Cart Lifecycle):
  - Cancel Order ⭐: Live DB cancellation with status validation (reject if DELIVERED, confirm refund if PLACED).
  - Track Order ⭐: Milestone timeline (Placed, In Transit, Delivered) with carrier (BlueDart Express) and ETA.
  - 1-Click Reorder ⭐: Batch-clone past order items into active cart.
  - Update Cart Quantity ("Increase Samsung quantity to 3").
  - Remove from Cart ("Remove Samsung from cart").
  - Cart Summary ("How much will I pay?").
- Level 4 (Decision Support & Advisory):
  - Smart Budget Advisor ⭐: "I have ₹25,000. Which phone is best?".
  - Purchase Decision Support: "Should I buy Samsung M35 or wait?".
  - Requirement-based Search: Map activities (e.g. "coding + gaming") to hardware specs.
  - Gift Recommendations: "Gift for a college student under ₹5,000".
- Level 5 (Concierge & Personalization):
  - AI Shopping Concierge Setup Builder ⭐: "Build a complete setup under ₹60,000" -> Assemble Laptop + Earbuds + Smart Watch with bundle metadata.
  - Personalized Suggestions: Curate items matching user profile interest tags.
```

---

### Prompt 4.3: FastAPI Chatbot Router Endpoint

> **Role / Persona:** Backend API Engineer  
> **Output Artifact:** `backend/app/routers/chatbot.py`  
> **Target:** Chat Execution Controller

```markdown
In `backend/app/routers/chatbot.py`:
- Implement `POST /chatbot/chat` accepting `ChatRequest` and returning `ChatResponse`.
- Inject `db: Session = Depends(get_db)` and `current_user_id: Optional[int] = Depends(get_current_user_id)`.
- Pass request message, user_name, interests, and resolved user_id to `ai_service.process_message(...)`.
- Return typed `ChatResponse` with response text, intent, action_taken, products, bundle, and comparison payloads.
```

---

## 🎨 Phase 5: Frontend Single Page Application (Angular 22)

### Prompt 5.1: Angular Reactive Core & Signals Architecture

> **Role / Persona:** Principal Frontend Architect (Angular)  
> **Output Artifact:** `app.config.ts`, `auth.ts`, `cart.ts`, `ai-chat.ts`  
> **Target:** Modern Standalone & Signals Topology

```markdown
Initialize an Angular 22 application using Standalone Components, Angular Signals, and Angular Material:

1. `app.config.ts`:
   - Configure `provideHttpClient(withFetch(), withInterceptors([authInterceptor]))`.
   - Configure `provideRouter(routes)` and `provideAnimationsAsync()`.
2. State Management with Angular Signals:
   - `AuthService`: `currentUser = signal<User | null>(null)`, `userFirstName = computed(...)`, `userInterests = computed(...)`.
   - `CartService`: `cartCount = signal<number>(0)`, `refreshCartCount()` to sync cart badge across pages.
   - `AiChatService`: `isChatOpen = signal<boolean>(false)`, `sendMessage(...)` calling `POST /chatbot/chat`.
3. Interceptor & Guard:
   - `auth.interceptor.ts`: Injects `X-User-Id` header from active user session.
   - `auth.guard.ts`: Protects `/dashboard`, `/products`, `/cart`, `/orders` from unauthenticated access.
```

---

### Prompt 5.2: Material Storefront Views (Catalog, Cart, Orders, Auth)

> **Role / Persona:** UI/UX Frontend Specialist  
> **Output Artifact:** `pages/` (login, signup, dashboard, products, cart, orders)  
> **Target:** Responsive Material Storefront

```markdown
Build responsive storefront pages using Angular Material components:

1. `pages/signup` & `pages/login`:
   - Enterprise branding panel, reactive forms, password strength meter.
   - Multi-select interest chips (Mobile Phones, Laptops, Accessories, Gaming, Smart Devices) with default selections.
2. `pages/products`:
   - Grid layout of catalog products with category filter chips, search bar, stock badges, and "Add to Cart" button.
3. `pages/cart`:
   - Cart item list with quantity controls (+ / -), subtotal calculation, tax/free shipping badges, and "Checkout" button.
4. `pages/orders`:
   - Order history cards with status badges (Placed, Shipped, Delivered, Cancelled), tracking stepper, "Cancel Order" dialog, and "Reorder" action.
```

---

## 💬 Phase 6: Floating Chatbot Component & Material UI Integration

### Prompt 6.1: Floating Chat Window & Interactive Controls

> **Role / Persona:** Conversational UI Specialist  
> **Output Artifact:** `frontend/src/app/components/chatbot/` (chatbot.ts, chatbot.html, chatbot.css)  
> **Target:** Material Floating Assistant

```markdown
Create a floating AI Assistant component in `frontend/src/app/components/chatbot/`:

1. Trigger Button:
   - Fixed FAB at bottom-right with gradient background (`#7c4dff` to `#1976d2`) and `auto_awesome` icon.
2. Floating Chat Window (380px x 560px):
   - Header with bot avatar, name, and pulsing green online status dot.
   - Auto-scrolling chat messages body with bubble distinction (user: blue bubble, bot: white card with border).
   - Typing indicator with 3 animated bouncing dots.
   - Suggested prompts horizontal chip bar with quick-tap query chips.
   - Input footer with voice microphone button, text input, and send button.
```

---

### Prompt 6.2: Dynamic Product Cards, Bundle Cards & State Sync

> **Role / Persona:** Senior Frontend Engineer  
> **Output Artifact:** Rich Widget Rendering & Signal Synchronization  
> **Target:** In-Chat Actions & Reactivity

```markdown
Extend `chatbot.ts` and `chatbot.html` to support rich interactive UI widgets:

1. In-Chat Product Embeds:
   - When `msg.products` is present, render compact product cards with title, price, category, and an inline "Add" button invoking `cartService.addToCart(...)`.
2. Concierge Bundle Cards:
   - When `msg.bundle` is present, render a highlighted package card showing included devices, total bundle price, and a one-click "Add Setup to Cart" button.
3. Contextual Navigation Links:
   - Render "View Cart →" or "View Orders →" links based on message intent.
4. Automatic Reactive Cart Synchronization:
   - In `sendMessage()`, whenever the response contains `action_taken === 'cart_updated'`, `item_deleted`, or `order_created`, immediately invoke `cartService.refreshCartCount()` so the navbar badge updates without page reload.
5. Client-Side Fallback Resilience:
   - Implement `handleLocalQueryFallback(query)` to display cached products if backend network fails.
```

---

## 🎙️ Phase 7: Native Voice Shopping & Web Speech API

### Prompt 7.1: Client-Side Speech Recognition Integration

> **Role / Persona:** Web Speech & Accessibility Engineer  
> **Output Artifact:** `initSpeechRecognition()` & `toggleVoiceInput()` in `chatbot.ts`  
> **Target:** Hands-Free Voice Procurement

```markdown
In `frontend/src/app/components/chatbot/chatbot.ts`:

1. Implement native client-side speech recognition using the browser's Web Speech API (`webkitSpeechRecognition` / `SpeechRecognition`) with zero external cloud dependencies.
2. Create `initSpeechRecognition()`:
   - Set language to `en-IN`.
   - On result: extract `event.results[0][0].transcript`, assign to `inputMessage`, stop listening, and automatically invoke `sendMessage()`.
   - On error / end: reset `isListening = signal<boolean>(false)`.
3. Implement `toggleVoiceInput()`:
   - Toggle voice listening state.
   - When listening, animate the mic icon with a pulsing red ripple animation and update the placeholder to "Listening to voice command...".
```

---

## 🧪 Phase 8: Conversational Evaluation Test Suite

### Evaluation Test Prompts Matrix

Use the following real-world prompts in the chatbot during live demonstrations to evaluate all 23 capabilities:

| # | Capability / Category | Test Prompt (Query to Enter/Speak) | Expected Assistant Action & Output |
|:---:|:---|:---|:---|
| **01** | **Greeting & Onboarding** | `"Hi"` / `"Hello"` | Personal welcome acknowledging user profile interest tags (e.g. Mobiles, Laptops). |
| **02** | **Product Comparison ⭐** | `"Compare Samsung M35 and OnePlus Nord CE"` | Side-by-side matrix (Battery, Camera, Display, Price) + recommended winner pick + interactive product cards. |
| **03** | **Budget Recommendation** | `"I have ₹50,000 budget. Suggest a laptop."` | Recommends Acer Aspire 7 with explicit "Why?" rationale and in-stock units. |
| **04** | **Smart Budget Advisor ⭐** | `"I have ₹25,000. Which phone is best?"` | Recommends Samsung M35 (6000mAh + 120Hz) and highlights Redmi Note 14 as budget alternative. |
| **05** | **Out-of-Stock Substitute** | `"Add iPhone 16 to cart"` | Explains iPhone is unavailable; suggests verified in-stock alternatives (Samsung M35, OnePlus Nord CE). |
| **06** | **Product Explain / Pros & Cons** | `"Why should I buy HP Victus?"` | Displays suitable workloads, bulleted pros (144Hz, dual cooling) and cons (heavier chassis). |
| **07** | **Purchase Decision Support** | `"Should I buy Samsung M35 or wait?"` | Generates decision matrix based on price stability, battery needs, and verified stock. |
| **08** | **Requirement-Based Search** | `"I need a laptop for coding and gaming"` | Filters high-performance laptops with dedicated GPUs and cooling systems. |
| **09** | **Gift Recommendation** | `"Gift for a college student under ₹5,000"` | Suggests combo gift: Noise Smart Watch (₹2,499) + Boat Airdopes (₹1,299) within ₹5k budget. |
| **10** | **Setup Concierge ⭐** | `"Build a complete setup under ₹60,000"` | Assembles Laptop + Earbuds + Smart Watch bundle with one-click "Add Setup to Cart" CTA. |
| **11** | **Add Setup Bundle to Cart** | `"Add setup to cart"` | Adds all bundle items into active cart; navbar cart counter increments automatically. |
| **12** | **Add Single Product** | `"Add Samsung M35 to cart"` | Inserts `CartItem` into database; updates subtotal and increments navbar badge. |
| **13** | **Update Quantity** | `"Increase Samsung quantity to 3"` | Mutates cart quantity in database; reports updated line item subtotal. |
| **14** | **Cart Bill Summary** | `"How much will I pay?"` | Computes itemized breakdown, total item count, and confirms free shipping. |
| **15** | **View Active Cart** | `"Show my cart"` | Lists line items with quantities, prices, grand total, and "View Cart →" link. |
| **16** | **Autonomous Checkout** | `"Place order"` | Atomic transaction: converts cart into `Order` and `OrderItems`, clears cart, returns Order ID. |
| **17** | **Live Order Tracking ⭐** | `"Where is my order?"` | Displays Order #, Status (In Transit), Carrier (BlueDart Express), ETA (2 Days), and timeline. |
| **18** | **Cancel Order ⭐** | `"Cancel my order"` / `"Cancel order #1009"` | Validates status; updates DB status to CANCELLED and initiates simulated refund. |
| **19** | **1-Click Reorder ⭐** | `"Order the same products as my last order"` | Reads items from latest order, re-inserts them into active cart, ready for checkout. |
| **20** | **Personalized Suggestions** | `"Personalized suggestions for me"` | Queries database filtered by user's profile interests (e.g. Mobiles, Gaming Laptops). |
| **21** | **Voice Shopping 🎙️** | *Click Mic & speak:* `"Suggest a gaming laptop"` | Transcribes speech via Web Speech API, sends query, and displays recommended hardware. |

---

<div align="center">
  <sub>AI Ecommerce Assistant • Enterprise Engineering Architecture Log • Built with Angular 22 & FastAPI</sub>
</div>
