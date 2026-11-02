===============================================================
  DHAKA RIDER — DELIVERY RUSH   (ঢাকা রাইডার — ডেলিভারি রাশ)
  Version 0.3  ·  3D browser game (Babylon.js)  ·  10 Dhaka areas
===============================================================

দ্রুত শুরু (Quick start)
-------------------------
১. index.html ফাইলে ডাবল-ক্লিক করুন (Google Chrome-এ খুলবে)।
২. ইন্টারনেট চালু রাখুন — 3D ইঞ্জিন (Babylon.js) অনলাইন থেকে লোড হয়।
৩. "খেলা শুরু করুন" চাপুন → লেভেল পরিচিতি দেখে "শুরু করুন" (বা Enter)।
৪. নীল নেভিগেশন তীর অনুসরণ করে রেস্তোরাঁয় যান, কর্মীর কাছে E চাপুন,
   তারপর সময়ের মধ্যে কাস্টমারের কাছে গিয়ে আবার E চাপুন।
৫. লেভেলের সব অর্ডার শেষ করলে পরের এলাকা আনলক হবে।

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
  README.txt                      this file
  backup_v0.1/                    the previous version (v0.1), untouched


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
                                    crowds. Evening.
 3  মোহাম্মদপুর (Mohammadpur) ★★     Busy market lane, fruit sellers, fuchka
                                    and chotpoti stalls, delivery van.
 4  ধানমন্ডি (Dhanmondi)    ★★       Road grid with many intersections,
                                    lake + park, bigger buildings,
                                    restaurants, parked cars.
 5  ফার্মগেট (Farmgate)     ★★★      Wide roads with traffic signals, bus
                                    stops, many buses/minibuses, footbridges,
                                    RAIN.
 6  শাহবাগ (Shahbagh)      ★★★      Flower market road, big junction, park,
                                    crowds, extra rickshaw encounters. Evening.
 7  পুরান ঢাকা (Old Dhaka)  ★★★★     Maze of narrow lanes, dense market, old
                                    buildings, rickshaw jams. Dusk. LOW FUEL
                                    (petrol pump on the map).
 8  মতিঝিল (Motijheel)     ★★★★     Office towers, signals, Shapla sculpture,
                                    heavy traffic, tight time limits. Low fuel.
 9  গুলশান-বনানী (Gulshan)  ★★★★★    Wide avenues, modern glass buildings,
                                    lake bridge, long routes. Evening. Low fuel.
10  হাতিরঝিল (Hatirjheel)  ★★★★★    Night ride around the big lake, two
                                    lit bridges, 3 orders, low fuel.

Levels 1–3 have 1 delivery order, levels 4–9 have 2, level 10 has 3.
Every level has its own road layout, building style, traffic mix,
stalls, pedestrians, weather/time of day and delivery orders.
Areas are compact, stylised blocks (about 220–340 m across) inspired by
each neighbourhood — not exact street maps.


