===============================================================
  DHAKA RIDER — DELIVERY RUSH   (ঢাকা রাইডার — ডেলিভারি রাশ)
  Version 0.4  ·  3D browser game (Babylon.js)  ·  10 Dhaka areas
  Plays on computers (keyboard) and on phones / tablets (touch)
===============================================================

দ্রুত শুরু (Quick start)
-------------------------
১. index.html ফাইলে ডাবল-ক্লিক করুন (Google Chrome-এ খুলবে)।
২. ইন্টারনেট চালু রাখুন — 3D ইঞ্জিন (Babylon.js) অনলাইন থেকে লোড হয়।
৩. "খেলা শুরু করুন" চাপুন → লেভেল পরিচিতি দেখে "শুরু করুন" (বা Enter)।
৪. নীল নেভিগেশন তীর অনুসরণ করে রেস্তোরাঁয় যান, কর্মীর কাছে E চাপুন,
   তারপর সময়ের মধ্যে কাস্টমারের কাছে গিয়ে আবার E চাপুন।
৫. লেভেলের সব অর্ডার শেষ করলে পরের এলাকা আনলক হবে।

ফোনে খেলা (Playing on a phone)
-------------------------------
লাইভ লিংক (dhaka-rider-game.vercel.app) ফোনের Chrome / Safari-তে খুলুন,
ফোনটা আড়াআড়ি (landscape) করে ধরুন। বাম দিকে ◀ ▶ (বাঁক), ডান দিকে
▲ (গতি), ▼ (ব্রেক / পেছনে) আর হলুদ E বাটন। বিস্তারিত: সেকশন 3b।

IMPORTANT: keep the "assets" folder next to index.html. It holds the
Bengali voice clips (assets/audio/voices/...). Without it the game still
runs, but dialogue falls back to browser speech or subtitles only.


1. FILES
--------
  index.html                      the whole game (open this)
  assets/audio/voices/rider/      rider voice clips (.mp3)
  assets/audio/voices/npc/        restaurant worker / angry public / rickshaw
  assets/audio/voices/customer/   customer reactions (male/female/elder)
  assets/audio/voices/vendors/    tea-stall and fruit-seller lines
  assets/audio/music/             start_music.mp3 (menu / level start music)
  assets/audio/sfx/               aye.mp3 (pedestrian hit), fight.mp3 (beating),
                                  bell.mp3 (rickshaw bell)
  README.txt                      this file
  backup_v0.1/                    the first version (v0.1), untouched
  backup_v0.3/ … backup_v0.3.4/   earlier versions, newest last
                                  (keep them on your computer only;
                                  they are not needed on GitHub)


