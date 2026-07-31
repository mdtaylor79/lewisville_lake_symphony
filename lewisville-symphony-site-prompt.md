# Full Build Prompt — Lewisville Lake Symphony Website Redesign

## Project Overview

Create a complete, single-file HTML website mockup for the **Lewisville Lake Symphony** (lewisvillesymphony.org). The current site is built on Wix and feels dated, cluttered, and unprofessional. The goal is a modern, light, elegant redesign inspired by top-tier symphony organization websites (LA Philharmonic, Dallas Symphony Orchestra, New York Philharmonic). The output is a fully scrollable, browser-ready HTML file with no external dependencies beyond Google Fonts and Unsplash images.

---

## Design Philosophy

- **Light and airy** — white and cream backgrounds dominate; darkness is used sparingly for contrast and drama
- **Editorial hierarchy** — every section has a clear label, title, and supporting text; no visual clutter
- **Classical but modern** — serif display fonts for elegance, clean sans-serif for readability
- **Action-oriented** — every section has a visible CTA; tickets and donations are never more than one click away
- **Content-first** — real concert dates, artist names, venues, and program details from the actual site populate all sections

---

## Typography

- **Display / Headlines:** `Playfair Display` (Google Fonts) — weights 400, 600, 700; use italic variant for emphasis where appropriate
- **Body / UI:** `Inter` (Google Fonts) — weights 300, 400, 500, 600
- Load both via a single `<link>` tag from Google Fonts

---

## Color Palette

```
--navy:    #0D1B2A   /* Primary dark — nav, footers, buttons */
--navy-md: #1A2E45   /* Secondary dark — hover states, gradients */
--gold:    #C9A84C   /* Accent — CTAs, labels, highlights */
--gold-lt: #E8C96A   /* Gold hover state */
--cream:   #FAF8F4   /* Warm off-white section backgrounds */
--gray-lt: #F4F2EE   /* Light gray for cards, stats bar */
--gray:    #6B7280   /* Body text, subtitles */
--text:    #1C1C1E   /* Primary text */
--white:   #FFFFFF
```

---

## Component Library

Define these reusable CSS classes before building sections:

- `.btn` — base button with padding, border-radius, font-weight, letter-spacing, transition
- `.btn-gold` — gold background, navy text
- `.btn-outline-white` — transparent with white border (for use on dark backgrounds)
- `.btn-outline-navy` — transparent with navy border (for use on light backgrounds)
- `.btn-navy` — navy background, white text
- `.section-label` — 11px, 600 weight, gold color, 0.16em letter-spacing, uppercase
- `.section-title` — Playfair Display, clamp(28px, 4vw, 42px), navy, line-height 1.2
- `.container` — max-width 1200px, centered, 24px horizontal padding
- `.tag` — small inline label with gold border and text
- `.card` pattern — white background, border-radius 10px, subtle box-shadow, hover lift animation

---

## Page Sections (in order)

### 1. Announcement Bar
- Full-width, navy background, 10px vertical padding
- 13px white text, centered
- Two announcements separated by `·`:
  - "Internship applications open through August 31, 2026" with gold "Apply Now →" link
  - "Free Scout merit badge program available this season" with gold "Learn More →" link

---

### 2. Sticky Navigation
- Sticky top, white background, 1px bottom border, subtle box-shadow
- Height: 72px
- **Left:** Logo lockup — "Lewisville Lake Symphony" in Playfair Display 18px bold navy, below it "Lewisville, Texas · Est. 1985" in 10px gold uppercase tracked text
- **Center:** Nav links — `Concerts & Tickets`, `Season`, `Youth Programs`, `Competitions`, `About`, `Visit` — 13.5px Inter 500, hover shows light gray background
- **Right:** "Donate" text link (gray) + "Get Tickets" gold button

---

### 3. Hero Section
- Height: 92vh, min 580px, max 860px
- Background image: full-bleed orchestra/concert photo (use Unsplash: `photo-1507838153414-b4b713384a76`)
- Gradient overlay: bottom-heavy, `rgba(10,20,35,.92)` at bottom → `rgba(10,20,35,.15)` at top
- Content anchored to bottom-left:
  - Season tag: gold line + "2026–27 Concert Season" uppercase label
  - H1: "Great Music. / Right Here in / Lewisville." — Playfair Display, clamp(38px, 6vw, 72px), white, bold
  - Subtitle: "World-class orchestral performances and chamber concerts — designed for our community." — 17px, light weight, 72% white opacity
  - Two CTAs: gold "Get 2026–27 Tickets" + outline-white "Explore the Season"
- Bottom-right: animated scroll indicator (bouncing down arrow + "SCROLL" label)

---

### 4. Stats Bar
- Background: `--gray-lt`
- 4-column grid
- Stats: `40+` Years of Live Music · `8` Concerts This Season · `4` Free Chamber Concerts · `DFW` North Texas's Orchestra
- Each stat: large Playfair Display number (42px, navy), smaller Inter label below

---

### 5. Featured Concert (Opening Night)
- Background: `--cream`
- Two-column layout: image left, content right
- **Image:** Unsplash piano photo (`photo-1520523839897-bd0b52f945a0`), 4:3 ratio, rounded, shadowed
- **Notice card** above the two columns: gold-tinted background, "2027 Vernell Gregg Young Artists Competition — Now Accepting Applications" with links to repertoire and guidelines
- **Content:**
  - Section label: "Opening Night · Symphony Series"
  - Date badge: navy pill "October 9, 2026 · 7:30 PM" + venue text "Lewisville Grand Theater"
  - Title: "Rachmaninoff Piano Concerto No. 1 & Haydn's 'Clock' Symphony"
  - Description paragraph about the concert
  - Soloist card: white box with gold left border, avatar initials circle (SD), name "Steven Dong, Piano", role "Grand Prize winner, 2026 International Competition for Piano"
  - CTAs: gold "Buy Tickets" + outline-navy "Program Notes"

