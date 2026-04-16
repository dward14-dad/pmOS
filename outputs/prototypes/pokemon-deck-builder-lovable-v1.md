# Lovable.dev Prototype Prompt: Pokemon Deck Builder for Kids

**Version:** v1  
**Date:** 2026-04-16  
**Source:** Verbal brief (no PRD yet)  
**Tool:** Lovable.dev  

---

## Paste this into Lovable.dev:

---

Build a fun, kid-friendly Pokemon TCG deck builder app called **"Deck Wizard"** that helps children scan their physical Pokemon cards and build a balanced battle deck using AI recommendations.

**Overview:**
Kids take photos of their physical Pokemon cards. An AI identifies each card and looks it up in the Pokemon TCG database. Once all their cards are loaded, a Deck Wizard AI analyzes what they have and builds them the best possible 60-card battle deck, explaining each choice in simple language a child can understand.

---

### Pages/Views

**1. Home Screen** (route: `/`)
- Big, colorful "Scan Your Cards!" CTA button
- "My Collection" button showing card count badge
- "Build My Deck!" button (disabled if fewer than 20 cards scanned)
- Fun Pokeball animated loading spinner used throughout the app
- Simple mascot character (a Pikachu silhouette or star icon) welcoming the user
- Background: subtle Pokeball pattern, bright and energetic

**2. Card Scanner** (route: `/scan`)
- Large camera viewfinder area (uses device camera via `getUserMedia`)
- "Take Photo" button (large, easy to tap)
- Upload from gallery fallback button ("Choose from Photos")
- After capture: show photo preview with "Looks Good!" and "Retake" buttons
- Processing state: animated Pokeball spinner with text "Identifying your card..."
- Result card showing: card name, type, HP, set name, rarity, card image from TCG API
- Confirm button: "Add to My Collection"
- Scan Another button
- If card cannot be identified: friendly error "Hmm, I couldn't read that card. Try better lighting or a flatter angle!"

**3. My Collection** (route: `/collection`)
- Grid of all scanned cards (card image thumbnails)
- Filter tabs: All | Pokemon | Trainer | Energy
- Each card shows: name, type icon, quantity badge if duplicates
- Tap a card to see full details (name, HP, attacks, abilities, set, rarity)
- Delete card button (with "Are you sure?" confirmation)
- Total card count shown at top: "You have X cards!"
- Empty state: "No cards yet! Go scan some."
- "Build My Deck!" FAB button at bottom right

**4. Deck Builder Loading** (route: `/building`)
- Full-screen animated loading state
- Pokeball spinning animation
- Rotating fun messages every 2 seconds:
  - "Analyzing your Pokemon..."
  - "Checking type matchups..."
  - "Finding the best energy balance..."
  - "Almost ready..."
- Transitions automatically to Deck Result when done

**5. My Deck** (route: `/deck`)
- Header: "Your Battle Deck is Ready!" with star/confetti animation on load
- Deck summary banner:
  - Pokemon count (target: 12-20)
  - Trainer/Item count (target: 10-18)
  - Energy count (target: 8-14)
  - Total: 60 cards
  - Visual balance bar showing the three sections with color coding
- Deck card list grouped by type (Pokemon / Trainers / Energy), each with card image and quantity
- "Why this deck?" expandable section per card group: simple explanation written for kids (e.g., "We picked 4 Charizard because he's your strongest attacker!")
- "Rebuild Deck" button (re-runs AI with same cards)
- "Start Over" button (clears everything, goes to Home)
- Share button: generates a simple text list of the deck for copying

---

### Data Model

**Card:**
- `id`: string (TCG API card ID)
- `name`: string
- `supertype`: "Pokemon" | "Trainer" | "Energy"
- `subtypes`: string[] (e.g., ["Basic", "Stage 1", "Item", "Supporter"])
- `hp`: number | null
- `types`: string[] (e.g., ["Fire", "Water"])
- `attacks`: { name, damage, text }[]
- `abilities`: { name, text }[] | null
- `set`: { name, series }
- `rarity`: string
- `images`: { small: url, large: url }
- `quantity`: number (how many the child has)
- `scannedAt`: timestamp

**Deck:**
- `id`: string
- `cards`: { cardId, quantity }[]
- `createdAt`: timestamp
- `reasoning`: { pokemon: string, trainer: string, energy: string } (AI explanations)

---

### User Flows

**Scan Flow:**
Home → Scan → Camera opens → Take photo → AI identifies card → TCG API validates + enriches → Preview card details → Confirm → Card added to Collection → Scan another or go to Collection

**Deck Build Flow:**
Collection (20+ cards) → Tap "Build My Deck!" → Building loading screen (3-5 seconds) → Deck result with 60-card recommendation → Review grouped deck list with AI reasoning → Optional: rebuild or share

**Error Flow:**
Scan → Card not identified → Friendly message + retry tips → Retake photo or skip

---

### AI Integration Points (mock with realistic dummy responses in prototype)

**Card Identification (Vision LLM):**
- Input: photo of card
- Output: card name, set name, card number (enough to look up in TCG API)
- Mock response for prototype: return "Charizard - Base Set - 4/102" style data

**Deck Builder (Text LLM):**
- Input: full list of available cards with counts
- Output: recommended 60-card deck as `{ cardId, quantity }[]` plus plain-English reasoning per group
- TCG deck rules enforced:
  - Exactly 60 cards total
  - Max 4 copies of any single card (except Basic Energy, which is unlimited)
  - Must include Basic Energy cards to power attacks
  - Recommended ratio: ~15 Pokemon / ~25 Trainers / ~20 Energy (adjust based on available cards)
