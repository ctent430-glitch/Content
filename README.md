Build a high-end, ultra-premium 18+ adult video streaming web application with full Burmese (Myanmar) UI localization, powered by the official Eporner API v2 (`https://www.eporner.com/api/v2/video/search/` and `https://www.eporner.com/api/v2/video/id/`).

### 1. Tech Stack & Architecture
- Use **Next.js (App Router)** with **Tailwind CSS** and **Lucide React** icons.
- **API Proxy Routes:** Create Next.js API routes (`/api/videos` and `/api/video/[id]`) to fetch data from Eporner API v2 server-side so there are zero CORS issues on the client.
  - Search Endpoint: `https://www.eporner.com/api/v2/video/search/?query={q}&per_page=24&page={page}&thumbsize=big&order={order}&gay=0&lq=0&format=json`
  - Single Video Endpoint: `https://www.eporner.com/api/v2/video/id/?id={id}&thumbsize=big&format=json`
- Load Google Font **Noto Sans Myanmar** and **Plus Jakarta Sans** so Burmese typography looks crisp, modern, and well-spaced.

### 2. Design Aesthetic & Liquid Glass UI
- **Color Palette:** Deep obsidian dark mode (`#070709`), rich velvet accents, and subtle crimson/rose-gold luxury highlights (`#E11D48` to `#F59E0B` gradients).
- **Liquid Glass (Glassmorphism) Styling:**
  - Apply frosted liquid glass effects (`backdrop-blur-xl`, translucent dark fills `bg-white/[0.04]`, luminous specular 1px borders `border-white/10`, and soft inner/outer glow shadows) across the floating navbar, category pills, video grid cards, and player containers.
  - On video card hover, add a smooth scale transition, a subtle liquid light sheen sweep across the card, and glowing border highlights.

### 3. Burmese UI & Age Verification
- **18+ Age Gate Modal:** On first visit (persisted in `localStorage`), display a sleek Liquid Glass age verification modal in Burmese:
  - Title: "အသက် ၁၈ နှစ်ပြည့်ပြီးသူများသာ ဝင်ရောက်ရန်"
  - Subtitle: "ဤဝဘ်ဆိုက်တွင် လူကြီးများအတွက် သီးသန့် ဗီဒီယိုများ ပါဝင်ပါသည်။ ဆက်လက်ကြည့်ရှုရန် သင်သည် အသက် ၁၈ နှစ်နှင့်အထက် ဖြစ်ကြောင်း အတည်ပြုပါ။"
  - Buttons: "၁၈ နှစ်ပြည့်ပြီးပါပြီ (ဝင်ရောက်မည်)" and "ထွက်မည်".
- **Burmese Navigation & Labels:**
  - Search placeholder: "ဗီဒီယိုများ ရှာဖွေရန်..."
  - Sort/Filter tabs in Burmese: "နောက်ဆုံးတင်ထားသော" (`latest`), "လူကြည့်အများဆုံး" (`most-popular`), "အကောင်းဆုံးသတ်မှတ်ချက်" (`top-rated`), "ယခုအပတ် ရေပန်းအစားဆုံး" (`top-weekly`), "အရှည်ဆုံး" (`longest`).
  - Category quick pills (with Burmese labels + English API search queries): အားလုံး (all), အာရှ (asian), ဂျပန် (japanese), အနောက်တိုင်း (blonde), HD အကြည် (4k), အသစ်စက်စက် (amateur).

### 4. Key Pages & Components
1. **Home Page (`/`):**
   - **Floating Liquid Glass Navbar:** Brand logo, live search bar, and quick filter controls.
   - **Featured Hero Banner:** Automatically showcase the top trending video from the API with a large widescreen backdrop (`default_thumb.src`), blurred liquid glass info overlay, view count, rating badge, duration (`length_min`), and a glowing "ယခုကြည့်ရှုမည်" (Watch Now) CTA button.
   - **Liquid Glass Video Grid:** Responsive 1-to-4 column grid. Each card must display:
     - High-res thumbnail (`default_thumb.src`) with duration pill badge (`length_min`) and HD/4K badge.
     - Video title (`title`), formatted view count (`views` + " ကြိမ်ကြည့်ရှုပြီး"), rating percentage (`rate`), and upload date (`added`).
   - **Pagination:** Clean Burmese pagination controls ("ရှေ့သို့", "နောက်သို့", and page numbers).

2. **Watch Video Page (`/watch/[id]`):**
   - Fetch full video metadata using `/api/video/[id]`.
   - **Responsive 16:9 Liquid Glass Video Player Frame:** Embed the official Eporner iframe player (`video.embed`) cleanly with rounded corners, ambient background glow, and theater-mode toggle.
   - **Video Details Glass Panel:** Full title, formatted views ("ကြည့်ရှုမှုအကြိမ်ရေ"), rating, duration, and clickable keyword tags (`keywords` split into interactive Liquid Glass pills that search when clicked).
   - **Related Videos Section:** A grid/sidebar of related videos fetched dynamically based on the current video's primary keyword/tag.

### 5. Execution Instructions
- Initialize the Next.js project cleanly in the current directory (if not already initialized), install dependencies, create all components and API routes, and verify there are no TypeScript or build errors.
- Start the dev server or confirm everything builds cleanly when done..