---

### 6. Symphony Series Concert Grid
- Background: white
- Section header: label "Symphony Series · Lewisville Grand Theater", title "2026–27 Orchestra Concerts", subtitle "Friday evenings at 7:30 PM · 100 N. Charles St., Lewisville TX", right-aligned "View full season →" gold link
- **4-column card grid:**

  | Date | Title | Subtitle / Artists |
  |---|---|---|
  | Oct 9, 2026 | Rachmaninoff & Haydn's "Clock" | Steven Dong, Piano |
  | Nov 13, 2026 | Capriccio Espagnol & Orchestral Favorites | Rimsky-Korsakov, Bizet, Grieg, Dvořák |
  | Feb 5, 2027 | Bokyung Byun, Guitar | Clarice Assad's O Saci-Pererê & Vivaldi Concerto in D |
  | Apr 9, 2027 | Mozart's "Haffner" Symphony | Plus: Winner of the 2027 Vernell Gregg Young Artists Competition |

- Each card: photo or dark placeholder with musical note character, gold date label, Playfair title, gray subtitle, navy "Buy Tickets" button (turns gold on hover)
- Card hover: translateY(-4px) lift + stronger shadow
- **Below the grid:** a gray-lt subscription banner — "Save with a Season Subscription" text + "Subscribe & Save" gold button + "Group Tickets" outline button

---

### 7. International Chamber Series
- Background: `--navy` (full dark section)
- Section label in gold, title in white: "World-Class Chamber Music — Free & Open to All"
- Description: partnership with UNT College of Music, venue info
- Gold badge: "All Concerts Free Admission"
- **4-item vertical list** — each row is a grid: date block | artist info | details button
  - Date block: rounded box with gold border, day name / large number / month-year
  - Artist info: Playfair Display artist name (white), subtitle in 50% white
  - Button: outline style (gold border, gold text), turns gold-filled on hover

  | Date | Artist | Note |
  |---|---|---|
  | Fri Sep 25, 2026 | Daeun Han, Piano | Opening evening |
  | Tue Dec 29, 2026 | TL Piano Duo — Taeyu Kwon & Laehyung Woo | Holiday season |
  | Fri Jan 22, 2027 | Yuehong Zhu, Piano | Solo piano masterworks |
  | Fri Mar 19, 2027 | Yejin Lee, Soprano | Season finale |

---

### 8. Special Family Event — Peter & the Wolf
- Background: `--cream`
- Two-column: content left, image right
- Date: Saturday, March 6, 2027 · 3:00 PM
- Venue: Lamb of God Lutheran Church, 1401 Cross Timbers Rd., Flower Mound TX 75028
- Narrated by Chip Waggoner · Choreography by Kelly Lannin · Staged by Janet Waters
- Members of LakeCities Ballet Theatre
- Unsplash ballet/performance image (`photo-1547153760-18fc86324498`)
- Gold "Get Tickets" button

---

### 9. Youth & Education
- Background: `--cream`
- Two-column: stacked images left (main + overlapping accent image), content right
- Main image: young musicians (`photo-1544531585-9847b68c8c86`); accent image: orchestra (`photo-1507838153414-b4b713384a76`)
- Accent image positioned absolutely: bottom-right of the stack, 48% width, white border, shadow
- **Three education items** (icon + heading + text):
  1. 🎓 **Internship Program** — Fall 2026 positions open through August 31
  2. 👤 **Scout Merit Badge Program** — Free program for Scouts of America & Girl Scouts
  3. ⭐ **Vernell Gregg Young Artists Competition** — Winner performs with full orchestra April 2027
- Icons: 44×44 navy rounded squares with gold SVG icons
- CTAs: "Youth Programs" gold button + "Apply for Internship" outline button

---

### 10. Competitions Section
- Background: white
- Two-column: content left, visual card right
- **Content:**
  - Label: "Annual Competition"
  - Title: "Vernell Gregg Young Artists Competition 2027"
  - Description paragraph
  - Detail rows (bold label + value): Opens · Deadline · Performance
  - CTAs: "2027 Repertoire" gold + "Competition Guidelines" outline
- **Visual card:** dark navy gradient box with decorative circles (pseudo-elements), trophy emoji, heading "A Stage for Tomorrow's Stars", subtitle, "Apply on ACCEPTD" gold button

---

### 11. Support / Donate Banner
- Background: white with a faint orchestra image overlay (7% opacity)
- Centered text layout, max-width 640px
- Title: "Help Us Keep Live Music Alive in Lewisville"
- Description: 501(c)(3) nonprofit, what donations fund
- Three CTAs: "Make a Donation" navy button · "Volunteer With Us" gold button · "Corporate Giving" outline button

---

### 12. Sponsors Row
- Background: white
- Centered uppercase label: "Proudly supported by our partners"
- Flex row of sponsor logo placeholders (gray-lt boxes with uppercase text):
  City of Lewisville · NTTA · UNT College of Music · Lewisville ISD · plus 3 generic "Sponsor Name" slots

---

### 13. Newsletter Signup
- Background: `--navy`
- Two-column flex: left = headline "Stay in the Loop" (Playfair, white) + subtext; right = email input + gold subscribe button
- Input: semi-transparent dark background, white text, gold border on focus

---

### 14. Footer
- Background: `#080F18` (deepest navy)
- **4-column grid:**
  - **Col 1 (2fr):** Brand — Playfair logo name, gold tagline "Great Music · Nearby", description paragraph, address (1301 Justin Road, Suite 201, PMB 461, Lewisville TX 75077), phone (972.874.9087)
  - **Col 2:** "Concerts" links — Symphony Series, Chamber Series, Special Events, Events Calendar, Buy Tickets, Group Tickets
  - **Col 3:** "Education" links — Youth Programs, Internships, Merit Badges, Young Artists Competition, Volunteer
  - **Col 4:** "About" links — Our Mission, Music Director, The Musicians, Board of Directors, Our Sponsors, Equity & Diversity, Contact Us