2. HOW TO OPEN THE GAME
-----------------------
- Double-click index.html. It runs directly from the file (file://).
- Recommended browser: Google Chrome (desktop). Edge also works.
- No installation, no npm, no Node.js, no local server, no build step.
- Internet is needed for Babylon.js (jsDelivr, with automatic fallback
  to unpkg and cdn.babylonjs.com) and Google Fonts. If the fonts fail,
  Windows' own Bengali font (Nirmala UI / Vrinda) is used.
- Each level is built when it is selected; switching level reloads the
  page (a few seconds), and your progress is kept.


3. KEYBOARD CONTROLS
--------------------
  W / Up arrow       Accelerate
  S / Down arrow     Brake (hold when stopped to reverse)
  A / Left arrow     Turn left
  D / Right arrow    Turn right
  SPACE              Strong brake
  E                  Pick up / hand over the parcel, refuel at a pump
  H                  Horn (people nearby jump aside)
  R                  Put the bike back on the road (if stuck)
  ESC  (or P)        Pause / resume
  M                  Sound on / off
  Enter              Start level (intro screen) / next order


3b. PHONE AND TABLET (TOUCH) CONTROLS — new in v0.4
----------------------------------------------------
Phones and tablets are detected automatically (touch screen without a
mouse) and get a separate layout:
- Landscape only. Held upright, the game shows "ফোনটা আড়াআড়ি
  (Landscape) করে ধরুন" and pauses the ride. On Android the game also
  switches to full screen and locks landscape after the first tap; the
  ⛶ button in the top bar enters / leaves full screen. (iPhone Safari
  has no full-screen mode for web pages; keep auto-rotate on.)
- On-screen buttons:
    ◀  ▶   (bottom left)   turn left / right
    ▲      (bottom right)  accelerate (hold)
    ▼      (bottom right)  brake; hold when stopped to reverse
    E      (yellow)        pick up / hand over / refuel — it pulses when
                           there is something to press it for; tapping
                           the "press E" prompt works too
  Two fingers work at once (▲ + ◀/▶), and a thumb can slide from ◀ to ▶
  without lifting.
- Pause (top right ॥) opens the pause menu, which now also has
  "বাইক রাস্তায় ফেরান" (the R key on a computer).
- Compact HUD: smaller mission card (top left), navigation (top centre),
  money / rating / sound / full screen / pause (top right), the minimap
  stays on screen under them, a small speed read-out at the bottom
  centre. The keyboard card is hidden.
- Menus, level select, settings, pause and the delivery result are laid
  out to fit a short landscape screen.
- Phones start on Graphics Low (faster); Settings → Graphics: High if
  your phone is strong.


4. THE 10 LEVELS (unlocked one by one)
--------------------------------------
Level 1 is open at the start. Completing every delivery order of a
level unlocks the next one. Unlocked levels can be replayed any time
from "লেভেল সিলেক্ট" (Level Select). Progress, best result per level
(rating, time, earnings) and your wallet are saved in the browser
(localStorage).

 #  Area               Difficulty  Character of the level
 1  মিরপুর ১০ (Mirpur 10)   ★        Starter area: main road with median, two
                                    side roads, local hotels, tea/fuchka/
                                    jhalmuri carts, fruit stall. Daytime.
 2  কাজীপাড়া (Kazipara)    ★        Metro-rail viaduct over the main road,
                                    narrow lanes, many tea stalls, rickshaw
                                    crowds. Daytime.
 3  মোহাম্মদপুর (Mohammadpur) ★★     Busy market lane, fruit sellers, fuchka
                                    and chotpoti stalls, delivery van.
 4  ধানমন্ডি (Dhanmondi)    ★★       Road grid with many intersections,
                                    lake + park, bigger buildings,
                                    restaurants, parked cars.
 5  ফার্মগেট (Farmgate)     ★★★      Wide roads with traffic signals, bus
                                    stops, many buses/minibuses, footbridges.
                                    Daytime.
 6  শাহবাগ (Shahbagh)      ★★★      Flower market road, big junction, park,
                                    crowds, extra rickshaw encounters. Daytime.
 7  পুরান ঢাকা (Old Dhaka)  ★★★★     Maze of narrow lanes, dense market, old
                                    buildings, rickshaw jams. Daytime. LOW FUEL
                                    (petrol pump on the map).
 8  মতিঝিল (Motijheel)     ★★★★     Office towers, signals, Shapla sculpture,
                                    heavy traffic, tight time limits. Low fuel.
 9  গুলশান-বনানী (Gulshan)  ★★★★★    Wide avenues, modern glass buildings,
                                    lake bridge, long routes. EVENING. Low fuel.
10  হাতিরঝিল (Hatirjheel)  ★★★★★    NIGHT ride around the big lake, two
                                    lit bridges, low fuel.

Level 1 keeps the three short Mirpur orders of v0.1; levels 2–3 have
1 delivery order, levels 4–9 have 2 and level 10 has 3.
Levels 1–8 are bright daytime. Level 9 is evening and level 10 is
night; there every vehicle drives with headlights and tail lights,
street lamps light up the road and shops/windows glow, so the street
stays easy to see. There is no rain.
Every level has its own road layout, building style, traffic mix,
stalls, pedestrians, time of day and delivery orders.
Areas are compact, stylised blocks (about 220–340 m across) inspired by
each neighbourhood — not exact street maps.


5. HOW A DELIVERY WORKS
-----------------------
 1. The restaurant worker waves; a yellow beam marks him. As you ride
    up to him the rider calls "ওই জিল্লু, পার্সেলটা দে!"; then press E
    and the parcel flies onto the delivery box.
 2. A time limit appears (based on the route length). The customer is
    marked with a teal beam. All customers are men. When you are close
    but not there yet, the rider says "আশেপাশেই তো থাকার কথা... ওইতো,
    ওইদিক!".
 3. Parcel condition starts at 100 %. Crashes, falls, potholes, hitting
    stalls/people and very hard braking reduce it. At 0 % the mission
    fails.
 4. At the customer press E. The customer reacts:
    on time            -> "এইবার তো ঠিক সময়ে আইছেন!"
    late               -> "এত দেরি মামা, ঠান্ডা হয়ে গেছে সব!"
    parcel under 80 %  -> "এইডা কেমন কথা? এইটা আমি খাবো, নাকি
                           কুত্তারে খাওয়াবো?"
 5. Reward = base pay (grows with level) + time bonus + safe-riding
    bonus − damage − late penalty. Rating 1–5 stars.
 6. The result screen shows the breakdown; after the last order of a
    level it announces the newly unlocked area.


6. SMART NAVIGATION
-------------------
- Every level has a road graph (intersections = nodes, road pieces =
  edges). The route is the shortest path (Dijkstra) from your position
  and heading to the target; turning around costs extra.
- The next road you must take glows and pulses on the asphalt, glowing
  chevrons run along it, and a 3D arrow floats over the intersection.
- The navigation panel (top centre) shows the instruction —
  "সামনের মোড়ে বামে যান।", "সামনের মোড়ে ডানে যান।", "সোজা যান।",
  U-turn, arrival — the distance to the next turn, the remaining route
  and a progress bar. The minimap shows the route as a blue line.
- Taking a wrong turn is detected: "ভুল রাস্তায় চলে গেছেন, নতুন রাস্তা
  দেখানো হচ্ছে!" and the route is recalculated.


7. CITY LIFE, CHAOS AND THE CROWD CHASE
---------------------------------------
- Traffic AI: local buses (with conductor), minibuses, CNGs, rickshaws,
  cars, microbuses, motorcycles, delivery bikes and vans drive in the
  LEFT lane on the road graph, turn at intersections, stop at red
  signals and bus stops, queue behind each other and honk.
- Parked motorcycles, rickshaws and cars; bus stops, signals, banners,
  billboards, construction zones, footbridges, metro viaduct.
- Stalls: tea, fuchka, chotpoti, jhalmuri, fruit, flower, mobile
  accessories. Hitting any stall sends its items flying with its own
  sound; the owner cries "হায়রে!!! সব শেষ আমার!" and 8 seconds later
  comes after you (with a helper) — the crowd chase below.
- Busy streets from Level 1 on: dozens of pedestrians on the footpaths,
  people walking along the edge of the road itself, groups chatting,
  people crossing at zebra crossings, and many street stalls on every
  level. People jump aside when you honk or ride close.
- Rickshaw cutting in: a real bicycle-bell sound, the puller shouts
  "ও ভাই! রাস্তা কি আপনার একার?" and the rider sometimes answers
  "মামা, একটু সাইড দেন!" (same when you bump a rickshaw).
- Potholes bounce the bike and damage the parcel; a hard head-on crash
  tips the bike over.
- The rider says "অশান্তি!" (your recording, rider_osanti.mp3) when the
  bike drops into a pothole or crashes into any vehicle — moving or
  parked bus, car, CNG, motorbike or rickshaw. With a rickshaw he says
  it first and the puller answers. At most once every 4 seconds, so a
  row of potholes does not repeat it.
- BUMPING A PEDESTRIAN: an "AYE!" sound, the person is knocked flat and
  lies on the road. After 3 seconds they shout — the two lines take
  turns from one incident to the next: "আমি তরে সিল মাইরা দিমু!" and
  "বুঝছি তোমার মরণের চুলকানি উঠেছে।". After 10 seconds they get up and
  the CROWD CHASE starts (if you are already far away they let it go).
  Every other person you knock down joins the chase the same way.
- CROWD CHASE: a small red counter under the navigation panel shows
  "🏃 N জন তাড়া করছে · D মি" (how many are chasing and how close the
  nearest one is), with chase music. The chase starts with
  "তোরে যদি একা পাই, একদম খাইয়া দিমু!".
  ESCAPE: speed up and pull clearly away from them — they give up and
  the rider says "যাক, আজকের মতো বাঁচলাম।".
  CAUGHT (they reach you while you are slow, or you stand still right
  next to them): the bike tips over, the rider falls onto the road and
  they beat him up — punching, dust cloud, "ধুপ-ধাপ!" and
  "ধুপ!/ধাপ!/ঢিশুম!" pop-ups and the recorded fighting sound (about
  4.5 s). Then the rider: "আজকে গেছি রে!" and GAME OVER with Restart
  Level / Level Select.
- A clean screen: spoken lines are heard, not printed (a subtitle only
  appears if a voice cannot be played, e.g. with sound muted); no
  pop-up banners or speech bubbles apart from the beating; the controls
  card hides itself 12 seconds after a level starts.

8. BENGALI VOICES
-----------------
- Every spoken line in the game is a real recording you supplied
  (assets/audio/voices): 12 lines you recorded (rider, customer,
  rickshaw puller, stall owner, angry man) and the two film-dialogue
  clips for the knocked-down pedestrians. They were trimmed, cleaned of
  light background hiss and set to the same loudness; the two film
  clips also had their background noise reduced and the sound effects
  at their start and end cut off.
- The older AI-generated voice files have been removed; the game no
  longer uses any AI voice.
- If an audio file is missing or cannot be played, the line is shown
  as a subtitle instead (or read by the browser's Bengali voice if the
  computer has one — never an English voice).
- Settings → "ভয়েস টেস্ট" plays a few of the recorded lines.

9. SOUND AND SETTINGS
---------------------
- Start music: assets/audio/music/start_music.mp3 plays on the main
  menu and on every level's start screen, and stops as soon as the ride
  begins. Browsers (Chrome, Edge, Firefox) do not let any web page play
  sound before the first click or key press. So when the browser blocks
  it, the loading screen ends with one "▶ শুরু করতে ক্লিক করুন" button;
  the music starts with that click. When the browser allows sound
  straight away, the button is skipped. The Music slider and Mute
  control it.
- Main menu / pause → Settings: Master, Voice, SFX, Ambient (city),
  Music sliders, Mute, Graphics High/Low, Voice test. Saved in the
  browser.
- All sound effects and music are synthesized with Web Audio:
  engine (pitch follows speed), horns per vehicle type, rickshaw bell,
  CNG horn, bus air-horn, crash, pothole thud, cup clatter, fruit
  scatter, wood/metal stall hits, pedestrian "oof", bike fall,
  footsteps, capture "ধুপ-ধাপ", game-over sting, success jingle,
  coin, unlock fanfare, city ambience, crowd murmur, city and
  chase music.
- Dialogue has priorities (Game Over > caught > crowd chase > mission
  > customer > collision > ambient), per-line cooldowns, and only one
  voice speaks at a time.


10. IMPLEMENTED FEATURES (SUMMARY)
----------------------------------
- Kept from v0.1: motorcycle controller, rider, camera, delivery
  hand-over animations, HUD style, minimap, speedometer, pause menu,
  Graphics High/Low, procedural buildings and signboards.
- New: 10 levels + level select with map previews, lock state, best
  results; level intro; progress saving; level-specific worlds;
  instanced traffic and pedestrians with LOD; traffic signals; stalls
  and parked vehicles; chaos/collision reactions; crowd chase and game
  over; smart navigation; time limits, parcel condition, fuel and petrol
  pumps; reward breakdown and customer reactions; Bengali voice files;
  audio channels and settings; bright day / evening / night lighting
  with vehicle headlights at evening and night.


11. WHAT WAS TESTED
-------------------
Tested in a headless Chromium browser with software (CPU) rendering,
opening index.html from the file system (file://), as you will:
- All 10 levels build and start without JavaScript errors
  (screenshots of every level checked, including the brighter daytime
  look and the evening/night headlights).
- Full play-through with a scripted rider that follows the in-game
  navigation: Level 1 from empty progress (all 3 orders: pickup ->
  delivery, including a damaged-parcel reaction -> level complete ->
  Level 2 unlocked -> "next level" reload keeps progress ->
  Level Select shows Level 1 best result, Level 2 open, 3–10 locked) and
  Level 10 (all 3 orders: on-time, late and very-late customer
  reactions, reward breakdown, final "all 10 areas" message).
- Navigation: left / right / straight / U-turn / arrival instructions
  appeared during the scripted rides; a deliberate wrong turn was
  detected and the route was recalculated (the panel now shows
  "ভুল রাস্তা! নতুন রুট দেখানো হচ্ছে").
- Latest checks (Level 1): each recorded line plays at its event —
  pickup "ওই জিল্লু…", near the customer, on-time / late / damaged
  customer, stall owner then the owner's chase exactly 8 s later,
  pedestrian AYE → line at 3 s → chase at 10 s → caught → fighting
  sound → "আজকে গেছি রে!" → GAME OVER, escape line, rickshaw bell and
  both rickshaw lines. During all of this no subtitles, toasts or
  speech bubbles appeared except the beating pop-ups.
- Start music, Settings voice test, sliders (saved), pause / resume,
  and the automatic "switch to Low graphics" safeguard.
- v0.4 (phones): emulated phones in landscape — 640×360, 844×390
  (iPhone 12/13/14), 932×430 (large phones) and a 1024×768 tablet —
  with real touch events: holding ▲ drives, ▲ + ◀ together turns, a
  thumb slide from ◀ to ▶ switches direction, releasing stops all
  input, ▼ brakes and reverses, E picks up the parcel, the E button
  pulses at the restaurant, the HUD panels do not overlap and stay on
  screen, menus / settings / pause / result fit, turning the phone
  upright shows the rotate screen and pauses. Full screen is entered on
  the first tap.
- v0.4 (voice): "অশান্তি!" on a pothole, on a real crash into a bus,
  on a direct car/bus hit, and before the rickshaw puller's line.
- v0.4 (computer): keyboard layout unchanged, no touch buttons, the
  "ফন্ট লোড হচ্ছে…" line is gone from the loading screen.
Not tested: real sound output (no speakers in the test machine), the
look and frame rate on a real graphics card or a real phone, other
browsers (iPhone Safari in particular).


12. KNOWN LIMITATIONS
---------------------
- Internet is needed for Babylon.js and fonts; offline the game shows
  an error message instead of starting.
- Voices are your recordings (see section 8). They were processed
  without listening to them: which film clip says which line was worked
  out from clip lengths and file names, and the noise clean-up was
  checked on spectrograms only.
- Performance on your PC is unknown. With Graphics High a busy level
  needs roughly 1,300 draw calls per frame (city + shadows + glow);
  with Low about half. If the frame rate is low during the first
  seconds of riding and you never chose a graphics setting, the game
  switches to Low once by itself; you can change it in Settings.
- Arcade physics: collisions use circles and boxes. The bike can tip
  over on a hard head-on crash, but there is no real ragdoll; people
  "stumble" with cartoon animations.
- Traffic AI is simple: vehicles follow lanes, signals and each other,
  but when a jam lasts several seconds a vehicle may briefly pass
  through another to unblock the road. Vehicles brake for you; they do
  not steer around you.
- Selecting a different level reloads the page (2–15 s depending on
  the PC). Restarting the same level is instant.
- Keyboard (computer) or on-screen buttons (phone / tablet); no gamepad.
- Phones: a busy level asks a lot of a phone; older phones may run
  slowly even on Low. iPhone Safari cannot lock landscape or go full
  screen for a web page. Changing level reloads the page, which leaves
  full screen; the next "tap to start" turns it back on (Android).
- Progress and settings use browser storage (localStorage). Some
  browsers / privacy modes block it for file:// pages; then progress
  resets when the page is closed.