- Mock response: pre-built sample deck using the sample data cards

---

### External APIs

**Pokemon TCG API** (`https://api.pokemontcg.io/v2/`)
- `GET /cards?q=name:{name}` — search by name after AI identification
- `GET /cards/{id}` — get full card details by ID
- No API key needed for basic use (100 req/day free; add key header for 1000/day)
- Use card data exactly as returned by API for accuracy

---

### Sample Data (use this to populate the prototype so it looks real)

Cards in collection:
1. Charizard ex (Obsidian Flames, #125) — Pokemon, Fire, HP 330 — qty: 1
2. Pidgeot ex (Obsidian Flames, #164) — Pokemon, Colorless, HP 280 — qty: 2
3. Arcanine ex (Obsidian Flames, #29) — Pokemon, Fire, HP 280 — qty: 2
4. Charmander (Obsidian Flames, #26) — Pokemon, Fire, HP 70 — qty: 4
5. Charmeleon (Obsidian Flames, #27) — Pokemon, Fire, HP 90 — qty: 2
6. Rare Candy (Paldea Evolved, #191) — Trainer/Item — qty: 4
7. Professor's Research (Sword & Shield, #178) — Trainer/Supporter — qty: 3
8. Boss's Orders (Rebel Clash, #154) — Trainer/Supporter — qty: 2
9. Nest Ball (Scarlet & Violet, #181) — Trainer/Item — qty: 4
10. Fire Energy (basic) — Energy — qty: 20
11. Double Turbo Energy (Astral Radiance, #151) — Special Energy — qty: 3

Sample deck output:
- Pokemon (14): 4x Charmander, 2x Charmeleon, 1x Charizard ex, 2x Arcanine ex, 2x Pidgeot ex, 3x [fill with basics]
- Trainers (26): 4x Rare Candy, 3x Professor's Research, 2x Boss's Orders, 4x Nest Ball, 13x [filler trainer cards]
- Energy (20): 17x Fire Energy, 3x Double Turbo Energy

---

### Style & Branding

- **Feel:** Playful, energetic, approachable for ages 6-14. Think "Pokemon game meets friendly wizard."
- **Colors:** 
  - Primary: Bright red (#E3350D) — Pokemon red
  - Secondary: Sunny yellow (#FFCB05) — Pikachu yellow
  - Accent: Deep blue (#003A70) — for contrast
  - Background: Light warm white (#FFFDF5)
  - Success green: #4CAF50
- **Typography:** Rounded, friendly font (Nunito or Poppins). Large font sizes (min 16px body, 24px+ headings). No tiny text anywhere.
- **Cards:** Card thumbnails with soft drop shadows and rounded corners (12px radius). Type-colored borders (fire=red, water=blue, grass=green, etc.)
- **Icons:** Emoji-style type icons for Pokemon types (🔥 Fire, 💧 Water, 🌿 Grass, ⚡ Electric, etc.)
- **Buttons:** Large, rounded pill buttons. Easy tap targets (min 48px height).
- **Animations:** Subtle and fun. Pokeball spin on loading. Bounce on card add. Confetti on deck complete.

---

### States

- **Empty collection:** Illustration with "Scan your first card to get started!" and big scan button
- **Loading (scan):** Pokeball spinner + "Identifying your card..." message
- **Loading (deck build):** Full-screen with rotating encouraging messages
- **Error (card not found):** Friendly illustration + tips for better photos + retry button
- **Success (card added):** Card flips in with a satisfying bounce animation
- **Deck complete:** Confetti burst + "Your deck is ready to battle!" headline

---

### Out of Scope for This Prototype

- User accounts or login
- Saving multiple decks
- Actual camera AI call (mock the vision response)
- Actual LLM deck builder call (mock with pre-built sample deck)
- Multiplayer or social features
- Card trading or marketplace
- Tournament legality checking

---

### Important Notes

- This is for kids. Every piece of copy should be simple, encouraging, and fun.
- Never show raw API errors. Always translate to child-friendly messages.
- The AI reasoning for deck choices must be written at a 4th-grade reading level.
- Make the scan flow feel magical — the moment a card is identified should feel satisfying.

---

## Requirements Coverage

*No formal PRD exists — requirements based on verbal brief from 2026-04-16*

- [x] Camera/photo capture to scan physical cards
- [x] LLM vision identification (mocked in prototype)
- [x] TCG API validation and data enrichment
- [x] Card collection/inventory management
- [x] LLM-powered deck builder (mocked in prototype)
- [x] Correct deck distribution logic (Pokemon / Trainer / Energy ratio)
- [x] Kid-friendly UI and copy
- [ ] Actual LLM API calls — deferred (prototype mocks AI responses)
- [ ] User accounts / persistence across sessions — out of scope for prototype
- [ ] Tournament legality / format validation — out of scope for prototype

---

## Next Steps

1. Paste the prompt above into [Lovable.dev](https://lovable.dev)
2. Review the generated app against the 5 key screens
3. Run `/prototype-feedback` to do a structured review
4. Use `/prd-draft` to formalize requirements before engineering handoff
5. For real LLM integration, use Claude API (vision for card ID, text for deck builder)