- **Footer bottom:** thin top border, copyright left, social icon links right (Facebook, Instagram, YouTube, Email) — circular buttons, gold on hover

---

## Technical Specs

- **Single file** — all CSS in `<style>`, no external stylesheets, no JS frameworks
- **No JavaScript required** — pure CSS hover states and transitions
- **Google Fonts** — load via `<link>` in `<head>`: Playfair Display (ital,wght@0,400;0,600;0,700;1,400;1,600) + Inter (wght@300;400;500;600)
- **Images** — all from Unsplash CDN with `?auto=format&fit=crop&w=XXX&q=80` params; use `aspect-ratio` CSS for correct sizing
- **Responsive base** — use `clamp()` for fluid type sizes; grid layouts defined in CSS
- **Smooth scroll** — `scroll-behavior: smooth` on `html`
- **Custom scrollbar** — 6px, navy thumb, cream track
- **CSS variables** — all colors defined as `--var` on `:root`
- **Hover animations** — cards lift with `translateY(-4px)` + shadow; buttons transition color/background over 0.15–0.18s

---

## Unsplash Image URLs Used

| Purpose | URL fragment |
|---|---|
| Hero (orchestra) | `photo-1507838153414-b4b713384a76` |
| Piano / opening concert | `photo-1520523839897-bd0b52f945a0` |
| Guitar / Feb concert | `photo-1558618666-fcd25c85cd64` |
| Support banner overlay | `photo-1519683109079-d5f539e1542f` |
| Youth programs main | `photo-1544531585-9847b68c8c86` |
| Peter & the Wolf | `photo-1547153760-18fc86324498` |

All image URLs follow the pattern:
```
https://images.unsplash.com/[photo-id]?auto=format&fit=crop&w=[width]&q=[quality]
```

---

## Content Reference — Real Data from lewisvillesymphony.org

**Organization:**
- Full name: Lewisville Lake Symphony Association, Inc.
- Address: 1301 Justin Road, Suite 201, PMB 461, Lewisville, Texas 75077
- Phone: 972.874.9087
- Email: question@lewisvillesymphony.org
- Social: Facebook (LewisvilleLakeSymphony)

**Symphony Series** — Lewisville Grand Theater, 100 N. Charles St., Lewisville TX, Fridays at 7:30 PM:
- Oct 9, 2026 — Rachmaninoff Piano Concerto No. 1 (Steven Dong, piano) + Haydn's "Clock" Symphony
- Nov 13, 2026 — Capriccio Espagnol + favorites by Rimsky-Korsakov, Bizet, Grieg, Dvořák
- Feb 5, 2027 — Bokyung Byun (guitar); Clarice Assad's O Saci-Pererê + Vivaldi Concerto in D
- Apr 9, 2027 — Mozart's "Haffner" Symphony + winner of 2027 Vernell Gregg Competition

**International Chamber Series** — Trinity Presbyterian Church, 5500 Morriss Rd., Flower Mound 75028, Fridays 7:30 PM, FREE:
- Sep 25, 2026 — Daeun Han, piano
- Dec 29, 2026 — TL Piano Duo (Taeyu Kwon & Laehyung Woo)
- Jan 22, 2027 — Yuehong Zhu, piano
- Mar 19, 2027 — Yejin Lee, soprano

**Special Events:**
- Peter & the Wolf — Sat March 6, 2027, 3:00 PM, Lamb of God Lutheran Church, 1401 Cross Timbers Rd., Flower Mound TX 75028. Narrated by Chip Waggoner. Members of LakeCities Ballet Theatre. Choreography by Kelly Lannin. Staged by Janet Waters.

**Competitions:**
- 2027 Vernell Gregg Young Artists Competition — Opens Aug 15, 2026 on ACCEPTD. Deadline Dec 30, 2026. Winner performs April 9, 2027.

**Internships:**
- Fall 2026 intern applications open through August 31, 2026 (or until filled). Spring 2027 reopens after.

**Youth:**
- Free Scout merit badge program for Scouts of America and Girl Scouts

**Ticket Sales:** https://www.tix.com/ticket-sales/lewisvillesymphony/3459

---

## What to Avoid (Problems with Current Site)

- ❌ Dark, heavy background on the main content area
- ❌ Unstructured, repetitive image slideshows with no context
- ❌ All-caps body text that's hard to read
- ❌ Inconsistent section spacing and alignment
- ❌ No visual hierarchy between sections
- ❌ Buried CTAs — "Buy Tickets" is hard to find
- ❌ No clear differentiation between Symphony Series and Chamber Series
- ❌ No featured soloist profiles or storytelling
- ❌ Sponsor logos displayed with inconsistent sizing and alignment
- ❌ Contact info scattered and hard to find

---

---

# PAGE 3: Donate & Give (`/donate`)

> Sources: /copy-of-giving + /donors merged into one page
> File: `lewisville-symphony-donate.html`

## Page Overview

The current site splits donations across two pages (/copy-of-giving and /donors) with no visual hierarchy, buried pricing, and plain text lists. This redesign merges both into a single comprehensive giving page — structured like a nonprofit's professional development page. Every giving pathway is clearly presented with benefits, pricing, and a direct contact/action path.

---

## Data: Donor Levels (all cumulative — each level includes levels below)

