# AI Ecommerce Assistant — Master Prompt Engineering Log

```
========================================================================================
PROJECT            : AI Ecommerce Assistant (Enterprise Edition)
ARCHITECTURE TIER  : Layered Clean Architecture (Decoupled SPA + Async REST API)
CORE STACK         : Angular 22 | Python FastAPI | SQL Server LocalDB | SQLAlchemy 2.0
INTELLIGENCE TYPE  : Autonomous Conversational Commerce & In-Memory Domain Reasoning
DOCUMENT TYPE      : Master Prompt Engineering & Execution Specification
STATUS             : Production Verified & Approved
========================================================================================
```

---

## 📌 Executive Overview

This document serves as the official, comprehensive repository of all structured prompts utilized throughout the end-to-end software development lifecycle of the **AI Ecommerce Assistant**.

The project was constructed following a disciplined **Role-Based Persona Prompting** and **Chain-of-Thought (CoT)** methodology. Every prompt explicitly defines:
- **Architectural Constraints & System Boundaries**
- **Type Contracts & Relational 3NF Schemas**
- **Deterministic Business Logic & Fallback Guardrails**
- **Target File Artifacts & Concrete Implementation Criteria**

---

## 🧭 Navigation Index

- [1. Prompt Execution & Delivery Matrix](#1-prompt-execution--delivery-matrix)
- [2. Phase 1: Architecture, Requirements & Low-Level Design (LLD)](#2-phase-1-architecture-requirements--low-level-design-lld)
  - [Prompt 1.1: System Architecture & Requirements Definition](#prompt-11-system-architecture--requirements-definition)
  - [Prompt 1.2: Enterprise LLD Document Generation](#prompt-12-enterprise-lld-document-generation)
- [3. Phase 2: Database Schema & SQLAlchemy Models](#3-phase-2-database-schema--sqlalchemy-models)
  - [Prompt 2.1: Database Engine & LocalDB Connection Setup](#prompt-21-database-engine--localdb-connection-setup)
  - [Prompt 2.2: 3NF Relational SQLAlchemy ORM Declarative Models](#prompt-22-3nf-relational-sqlalchemy-orm-declarative-models)
  - [Prompt 2.3: Pydantic Validation Schemas & DTO Contracts](#prompt-23-pydantic-validation-schemas--dto-contracts)
- [4. Phase 3: Backend FastAPI REST Endpoints & Authentication](#4-phase-3-backend-fastapi-rest-endpoints--authentication)
  - [Prompt 3.1: Cryptographic Authentication & Salted PBKDF2 Password Hashing](#prompt-31-cryptographic-authentication--salted-pbkdf2-password-hashing)
  - [Prompt 3.2: E-Commerce Storefront CRUD Routers](#prompt-32-e-commerce-storefront-crud-routers)
- [5. Phase 4: AI Shopping Assistant & Intent Orchestration Engine](#5-phase-4-ai-shopping-assistant--intent-orchestration-engine)
  - [Prompt 4.1: Domain Catalog Knowledge Base & Spec Advancements](#prompt-41-domain-catalog-knowledge-base--spec-advancements)
  - [Prompt 4.2: 23-Capability Natural Language Intent Processing Pipeline](#prompt-42-23-capability-natural-language-intent-processing-pipeline)
  - [Prompt 4.3: FastAPI Chat Execution Controller](#prompt-43-fastapi-chat-execution-controller)
- [6. Phase 5: Frontend Single Page Application (Angular 22)](#6-phase-5-frontend-single-page-application-angular-22)
  - [Prompt 5.1: Angular Reactive Core, Signals & Interceptors](#prompt-51-angular-reactive-core-signals--interceptors)
  - [Prompt 5.2: Material Design Storefront Views](#prompt-52-material-design-storefront-views)
- [7. Phase 6: Floating Chatbot Component & Material UI Integration](#7-phase-6-floating-chatbot-component--material-ui-integration)
  - [Prompt 6.1: Floating Chat Window & Interactive Controls](#prompt-61-floating-chat-window--interactive-controls)
  - [Prompt 6.2: In-Chat Product Embeds, Bundle Cards & State Synchronization](#prompt-62-in-chat-product-embeds-bundle-cards--state-synchronization)
- [8. Phase 7: Native Voice Shopping & Web Speech API](#8-phase-7-native-voice-shopping--web-speech-api)
  - [Prompt 7.1: Client-Side Speech Recognition Integration](#prompt-71-client-side-speech-recognition-integration)
- [9. Phase 8: Conversational Evaluation Test Suite](#9-phase-8-conversational-evaluation-test-suite)
  - [Comprehensive Conversational Validation Matrix](#comprehensive-conversational-validation-matrix)

---

## 1. Prompt Execution & Delivery Matrix

| Phase | Milestone / Domain | Primary Artifact Created | Target Stack | Delivery Status |
|:---:|:---|:---|:---|:---:|
| **01** | Architecture & Low-Level Design | `docs/LLD_AI_Ecommerce_Assistant.md` | Architecture, Mermaid | `COMPLETED` |
| **02** | Relational Database & Models | `backend/app/models.py`, `database.py` | SQLAlchemy 2.0, MSSQL | `COMPLETED` |
| **03** | FastAPI Backend & Crypto Auth | `backend/app/routers/` (auth, products, cart, orders) | FastAPI, PBKDF2, Uvicorn | `COMPLETED` |
| **04** | AI Shopping Intent Engine | `backend/app/services/ai_service.py` | Python NLU, Knowledge Base | `COMPLETED` |
| **05** | Angular 22 SPA Frontend | `frontend/src/app/pages/` (catalog, cart, orders) | Angular Signals, Material | `COMPLETED` |
| **06** | Floating Chatbot UI Widget | `frontend/src/app/components/chatbot/` | Angular Material, CSS3 | `COMPLETED` |
| **07** | Voice Shopping Engine | `chatbot.ts` (`toggleVoiceInput`) | Web Speech API | `COMPLETED` |
| **08** | Conversational Testing Suite | Live Chatbot Validation Verification | E2E Conversational Testing | `COMPLETED` |

---

## 2. Phase 1: Architecture, Requirements & Low-Level Design (LLD)

### Prompt 1.1: System Architecture & Requirements Definition

```
[ METADATA ]
Target Artifact : System Architecture Plan & Functional Requirements
Role / Persona  : Enterprise Solution Architect
Objective       : Define full-stack decoupled architecture and specifications
```

```text
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

```
[ METADATA ]
Target Artifact : docs/LLD_AI_Ecommerce_Assistant.md
Role / Persona  : Lead Technical Documentation Engineer
Objective       : Generate 100% code-accurate Low-Level Design documentation
```

```text
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

## 3. Phase 2: Database Schema & SQLAlchemy Models

### Prompt 2.1: Database Engine & LocalDB Connection Setup

```
[ METADATA ]
Target Artifact : backend/app/database.py & backend/app/test_connection.py
Role / Persona  : Database & Backend Infrastructure Specialist
Objective       : Establish persistent pyodbc connection to Microsoft SQL Server LocalDB
```

```text
In `backend/app/database.py`, configure a SQLAlchemy engine and session factory for Microsoft SQL Server LocalDB:
- Connection String: `mssql+pyodbc://@(localdb)\MSSQLLocalDB/AI_ECOMMERCE?driver=ODBC+Driver+18+for+SQL+Server&trusted_connection=yes`
- Implement declarative Base and SessionLocal factory with autocommit=False, autoflush=False.
- Provide a connection verification script `backend/app/test_connection.py` to test connectivity, query the Products table, and verify active schema state.
```

---

### Prompt 2.2: 3NF Relational SQLAlchemy ORM Declarative Models

```
[ METADATA ]
Target Artifact : backend/app/models.py
Role / Persona  : Senior Data Engineer
Objective       : Implement 3NF normalized declarative SQLAlchemy models
```

```text
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

### Prompt 2.3: Pydantic Validation Schemas & DTO Contracts

```
[ METADATA ]
Target Artifact : backend/app/schemas.py
Role / Persona  : API Contract Specialist
Objective       : Define type-safe request and response Pydantic models
```

```text
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

## 4. Phase 3: Backend FastAPI REST Endpoints & Authentication

### Prompt 3.1: Cryptographic Authentication & Salted PBKDF2 Password Hashing

```
[ METADATA ]
Target Artifact : backend/app/routers/auth.py
Role / Persona  : Application Security Engineer
Objective       : Implement PBKDF2-HMAC-SHA256 password hashing and user onboarding
```

```text
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

### Prompt 3.2: E-Commerce Storefront CRUD Routers

```
[ METADATA ]
Target Artifact : backend/app/routers/ (products.py, cart.py, orders.py)
Role / Persona  : Full-Stack Backend Developer
Objective       : Implement transactional e-commerce operations with SQLAlchemy DI
```

```text
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

## 5. Phase 4: AI Shopping Assistant & Intent Orchestration Engine

### Prompt 4.1: Domain Catalog Knowledge Base & Spec Advancements

```
[ METADATA ]
Target Artifact : backend/app/services/ai_service.py
Role / Persona  : Conversational AI & E-Commerce Knowledge Engineer
Objective       : Construct structured catalog specifications and out-of-stock substitutes
```

```text
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

### Prompt 4.2: 23-Capability Natural Language Intent Processing Pipeline

```
[ METADATA ]
Target Artifact : AIService.process_message(...) in backend/app/services/ai_service.py
Role / Persona  : Natural Language Processing (NLP) Specialist
Objective       : Implement deterministic multi-tier intent matching across 5 capability levels
```

```text
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
  - Product Comparison Matrix: Compare two items (e.g. "Compare Samsung M35 and OnePlus Nord CE") across battery, camera, display, and price, with a definitive recommendation pick.
  - Smart Budget Recommendations with "Why?" rationale.
  - Out-of-Stock Alternatives: Propose substitutes for unavailable items.
  - Explain Product: Detailed pros, cons, and target workloads.
- Level 3 (Order & Cart Lifecycle):
  - Cancel Order: Live DB cancellation with status validation (reject if DELIVERED, confirm refund if PLACED).
  - Track Order: Milestone timeline (Placed, In Transit, Delivered) with carrier (BlueDart Express) and ETA.
  - 1-Click Reorder: Batch-clone past order items into active cart.
  - Update Cart Quantity ("Increase Samsung quantity to 3").
  - Remove from Cart ("Remove Samsung from cart").
  - Cart Summary ("How much will I pay?").
- Level 4 (Decision Support & Advisory):
  - Smart Budget Advisor: "I have ₹25,000. Which phone is best?".
  - Purchase Decision Support: "Should I buy Samsung M35 or wait?".
  - Requirement-based Search: Map activities (e.g. "coding + gaming") to hardware specs.
  - Gift Recommendations: "Gift for a college student under ₹5,000".
- Level 5 (Concierge & Personalization):
  - AI Shopping Concierge Setup Builder: "Build a complete setup under ₹60,000" -> Assemble Laptop + Earbuds + Smart Watch with bundle metadata.
  - Personalized Suggestions: Curate items matching user profile interest tags.
```

---

### Prompt 4.3: FastAPI Chat Execution Controller

```
[ METADATA ]
Target Artifact : backend/app/routers/chatbot.py
Role / Persona  : Backend API Engineer
Objective       : Route POST /chatbot/chat and inject database and user dependencies
```

```text
In `backend/app/routers/chatbot.py`:
- Implement `POST /chatbot/chat` accepting `ChatRequest` and returning `ChatResponse`.
- Inject `db: Session = Depends(get_db)` and `current_user_id: Optional[int] = Depends(get_current_user_id)`.
- Pass request message, user_name, interests, and resolved user_id to `ai_service.process_message(...)`.
- Return typed `ChatResponse` with response text, intent, action_taken, products, bundle, and comparison payloads.
```

---

## 6. Phase 5: Frontend Single Page Application (Angular 22)

### Prompt 5.1: Angular Reactive Core, Signals & Interceptors

```
[ METADATA ]
Target Artifact : app.config.ts, auth.ts, cart.ts, ai-chat.ts, auth.interceptor.ts
Role / Persona  : Principal Frontend Architect (Angular)
Objective       : Establish reactive signal-driven state management and standalone components
```

```text
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

### Prompt 5.2: Material Design Storefront Views

```
[ METADATA ]
Target Artifact : frontend/src/app/pages/ (login, signup, dashboard, products, cart, orders)
Role / Persona  : UI/UX Frontend Specialist
Objective       : Build responsive, accessible e-commerce storefront views
```

```text
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

## 7. Phase 6: Floating Chatbot Component & Material UI Integration

### Prompt 6.1: Floating Chat Window & Interactive Controls

```
[ METADATA ]
Target Artifact : frontend/src/app/components/chatbot/ (chatbot.ts, chatbot.html, chatbot.css)
Role / Persona  : Conversational UI Specialist
Objective       : Create floating Material chat interface with suggestion chips
```

```text
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

### Prompt 6.2: In-Chat Product Embeds, Bundle Cards & State Synchronization

```
[ METADATA ]
Target Artifact : In-Chat Actions & Signal Synchronization in chatbot.ts
Role / Persona  : Senior Frontend Engineer
Objective       : Render interactive product/bundle cards and sync navbar cart count
```

```text
Extend `chatbot.ts` and `chatbot.html` to support rich interactive UI widgets:

1. In-Chat Product Embeds:
   - When `msg.products` is present, render compact product cards with title, price, category, and an inline "Add" button invoking `cartService.addToCart(...)`.
2. Concierge Bundle Cards:
   - When `msg.bundle` is present, render a highlighted package card showing included devices, total bundle price, and a one-click "Add Setup to Cart" button.
3. Contextual Navigation Links:
   - Render "View Cart ->" or "View Orders ->" links based on message intent.
4. Automatic Reactive Cart Synchronization:
   - In `sendMessage()`, whenever the response contains `action_taken === 'cart_updated'`, `item_deleted`, or `order_created`, immediately invoke `cartService.refreshCartCount()` so the navbar badge updates without page reload.
5. Client-Side Fallback Resilience:
   - Implement `handleLocalQueryFallback(query)` to display cached products if backend network fails.
```

---

## 8. Phase 7: Native Voice Shopping & Web Speech API

### Prompt 7.1: Client-Side Speech Recognition Integration

```
[ METADATA ]
Target Artifact : initSpeechRecognition() & toggleVoiceInput() in chatbot.ts
Role / Persona  : Web Speech & Accessibility Engineer
Objective       : Implement browser-native speech-to-text without external cloud dependencies
```

```text
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

## 9. Phase 8: Conversational Evaluation Test Suite

### Comprehensive Conversational Validation Matrix

| Test ID | Capability Tested | Input Prompt (Type / Speak) | Expected System Action & Response |
|:---:|:---|:---|:---|
| **TC-01** | Greeting & Profile Awareness | `"Hi"` / `"Hello"` | Welcomes user acknowledging profile interest tags (e.g. Mobiles, Laptops). |
| **TC-02** | Product Comparison Matrix | `"Compare Samsung M35 and OnePlus Nord CE"` | Side-by-side spec comparison (Battery, Camera, Display, Price) + recommendation pick. |
| **TC-03** | Smart Budget Recommendation | `"I have ₹50,000 budget. Suggest a laptop."` | Recommends Acer Aspire 7 with explicit "Why?" rationale and remaining stock. |
| **TC-04** | Smart Budget Advisor | `"I have ₹25,000. Which phone is best?"` | Recommends Samsung M35 (6000mAh + 120Hz) and highlights Redmi Note 14 as alternative. |
| **TC-05** | Out-of-Stock Substitute | `"Add iPhone 16 to cart"` | Explains iPhone is unavailable; suggests in-stock substitutes (Samsung M35, OnePlus). |
| **TC-06** | Product Pros & Cons | `"Why should I buy HP Victus?"` | Displays suitable workloads, pros (144Hz, dual cooling) and cons (heavier chassis). |
| **TC-07** | Purchase Decision Support | `"Should I buy Samsung M35 or wait?"` | Generates decision matrix based on price stability, battery needs, and stock. |
| **TC-08** | Requirement-Based Search | `"I need a laptop for coding and gaming"` | Filters laptops with dedicated GPUs, multi-core CPUs, and thermal cooling. |
| **TC-09** | Gift Recommendations | `"Gift for a college student under ₹5,000"` | Suggests combo gift: Noise Smart Watch (₹2,499) + Boat Airdopes (₹1,299) under ₹5k. |
| **TC-10** | Concierge Setup Builder | `"Build a complete setup under ₹60,000"` | Assembles Laptop + Earbuds + Smart Watch bundle with total price and CTA. |
| **TC-11** | Add Setup Bundle to Cart | `"Add setup to cart"` | Adds all bundle items into active cart; navbar cart badge increments. |
| **TC-12** | Add Single Product to Cart | `"Add Samsung M35 to cart"` | Inserts CartItem in database; updates subtotal and increments navbar badge. |
| **TC-13** | Adjust Item Quantity | `"Increase Samsung quantity to 3"` | Mutates cart quantity in database; reports updated line item subtotal. |
| **TC-14** | Cart Bill Summary | `"How much will I pay?"` | Computes itemized breakdown, total count, and confirms free shipping. |
| **TC-15** | View Active Cart | `"Show my cart"` | Lists line items with quantities, prices, grand total, and "View Cart ->" link. |
| **TC-16** | Autonomous Checkout | `"Place order"` | Atomic transaction: converts cart into Order & OrderItems, clears cart, returns Order #. |
| **TC-17** | Live Order Tracking | `"Where is my order?"` | Displays Order #, Status, Carrier (BlueDart Express), ETA (2 Days), and timeline. |
| **TC-18** | Cancel Order | `"Cancel my order"` / `"Cancel order #1009"` | Validates status; updates DB status to CANCELLED and initiates refund. |
| **TC-19** | 1-Click Reorder | `"Order the same products as my last order"` | Reads items from latest order, re-inserts them into active cart, ready for checkout. |
| **TC-20** | Personalized Suggestions | `"Personalized suggestions for me"` | Queries database filtered by user's profile interests (e.g. Mobiles, Laptops). |
| **TC-21** | Hands-Free Voice Shopping | *Click Mic & speak:* `"Suggest a gaming laptop"` | Transcribes speech via Web Speech API, sends query, and displays recommended hardware. |

---

```
========================================================================================
AI Ecommerce Assistant • Enterprise Engineering Prompt Specification • Angular 22 & FastAPI
========================================================================================
```