5. HOW A DELIVERY WORKS
-----------------------
 1. The restaurant worker waves; a yellow beam marks him. Ride up and
    press E. The parcel flies onto your delivery box.
 2. A time limit appears (based on the route length). The customer is
    marked with a teal beam.
 3. Parcel condition starts at 100 %. Crashes, falls, potholes, hitting
    stalls/people and very hard braking reduce it. At 0 % the mission
    fails.
 4. At the customer press E. The customer reacts:
    on time   -> "এইবার তো ঠিক সময়ে আইছেন!"
    late      -> "ভাই, এত দেরি কেন?" (rider may answer "ঢাকার জ্যাম ভাই,
                 আমার কী দোষ!")
    very late -> "ভাই, বিরিয়ানি অর্ডার করছি, আপনার জীবনের গল্প না!"
                 (for biryani / kacchi / tehari / polao orders)
    damaged   -> "এইডা কোনো কথা হইলো?"
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
  accessories. Hitting one sends its items flying with its own sound
  and a reaction line from the owner (e.g. "এই ভাই! চায়ের দোকান
  নাকি আপনার রেসিং ট্র্যাক?").
- Pedestrians walk, wait and cross at zebra crossings, chat in groups,
  jump aside when you honk, stumble and recover if you bump them.
- Funny events: pothole surprise ("ও মা! রাস্তা নাকি চাঁদের জমিন!"),
  rickshaw cutting in ("ও ভাই! রাস্তা কি আপনার একার?"), bike falling
  over on a hard crash. Events have cooldowns and never overlap.
- CROWD CHASE: knocking over a stall (sometimes) or bumping two people
  within 45 s makes the public chase you: banner "ওহ না! লোকজন পেছনে
  লেগেছে!", chase music, a red chase panel, the rider's line
  "ওরা আমারে মারতে চায় মা, ওরা আমারে বাঁচতে দেবে না!" and the angry
  man's "তোরে যদি আমি একা পাই, একদম থাসায়া ধরমু!".
  Ride ~38 m away to escape (normal music returns).
  If they reach you while you are slow: cartoon capture (dust, stars,
  "ধুপ-ধাপ" sound), "এবার বুঝছেন, ঢাকা শহর কার!" → "আমি আইজকা শ্যাষ!",
  then GAME OVER with Restart Level / Level Select.


8. BENGALI VOICES — WHAT THEY ACTUALLY ARE
------------------------------------------
- 29 dialogue lines are pre-generated audio files (assets/audio/voices).
  They were produced OFFLINE with an open-source Bengali neural
  text-to-speech model (Coqui TTS, VITS Bengali male and female voices)
  and then pitch/speed-shaped with ffmpeg to give different characters
  (rider, worker, angry man, rickshaw puller, vendors, customers).
- They are AI-generated synthetic speech, NOT recordings of real voice
  actors. The Dhakaiya lines are spelled phonetically ("আমি আইজকা
  শ্যাষ!", "এইডা কোনো কথা হইলো?"); the TTS model reads them, but the
  accent is most likely closer to standard Bangla and was not checked by a native
  listener. Replace any .mp3 with a real recording of the same name if
  you want better acting — the game will use it automatically.
- If an audio file is missing or cannot be played, that line uses the
  browser's Bengali speech voice (bn-BD, then bn-IN) when the computer
  has one. An English voice is never used for Bengali text. If neither
  exists, only the Bangla subtitle is shown. Subtitles are always
  shown.
- Settings → "ভয়েস টেস্ট" plays the signature lines and tells you
  which voice source is in use.


9. SOUND AND SETTINGS
---------------------
- Main menu / pause → Settings: Master, Voice, SFX, Ambient (city),
  Music sliders, Mute, Graphics High/Low, Voice test. Saved in the
  browser.
- All sound effects and music are synthesized with Web Audio:
  engine (pitch follows speed), horns per vehicle type, rickshaw bell,
  CNG horn, bus air-horn, crash, pothole thud, cup clatter, fruit
  scatter, wood/metal stall hits, pedestrian "oof", bike fall,
  footsteps, capture "ধুপ-ধাপ", game-over sting, success jingle,
  coin, unlock fanfare, city ambience, rain, crowd murmur, city and
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
  audio channels and settings; day / evening / dusk / night / rain.


11. WHAT WAS TESTED
-------------------
Tested in a headless Chromium browser with software (CPU) rendering,
opening index.html from the file system (file://), as you will:
- All 10 levels build and start without JavaScript errors
  (screenshots of every level checked).
- Full play-through with a scripted rider that follows the in-game
  navigation: Level 1 from empty progress (pickup -> delivery -> level
  complete -> Level 2 unlocked -> "next level" reload keeps progress ->
  Level Select shows Level 1 best result, Level 2 open, 3–10 locked) and
  Level 10 (all 3 orders: on-time, late and very-late customer
  reactions, reward breakdown, final "all 10 areas" message).
- Navigation: left / right / straight / U-turn / arrival instructions
  appeared during the scripted rides; a deliberate wrong turn showed
  "ভুল রাস্তায় চলে গেছেন, নতুন রাস্তা দেখানো হচ্ছে!" and the route was
  recalculated.
- Events: stall knocked over (owner reaction), pothole (rider line,
  mud, bounce), two pedestrian bumps -> crowd chase (banner, chase
  panel, both chase lines) -> standing still -> caught -> "এবার বুঝছেন,
  ঢাকা শহর কার!" -> "আমি আইজকা শ্যাষ!" -> GAME OVER -> Restart Level;
  separately, escaping a chase.
- All 29 voice files load and play from file:// (playback position
  advances); Settings voice test, sliders (saved), pause / resume.
- The automatic "switch to Low graphics when the frame rate is low"
  safeguard.
Not tested: real sound output (no speakers in the test machine), the
look and frame rate on a real graphics card, other browsers.


12. KNOWN LIMITATIONS
---------------------
- Internet is needed for Babylon.js and fonts; offline the game shows
  an error message instead of starting.
- Voices are AI text-to-speech, not actors (see section 8). The
  Dhakaiya flavour comes from the spelling; the generated accent is
  closer to standard Bangla, and pronunciation was not checked by ear.
  Every spoken dialogue line has its own audio file. Short speech-
  bubble shouts (bus conductor "মিরপুর! মিরপুর!", bystanders' "আরে
  আরে!") are text bubbles without voice. If the assets folder is
  missing, the game falls back to the browser's Bengali voice — Chrome
  on Windows usually has none, so then only subtitles are shown.
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
- Keyboard only (no touch or gamepad controls).
- Progress and settings use browser storage (localStorage). Some
  browsers / privacy modes block it for file:// pages; then progress
  resets when the page is closed.
- Rain is visual + sound only (no wet-road physics).