| Level | Minimum | Key Benefits |
|---|---|---|
| Musician's Circle | $100 | Name in Symphony Series programs · Invitation to Appreciation Event & Annual Meeting |
| Concertmaster's Circle | $250 | + Voucher for 2 guest tickets (Symphony Series, space available) |
| Conductor's Circle | $500 | + Invitation to Conductor's Dinner · 2 additional guest tickets |
| Bronze Baton | $750 | + On-stage rehearsal seating in section of choice (by request) |
| Silver Baton | $1,000 | + International Chamber concert sponsorship · Backstage tour of MCL Grand Theater |
| Gold Baton | $2,500 | + Concert sponsorship with program/signage recognition |
| Platinum Baton | $5,000 | + Season sponsorship at opening concert + printed programs/signage all season |
| Symphony Visionary | $10,000+ | + Private recital in your home (by request) |

"By Request" benefits coordinator: Nancy Wright — info@lewisvillesymphony.org

---

## Data: Chair Sponsorship Pricing

| Chair | Price |
|---|---|
| Principal Chair | $350 |
| Concertmaster's Chair | $400 |
| Associate Conductor Directorship | $550 |
| Conductor's Podium | $600 |

- French horn chair available for 2026-27 ($400)
- First-come, first-served
- Contact: info@lewisvillesymphony.org
- Naming examples: "The John & Mary Smith Chair", "The Kim Chiu Memorial Chair", "The ABC Company Chair"

---

## Data: Program Advertising

| Size | Dimensions | Price |
|---|---|---|
| Business Card | Business card size | $150/season |
| Third Page | 4.5" × 2.25" | $300/season |
| Half Page | 4.5" × 3.5" (color) | $500/season |
| Full Page | 4.5" × 7.5" (color) | $1,000/season |

---

## Data: Concert Sponsorships

- Available for Symphony, Chamber, and Pops series, and individual concerts
- Co-sponsors must be from different business segments
- Maximum 4 co-sponsors per series or event
- Contact for pricing: 972.874.9087 or info@lewisvillesymphony.org

---

## Data: Smart Giving Strategies

- **Corporate matching**: Many employers match donations to nonprofits — LLS can provide 501(c)(3) status, EIN, and documentation
- **Stock donation**: Donate appreciated stock to a charitable fund (Schwab/Fidelity), recommend a grant to LLS — converts capital gains to tax deductions

---

## Page Sections

### 1. Announce Bar
- "The LLS is a 501(c)(3) nonprofit — all gifts are tax deductible" + gold link to contact about corporate matching

### 2. Nav
- "Donate" nav link highlighted in gold (not gray) to indicate current section

