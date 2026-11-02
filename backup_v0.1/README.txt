===============================================================
  DHAKA RIDER — DELIVERY RUSH   (ঢাকা রাইডার — ডেলিভারি রাশ)
  Demo version 0.1  ·  3D browser game (Babylon.js)
===============================================================

দ্রুত শুরু (Quick start)
-------------------------
১. index.html ফাইলে ডাবল-ক্লিক করুন (Google Chrome-এ খুলবে)।
২. ইন্টারনেট চালু রাখুন — 3D ইঞ্জিন (Babylon.js) অনলাইন থেকে লোড হয়।
৩. "খেলা শুরু করুন / PLAY GAME" বাটনে ক্লিক করুন।
৪. রেস্তোরাঁর সামনের কর্মীর কাছে গিয়ে E চাপুন, তারপর হলুদ/সবুজ
   মার্কার অনুসরণ করে কাস্টমারের কাছে পার্সেল পৌঁছে দিন।


1. HOW TO OPEN THE GAME
-----------------------
- Double-click  index.html . It opens directly from the file (file://).
- Recommended browser: Google Chrome (desktop). Edge also works.
- If Windows opens it in another browser: right-click index.html ->
  "Open with" -> Google Chrome.
- No installation, no npm, no Node.js, no local server, no build step.
- First load takes a few seconds while Babylon.js (~8 MB) downloads;
  the browser caches it afterwards.


2. INTERNET REQUIREMENT
-----------------------
- Internet is required to load Babylon.js from a CDN
  (jsDelivr, with automatic fallback to unpkg and cdn.babylonjs.com).
- Google Fonts (Hind Siliguri, Bungee) are also loaded online. If they
  are unavailable, the game falls back to the Bengali font that ships
  with Windows (Nirmala UI / Vrinda), so Bangla text still shows.
- Everything else (3D models, textures, sounds, dialogue) is generated
  inside index.html — there are no other files to download.


3. KEYBOARD CONTROLS
--------------------
  W / Up arrow       Accelerate
  S / Down arrow     Brake (hold when stopped to reverse)
  A / Left arrow     Turn left
  D / Right arrow    Turn right
  SPACE              Strong brake
  E                  Interact (pick up / hand over the parcel)
  H                  Horn
  R                  Put the bike back on the road (if stuck)
  ESC  (or P)        Pause / resume
  M                  Sound on / off
  Enter              Play (on the main menu) / next order (on the
                     delivery-complete screen)


4. HOW TO PLAY (THE DEMO MISSION)
---------------------------------
 1. You start on the main road outside "ঢাকা বিরিয়ানি" restaurant.
 2. The restaurant worker (red shirt, white apron) waves at you and a
    yellow marker / light beam floats above him.
 3. Ride up to him. "ভাই, আপনার অর্ডার রেডি!" appears; press E.
 4. He hands over the parcel, which flies onto your delivery box and is
    strapped on top. Mission status -> DELIVERY IN PROGRESS.
 5. A teal destination marker appears at the customer (Rafi bhai,
    শাপলা টাওয়ার, রোড ২). Follow the minimap (top-right) or the
    on-screen arrow: go north on the main road, turn LEFT (west) at the
    second intersection.
 6. Funny street events may happen on the way (see below).
 7. At the customer, "কাস্টমার অপেক্ষা করছে!" appears; press E.
 8. Short dialogue, the parcel is handed over, the customer cheers,
    DELIVERY COMPLETED / ডেলিভারি সফল! and +৳150.
 9. Choose "পরবর্তী অর্ডার" (next order — 3 different orders rotate)
    or "মিশন রিস্টার্ট" (restart from the beginning). Restart is also in
    the pause menu.
Traffic keeps to the LEFT, as in Bangladesh.


5. IMPLEMENTED FEATURES
-----------------------
World (all procedural 3D, ~250 m x 250 m, Mirpur-inspired)
- Main road + two side roads, two 4-way intersections, lane markings,
  zebra crossings, painted curbs, footpaths, a median with plants,
  roadside/construction barriers, 11 visible potholes.
- 100+ apartment buildings with balconies, laundry, AC units, rooftop
  water tanks, unfinished rooftop columns, shop shutters and Bangla
  signboards; restaurants (ঢাকা বিরিয়ানি, মামার হোটেল, খিচুড়ি ঘর),
  pharmacy, grocery (মুদির দোকান), fruit shop, garage, apartments.
- Tea stall (চায়ের আড্ডা), fuchka cart (ফুচকা কর্নার), jhalmuri cart,
  fruit crates, biryani pots with fire and steam, benches, dustbins,
  electric poles with tangled wires, street lights, trees, road signs,
  a banner across the road and a rooftop billboard.
- Hazy late-afternoon lighting, sky dome, fog, real-time shadows and
  glowing lights (Graphics: High).

Player
- 3D motorcycle: two spoked wheels, body, tank, seat, handlebar, mirrors,
  headlight, brake light, number plate, exhaust and an orange delivery box.
- 3D rider with helmet, jacket, pants, gloves and shoes; puts a foot down
  when stopped.
- Smooth acceleration, braking, reverse, strong brake, speed-dependent
  steering, wheel rotation, leaning, suspension bounce, third-person
  follow camera (avoids clipping into buildings), speed-based FOV.
- Collisions with buildings, poles, trees, stalls, barriers, traffic
  and people.

Mission system
- Restaurant pickup with waving / looking worker, floating marker,
  Bangla prompts, parcel hand-over animation, parcel strapped on the box.
- Customer delivery with waving customer, 3-line Bangla dialogue,
  hand-over, receive + happy animation, confetti, DELIVERY COMPLETED,
  ৳150 reward, customer star rating (time, crashes, bumping people).
- 3 rotating orders, restart, mission HUD with distance and timer.

Funny events (with a shared cooldown so they don't overlap)
- A: Rickshaw encounter — a rickshaw cuts across and blocks your lane,
  your bike slows automatically, the driver gestures, Bangla dialogue.
  One is guaranteed during the first delivery, later ones are random.
- B: Angry tea-stall owner — ride through the tea stall corner and the
  bench, stools and cups go flying; the owner gets angry, chases you for
  a few seconds, shouts, then gives up and the stall resets.
- C: Pothole surprise — suspension bounce, mud splash, camera shake,
  shaking delivery box, rider flails his arms, Bangla reaction.
- Extra street life: pedestrians who jump aside, bus conductor shouting
  "মিরপুর! মিরপুর!", honking when you block traffic, rickshaw bells.

Traffic & NPCs
- 1 CNG, 2 cycle rickshaws (pedalling drivers), 2 cars, 1 local bus
  (with a conductor hanging at the door) on waypoint loops, keeping to
  the left, slowing for each other and for you.
- 8 pedestrians on the footpaths, tea drinkers, vendors.

Dialogue & audio
- Reusable dialogue queue with Bangla subtitles and speech bubbles above
  characters; 25+ original Bangla lines.
- Uses the browser's Bengali text-to-speech voice when one exists
  (only one voice speaks at a time); subtitles are always shown.
- Web Audio synthesized sounds: engine (pitch follows speed), horn,
  traffic ambience, rickshaw bell, delivery chime, mission jingle,
  pothole thud, crash, cup clatter. Mute button / M key.

UI
- Main menu, pause menu, delivery-complete screen, mission panel,
  money + rating, minimap, speedometer with gear and brake lamp,
  key hints, interaction prompts, toasts, event banners.
- Graphics High / Low switch (Low turns off shadows/glow and renders at
  lower resolution for slower PCs). Layout adapts to the window size.


6. KNOWN LIMITATIONS
--------------------
- Internet is needed for Babylon.js (see section 2); offline the game
  shows an error message instead of starting.
- Bengali voice: Chrome on Windows usually has no Bengali text-to-speech
  voice, so dialogue is subtitle-only there. Edge may offer one.
- Tested in a headless Chromium browser with software rendering
  (full pickup -> delivery -> next order -> pause -> restart flow, all
  three events, no JavaScript errors). It was not tested on your own
  graphics card, so frame rate on your PC is unknown — if it feels slow,
  switch "Graphics" to Low in the menu or pause screen.
- Real sound playback and the speech voice could not be heard in the
  test environment; they use standard Web Audio / speechSynthesis APIs.
- Arcade physics: collisions use circles and boxes; the bike cannot
  fall over. Traffic follows fixed loops, U-turns near the closed road
  ends and has no traffic lights.
- The map is a compact demo block; road ends are closed with
  "রাস্তার কাজ চলছে" barriers.
- Keyboard only (no touch or gamepad controls).
- Graphics/sound settings are remembered with browser storage, which
  some browsers block for file:// pages (settings then reset on reload).