### 3. Page Hero
- Background: navy with faint orchestra image overlay (10%)
- 501(c)(3) tag badge (gold-bordered pill)
- H1: "Support the Music That Moves You"
- Subtext about making world-class music accessible
- CTAs: "Make a Donation" (anchors to #give) + "Sponsor a Chair" (anchors to #chair)

### 4. Impact Stats Bar
- Full-width gold bar, 4 stats: 40+ Years · 8 Concerts · 1,000s Students · $0 Chamber Admission
- White dividers between stats

### 5. Ways to Give (3 cards)
- Navy primary card: Individual Donation → links to #donor-levels
- White card: Sponsor a Chair → links to #chair
- White card: Corporate Giving → links to #corporate
- Below: gray strip noting check mailing address

### 6. Donor Levels (2 rows of 4 cards)
- **Row 1** (white cards): Musician's Circle, Concertmaster's Circle, Conductor's Circle, Bronze Baton
- **Row 2** (dark navy cards, `.featured` and `.top`): Silver Baton, Gold Baton, Platinum Baton, Symphony Visionary
- Each card: level label, name (Playfair), gold price, cumulative perks with gold ✓ checkmarks
- "All above, plus:" divider line between inherited and new benefits
- Below grid: "Donate Now" gold button + note about Nancy Wright for "By Request" scheduling

### 7. Chair Sponsorship (2-column)
- **Left:** Explanatory content + naming examples list + available chairs for 2026-27 (French horn, $400) + contact note
- **Right:** Dark navy pricing table (4 tiers), contact note, "View Orchestra Page" outline button

### 8. Corporate Sponsorships + Program Advertising (2-column)
- **Left:** Concert sponsorship explanation + 4-co-sponsor rule note + phone/email CTA buttons
- **Right:** Advertising rate table (4 rows: size, dimensions, price in gold Playfair)

### 9. Smart Giving Strategies (2 cards)
- Dark navy card: Corporate Matching
- White card: Stock Donation / Capital Gains Strategy

### 10. Donate CTA
- Navy background with faint image overlay
- Centered: "Ready to Make a Gift?" + 3 CTA buttons (Donate by Email, Call, Sponsor a Chair)
- Footer tax note: "501(c)(3) · All gifts tax deductible"

---

---

# PAGE 4: About Us (`/about`)

> Sources: /our-mission, /music-director, /assistantconductor, /copy-of-assistant-conductor, /orchestra, /board-of-directors, /copy-of-board-of-directors, /copy-of-contact-us (Equity & Diversity)
> File: `lewisville-symphony-about.html`

## Page Overview

All "About Us" subpages are combined into a single scrollable page with a sticky submenu bar that updates the active link as the user scrolls between 8 anchor sections. Each section is a full-width layout matching the design system, alternating cream/white backgrounds.

---

## Sticky Submenu

- Sits immediately below the main nav (top: 72px, z-index: 90)
- White background, gray-lt bottom border, subtle shadow
- 8 horizontal links: Our Mission · Music Director · Asst. Conductor · Executive Director · The Musicians · Board of Directors · Our Sponsors · Equity & Diversity
- Active link: navy color + 2px navy bottom border + bold weight
- Horizontal scroll on small screens (no visible scrollbar)

---

## Section 1 — Our Mission (id="mission", white)

**Mission statement:**
"The Lewisville Lake Symphony is dedicated to enhancing the quality of life for people of all ages in North Texas through live and inspiring classical music. The symphony is committed to educating young audiences and supporting rising talent."

**Body text:**
Since 1984. Four symphony concerts + four chamber concerts per season. Peter & the Wolf family events. Educational outreach: concert for every 3rd grader in LISD, internships (middle school → university), competitions with scholarships. Scout merit badge program. Underserved children and adults at no cost. "More than concerts, we're building a vibrant, inclusive community through music."

**3 mission stats:** 40+ Years · 8 Concerts per season · 1,000s Students reached annually — displayed as white cards in a 3-column grid

---

## Section 2 — Music Director (id="music-director", cream)

**2-column layout:** image placeholder left (3:4 ratio, navy gradient) + content right

**Adron Ming:**
- Photo credit: © 2026 Nikki Dunnahoo Photography
- Dallas Morning News pull-quote (gold left border, gray-lt background)
- Bio: Native of Weslaco TX · Master's in music theory from Baylor · studied cello with Lev Aronson, conducting with Daniel Sternberg · Baylor faculty (music theory instructor, asst conductor Baylor & Waco Symphonies) · UNT (studied with Anshel Brusilow) · Bethel College MN (asst professor + conductor Bethel Chamber Symphony) · Conducted: Toledo Symphony, Taipei Sunshine Symphony, Plano Symphony, Irving Symphony, Chamber Symphony of the Metrocrest, New Philharmonic of Irving · Associate conductor Richardson Symphony until 2010 · Director String Orchestra at UTD since 2016

---

## Section 3 — Assistant Conductor (id="asst-conductor", white)

**Same 2-column layout**

**Nathan Howard:**
- Pursuing Doctorate at UNT under Maestro David Itkin
- Graduate studies at SMU → resident conductor Meadows Symphony Orchestra
- Indiana University Jacobs School of Music → New Music Ensemble recordings
- Music Director: Camp-of-the-Woods jazz band
- Conducted: Lviv National Philharmonic, Meadows Symphony Orchestra, Samford University Orchestra
- Teachers: Paul C. Phillips, Jack Delaney, Michelle Merrill

---

## Section 4 — Executive Director (id="exec-director", cream)

**Nancy Wright:**
- Became first Executive Director in 2024
- Previous involvement: flutist, then active volunteer
- BM + MM in flute performance from University of Houston and West Texas A&M
- Studied with Byron Hester and Gary Garner
- IBM career: technical support → project & people management through retirement
- Contact button: "Contact Nancy →" → info@lewisvillesymphony.org
- Photo credit: © 2026 Nikki Dunnahoo Photography

---

## Section 5 — The Musicians (id="musicians", white)

**Leadership row** (2-column navy cards):
- Adron Ming, Music Director/Conductor · Friends of the Music Director Chair
- Ella Castro, Assistant Conductor · Friends of the Assistant Conductor Chair

**Full orchestra roster in 3-column grid** (Strings | Woodwinds | Brass/Perc/Keys):

**Strings:**
- First Violins: Tonda Sykes (Concertmaster, Pamela Mia Paul Chair), Emily Aquin (Assoc. Concertmaster, Pamela Mia Paul Chair), Lucia Neaga, Rob Flickinger, Kristin Van Cleve, Lisa Shields, Tami Peterson, Cassandra Lin
- Second Violins: Susan Younghans (Principal, Harvey Wechsler Memorial Chair), Mia Catania, Janetta Tang, Klaudia Cop, Chris Chapin, Julianne Booth, Suneetha D'Apice, Hallie Michaels
- Violas: Jennifer Sweetman (Principal, Schuitema Family Chair), Cornelia Harris, Tonia Pilliod, Iris Messenger, Eric Jones, Stephen Beall
- Cellos: Dan Lewis (Principal, Paul & Marjory Vickery Memorial Chair), Kyle Rosenquist, Hsinyi Wang, Hamin Kim, Brooke Scholl, Vilma Peguero
- Basses: David Shaw (Principal, Vernell T. Gregg Chair), Brian Peacock, Michael Lelevich, Joel MacMillan

**Woodwinds:**
- Flutes: Jackie Akin (Principal, Green Family Chair), Jennifer McElroy
- Piccolo: Jennifer McElroy (Christine Hotchkiss Chair)
- Oboes: Sally Bohls (Principal, Fred and Diane Busche Chair), Sharon Lacey
- English Horn: Sharon Lacey (Martha Cecile Storrie M.D., R.Ph. Chair)
- Clarinets: Kenneth Krause (Principal, Rogers Family Chair), John Scott
- Bass Clarinet: Doug Obst
- Saxophone: Don Fabian (Martin Family Chair)
- Bassoons: Charlie Hall (Principal, Dan Wittington Memorial Chair), Ralph Morgan
- Contra Bassoon: Jeff Strong

**Brass / Percussion / Keys:**
- French Horns: Daniel Serrago (Principal, Amber Busche Memorial Chair), Nancy Piper, Heather Suchodolski, Chrystal Stevens
- Trumpets: Bert Truax (Principal, anonymous donor Chair), Richard Hall
- Trombones: James McNair (Principal, McMillin Family Chair), Jonathan Gill
- Bass Trombone: Jon Bohls (Alex McDonald Chair)
- Tuba: Carl Kleinsteuber (Marguerite Lamp Memorial Chair)
- Timpani: Steven Kimple (Rev. Dr. Byron & Margaret Wells Chair)
- Percussion: David Elias (Principal, Susan and Dave Mullins Chair), Michael McNicholas
- Harp: Kimberly De Rosa (Bill and Grace Lawrence Chair)
- Keyboard: Heejung Kang (Howard Glenn Schmidt Memorial Chair)
- Production Manager: David Elias

**Friends sponsorship strip below roster:**
- Friends of Music Director Chair: Ronnie & Lisa Lingren, Pamela Mia Paul, Deborah Svedman, Nancy Wright
- Friends of Assistant Conductor Chair: Jamie & Susan Martin, Pamela Mia Paul
- "Sponsor a Chair →" button

---

## Section 6 — Board of Directors (id="board", cream)

**2-column grid:**

**Left column:**
- Board of Directors with roles: Deborah Svedman (Chair), Jamie Martin (Vice-Chair & Treasurer), Susan Martin (Secretary), Sally Bohls (Player Rep), plus 12 at-large members: Jennifer Clay, Kevin Geise, Charles Ku DDS, Ronnie Lingren, Kyle McKay, Diana McMillin, Don Rogers, Drew Sutherland, Marcus Taylor, Rosalyn Taylor, Margaret Wells, Carol Wilson
- Ex-Officio (non-voting): Adron Ming (Music Director), Nancy Wright (Exec Director)

**Right column:**
- Active Honorary: Sara Abell, Grace Lawrence, Pamela Paul
- Honorary Wise Council (with titles): Dr. Warren Henry (UNT College of Music, Sr. Assoc. Dean), Kelly Lannin (Artistic Director, LakeCities Ballet Theatre), Hon. Jane Nelson (Texas Secretary of State), Morris Salerno (Owner & Executive Chef, Bistecca Steakhouse)
- Honorary Emeritus (with explanation paragraph + † for deceased): Ian & Lyn Cleghorn, Leland Mebine†, Mary Mebine†, Lee Vander Waal†, Marjory & Paul Vickery†, Martha Whitescarver†

---

## Section 7 — Our Sponsors (id="sponsors", white)

- Description paragraph
- Sponsor logo boxes in flex-wrap row (gray-lt boxes with text placeholders — actual logos are images on site)
- "Interested in becoming a sponsor?" + gold CTA button

---

## Section 8 — Equity & Diversity (id="equity", cream)

**Full statement:**
"The Lewisville Lake Symphony is committed to the principles of equity, racial equality, and diversity when hiring orchestral musicians and guest artists and in the audiences we serve. We are committed to including all individuals regardless of race, nationality, gender, age, sexual orientation, or sexual identification both as performers and audience members. We believe that fully utilizing the talents of all individuals allows us to use our concert and outreach programs to foster and strengthen artistic connections within the greater DFW community and beyond."

**3 pillar cards below:** Diverse Programming · Accessible Education · Inclusive Hiring

---

---

# PAGE 5: Youth Programs (`/youth-programs`)

> Source: /youth-programs
> File: `lewisville-symphony-youth.html`

## Page Overview

A warm, energetic page that makes the three youth programs immediately clear (Interns, Associates, Scouts), tells the mission story well, and drives eligible students to apply. The deadline/application CTA is pinned at the top in the announce bar AND repeated at the bottom in a full-width apply section.

---

## Program Data

### Symphony Interns
- Eligibility: Grades 8–12
- Duration: Two-semester commitment (standard)
- What they do: Assist the House Front team at Symphony Series concerts
- Benefit to intern: Community service credit hours + on-stage seating at final rehearsals with the professional orchestra under Maestro Adron Ming
- Mission: "Foster the long-term enjoyment of great music and encourage student musicians."
- Quote: Margaret Wells, Chair of LLS Civic Relationships Group

### Symphony Associates
- Eligibility: Students who completed the Intern program
- Duration: Through college graduation
- Pathway: Standard = 2 semesters as Intern → become Associate; Fast-track = final-semester seniors may become Associate after just 1 intern semester
- What they do: Provide concert assistance each season

### Scout Merit Badge Program
- Who: Scouts of America (including Cub Scouts) and Girl Scouts
- Cost: Free
- What: Guided engagement with live orchestra to fulfill music-related merit badge requirements
- PDF details: https://www.lewisvillesymphony.org/_files/ugd/1dd4b7_598d4af0cb114095a86d4f04ad5dca92.pdf

### Application Info
- Fall 2026 application deadline: August 31, 2026 (or until filled)
- Program closes until Spring 2027 after deadline
- Application download: https://www.lewisvillesymphony.org/_files/ugd/1dd4b7_c7b20f39c73c4e22b81edb8361944535.docx

---

## 2025–26 Roster

**Interns:** Sahana Sudhagar, Sahasra Sudhagar, Selina Jin, Ishaana Vishwanath

**Associates:** Leah Brown, Ethan Chen, Jordan Clay, Ava Hong, Satvik Kolathaya, Iris Lewis, Matthew Jacob, Eugenia Jin, Benedict Juba, Shravya Kasturi, Matthew Maliyil, Moukthika Palli, Anamarie Sutiono, Aveline Sutiono, Adhira VinothKumar

---

## Page Sections

### 1. Announce Bar
- "Fall 2026 Intern applications accepted through August 31, 2026" + gold "Apply Now →" link to application docx

### 2. Nav
- "Youth Programs" link gets `.active` class

### 3. Page Hero
- Background image: young musicians (Unsplash `photo-1544531585-9847b68c8c86`) at 14% opacity
- H1: "Inspiring the Next Generation of Musicians"
- Subtext about opening doors for young people
- CTAs: "Apply for Internship" (gold) + "Scout Merit Badge Program" (outline white, anchors to #scouts)

### 4. Application Notice Card
- Gold-tinted notice banner immediately below hero
- "Fall 2026 Intern Applications Now Open" — deadline text + "Download Application →" link

### 5. Overview — 3 Program Cards

Each card has a navy header (different gradient per program) + white body:

| Program | Header Gradient | Grade/Who | Key Details |
|---|---|---|---|
| Symphony Interns | `#0D1B2A → #1A2E45` | Grades 8–12 | Community service + on-stage rehearsal experience |
| Symphony Associates | `#1A2E45 → #2A4A6A` | HS through college | Post-intern continuation through graduation |
| Scout Merit Badge | `#1A4030 → #0D2A1E` | Scouts/Girl Scouts | Free, music-related badge requirements |

### 6. Intern Detail Section (id="interns", white)
- 2-column: image placeholder left, content right
- Margaret Wells pull-quote on navy background with gold left border
- Mission statement + bullet list of what interns do + Apply Now / Download Application buttons

### 7. Associates Detail Section (id="associates", cream)
- 2-column: content left, image placeholder right
- Pathway strip: 3 boxes (Intern Yr 1, Intern Yr 2 → Associate), center box in navy highlight
- Fast-track note for senior-semester interns
- Bullet list of associate benefits

### 8. Scout Merit Badge Section (id="scouts", white)
- 2-column: large circular badge icon (dark green gradient) left, content right
- 3-step process: Download Details → Attend Concert → Earn Badge
- Gold-bordered info box: "Available to: Scouts of America and Girl Scouts · Free of charge"
- "View Program Details" gold button → PDF link

### 9. Current Roster (dark navy section)
- 2-column: Interns (4 names) | Associates (15 names)
- Gold dot before each name
- Names in 50% white opacity text

### 10. Apply CTA (id="apply")
- Dark navy with image overlay (8% opacity)
- "Apply for Fall 2026" heading
- Two CTAs: "Download Application" (gold, .docx link) + "Email Questions"
- Deadline note with gold-highlighted date: "August 31, 2026"

---

---

# PAGE 2: Tickets Page (`/tickets`)

> Source: https://www.lewisvillesymphony.org/copy-of-tickets
> File: `lewisville-symphony-tickets.html`

## Page Overview

A dedicated, standalone tickets page that handles the full purchase journey: pricing tiers, how to buy, the full season schedule, venue details, FAQ, and a contact CTA. Must share the same design system (colors, fonts, components) as the homepage. The current tickets page is a plain text list with no visual hierarchy — this redesign makes pricing scannable, venue info clear, and the path to purchase obvious at every scroll depth.

---

## Page-Specific Components

### Breadcrumb
- Small nav trail below the page hero: `Home › Tickets`
- 12.5px, muted white/gray color, links hover to gold

### Pricing Card (`.pricing-card`)
- Border-radius 12px, 1.5px border
- **Featured variant** (`.featured`): gold border + double box-shadow using gold color
- Structure: `.card-header` (navy background) + `.card-body` (white)
- `.card-header` contains: icon emoji, type label (gold uppercase), card name (Playfair), description
- `.card-badge`: absolute-positioned pill ("Best Value") in gold, top-right of header
- `.price-row`: flex row — tier label left, Playfair price right — separated by thin bottom border
- `.card-perks`: checkmark list (✓ in gold) for benefits
- Hover: translateY(-4px) lift

### Special Pricing Card (`.special-card`)
- Tinted backgrounds — blue tint for Military, green tint for Group
- Large emoji icon + title + price badge + description + contact links
- Side-by-side in a 2-column grid

### Schedule Row (`.schedule-row`)
- 3-column grid: date block | concert info | action (price + button)
- Hover: background fills to `--gray-lt`, padding shifts left/right for an inset effect
- Date block: day name, full date, time — stacked vertically
- Artist name uses `.sched-artist` class (slightly darker than subtitle)

### Venue Card (`.venue-card`)
- White card, rounded 12px, full shadow
- Top: `aspect-ratio: 16/7` photo
- Body: series label (gold), venue name (Playfair), address, meta row (clock icon + calendar icon), note box (gray-lt background), action buttons

### FAQ Grid
- 2-column layout, items stacked vertically in each column
- Each item: bold question + paragraph answer, thin bottom border
- Gold links within answers

### Contact Card (`.contact-card`)
- Dark card on navy section background
- rgba white background with white border
- Left: colored icon box (gold-tinted) with emoji; Right: label + value + sub-label

---

## Sections (in order)

### 1. Announce Bar
- "2026–27 Season tickets on sale now · Season subscribers receive best seating and exclusive benefits" + gold "Subscribe Today →" link

### 2. Nav
- Identical to homepage nav
- "Season" link gets `.active` class (bold, gray-lt background) to indicate current section

### 3. Page Hero
- Background: `--navy` with a faint concert hall image overlay (12% opacity)
- Unsplash: `photo-1459749411175-04bf5292ceea`
- Breadcrumb above heading
- H1: "Tickets & Pricing"
- Subtext: "Join us for an unforgettable season of orchestral and chamber music in Lewisville and Flower Mound. Choose the option that fits your schedule and budget."
- CTAs: gold "Buy Tickets Online" → tix.com link + semi-transparent "Call the Box Office" button + small "🟢 Secure checkout via Tix.com" trust badge

### 4. Pricing Section
- Background: white
- Intro: section label + "Find Your Perfect Ticket" title + supporting paragraph
- **3-column pricing card grid:**

  | Card | Type | Name | Featured? |
  |---|---|---|---|
  | 1 | Full Season | Season Subscription | ✅ Yes — "Best Value" badge |
  | 2 | Per Concert | Individual Tickets | No |
  | 3 | Chamber Series | Free Admission | No |

  **Card 1 — Season Subscription (featured):**
  - Price rows: Adults $100 · Seniors 60+ $90 · Students $35
  - Perks: All four concerts · Priority seating · Rehearsal observation · Friend discounts · Early event access
  - CTA: gold "Subscribe Now" → tix.com

  **Card 2 — Individual Tickets:**
  - Price rows: Adults $30 · Seniors 60+ $25 · Students $10
  - Perks: Any single concert · Buy up to night of show · Online / phone / door · No commitment
  - CTA: navy "Buy Tickets" → tix.com

  **Card 3 — Chamber Series (Free):**
  - Giant "FREE" in green (#1A7A4A), 52px Playfair
  - "No ticket required · Open to all"
  - Perks: Four concerts · UNT partnership · International soloists · Open seating · 7:30 PM
  - CTA: outline-navy "View Chamber Schedule" → anchors to #schedule

- **2-column Special Pricing strip below:**

  **Military Card** (blue tint, `#F0F7FF` background):
  - 🎖️ icon
  - Title: "Military Appreciation Tickets"
  - Price badge: "$10 per person" (navy pill)
  - Desc: active duty + family members, all Symphony Series concerts
  - Contact: phone + email link for promo code

  **Group Card** (green tint, `#F5FFF9` background):
  - 👥 icon
  - Title: "Group Tickets"
  - Price badge: "Call for best rates"
  - Desc: bus tours, churches, social orgs, clubs, large families
  - Contact: phone + email link

### 5. How to Buy (3 steps)
- Background: `--cream`
- Section label + "Three Easy Ways to Get Your Tickets" title
- 3 white cards in a row, each with a navy circle number (Playfair), heading, description, and gold link

  | Step | Title | Detail |
  |---|---|---|
  | 1 | Buy Online | tix.com/lewisvillesymphony link |
  | 2 | Call the Box Office | 972.874.9087 |
  | 3 | Email Us | question@lewisvillesymphony.org |

### 6. Season Schedule (id="schedule")
- Section label + "Full Season Schedule" title
- **Tab row** (CSS-only visual tabs, no JS): Symphony Series · Chamber Series · Special Events
  - Active tab: navy color + 2px navy bottom border
  - Default tab: gray color, no underline
- **Schedule list** — one row per Symphony Series concert:
  - Date block: day name / full date / 7:30 PM
  - Concert info: Playfair title + artist subtitle
  - Action: "From $10" price label + gold "Tickets" button (btn-sm) → tix.com
- **Below the list, two info strips:**
  - Gray-lt strip: Chamber Series reminder — all 4 dates + venue + FREE label + "View Details" button
  - Purple-tinted strip: Peter & the Wolf — March 6, 2027 + venue + "Get Tickets" button

### 7. Venues
- Background: `--cream`
- Section label + "Where We Perform" title
- 2-column venue card grid

  **Venue 1 — Lewisville Grand Theater (Symphony Series):**
  - Image: Unsplash `photo-1459749411175-04bf5292ceea`
  - Address: 100 N. Charles St., Lewisville TX 75057
  - Meta: 7:30 PM · 4 concerts per season
  - Note: "Located in historic Old Downtown Lewisville. Ample parking nearby. Accessible seating available — contact box office in advance."
  - Buttons: "Get Directions" (Google Maps link) + "Venue Info"

  **Venue 2 — Trinity Presbyterian Church (Chamber Series):**
  - Image: Unsplash `photo-1415201364774-f6f0bb35f28f`
  - Address: 5500 Morriss Rd., Flower Mound TX 75028
  - Meta: 7:30 PM · Free admission (❤️ icon)
  - Note: "Free and open to the community. Open seating — arrive 15–20 minutes early. Presented with UNT College of Music."
  - Buttons: "Get Directions" + "Venue Info"

### 8. FAQ
- Background: white
- Section label + "Ticket & Visit Questions" title
- 2-column grid of Q&A items, 4 per column, thin bottom borders

  **Left column:**
  1. Can I buy tickets at the door? → Yes, but recommend advance purchase
  2. Is there a discount for students? → $10 individual / $35 season, ID required at door
  3. How do military discounts work? → $10/person, call or email for promo code
  4. What are the benefits of a season subscription? → Priority seating, rehearsal observation, friend discounts

  **Right column:**
  1. Do I need a ticket for the Chamber Series? → No, completely free, no RSVP
  2. Is the venue wheelchair accessible? → Yes, contact box office in advance
  3. Can I get a refund or exchange? → Contact box office directly
  4. How do group tickets work? → Any size group, contact us for rates

### 9. Contact CTA (id="contact")
- Background: `--navy`
- 2-column: left = headline "Still Have Questions? We'd Love to Help." + paragraph; right = 3 contact cards stacked

  | Card | Icon | Label | Value |
  |---|---|---|---|
  | 1 | 📞 | Box Office Phone | 972.874.9087 (tel link) |
  | 2 | ✉️ | Email | question@lewisvillesymphony.org |
  | 3 | 🎟️ | Buy Online 24/7 | tix.com/lewisvillesymphony |

### 10. Footer (simplified)
- Background: `#080F18`
- Single row: logo name + copyright + address left; nav links right (Home · Concerts · Youth Programs · Donate · Contact · Privacy Policy)

---

## Pricing Data Reference

| Ticket Type | Adults | Seniors 60+ | Students |
|---|---|---|---|
| Season Subscription | $100 | $90 | $35 |
| Individual Concert | $30 | $25 | $10 |
| Military (active + family) | $10 | $10 | $10 |
| Chamber Series | FREE | FREE | FREE |
| Group Rates | Call for pricing | — | — |

---

## Additional Technical Notes for Tickets Page

- **No JavaScript required** — tab switching is visual only (CSS `.active` class hardcoded); a real implementation would use JS or server-side rendering
- **Trust signal** — small green dot + "Secure checkout via Tix.com" text next to the hero CTA
- **Schedule row hover** — uses negative left/right margin trick to extend background beyond the column while maintaining text alignment
- **Green color** for "FREE" label: `#1A7A4A` — distinct from gold/navy palette, communicates value clearly
- **Special card tints** — Military uses `#F0F7FF` (blue), Group uses `#F5FFF9` (green) to visually differentiate without being heavy
- **Peter & the Wolf strip** — purple-tinted (`#F5F0FF` to `#EEF5FF` gradient) to stand out as a distinct family event, not a regular Symphony Series concert
- **All external links** open in `target="_blank"` (tix.com, Google Maps)
