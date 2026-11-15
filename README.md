# Mission Mars · Project Ares 2050

Educational mobile game (for kids aged 7 to 12) about founding the first human colony on Mars.

**Story:** it's 2050, Earth is in bad shape and humanity needs a new home. You lead the crew of astronauts who must turn a Martian crater into a self-sufficient colony.

## How to play
- Open `index.html` in your phone's browser together with the `assets/` folder (building sprites). For everything to work properly, serve it from a web server (for example `python3 -m http.server`).
- Isometric view (40×40 tile map, 64×32 px tiles): drag to move the camera, pinch or use + / − to zoom, ⌂ to go back to the base.
- Tap **Build** (or tap the ground), choose a building and place it: the footprint shows green if the spot is valid and red if it isn't.
- Choose your name and 3 specialists (engineer, botanist, doctor, geologist, psychologist).
- Buildings: central base, corridors, solar panels, MOXIE plant (oxygen from CO₂), ice extractor, mining excavator, battery, bio-lab against perchlorates, greenhouse, vertical farm, regolith shelter (tap a crater to build it there), antenna, habitat (double capacity on lava tubes), mess hall, gym, robot workshop, nuclear microreactor and magnetic shield.
- Collect the cargo crates that arrive from Earth.
- Corridors only connect to each other and to building doors. A building not connected to the base produces 40% less and uses 50% more energy.
- Every sol has a day and a night: panels only work during the day, and at night you need batteries or a reactor.
- Buildings wear out and break down if they aren't maintained; over time long storms arrive, along with meteorites that badly damage everything in a 4×4 area (the magnetic shield prevents them).
- Mechanics unlock little by little: night (mission 1), connections (mission 2), wear (sol 4), upgrades (mission 4), food spoilage (mission 5), research (sol 6), limited storage (mission 7) and meteorites (mission 9 and sol 12).
- Crew of 6: you and 5 specialists chosen from 10, each with their own skill.
- Construction takes time: panels, extractor, excavator and battery 1 sol; MOXIE, lab, greenhouse, gym, antenna and mess hall 2; shelter, workshop, habitat and vertical farm 3; reactor and shield 4. Corridors are instant.
- Upgrade buildings up to level 3 (each level gives ×1.5 production or capacity); the level is shown on the map.
- Warnings before something happens (high wear, night-time energy, resources running out, weather forecast) and a confirmation when ending the sol if there are new warnings.
- The antenna (or the meteorologist) forecasts storms and cold snaps 1 or 2 sols in advance.
- The bio-lab researches 9 upgrades using the scientific method: first you predict what will happen, the experiment lasts a few sols and at the end the result is compared with your hypothesis.
- Every building has a "Why?" button that explains in two sentences why it works the way it does.
- Questions are about what just happened (after a storm, one about storms; when you build the MOXIE, one about CO₂).
- On the final screen, "Facts learned" shows all the questions answered, the experiments and the facts discovered.
- Final score based on colonists, buildings standing (and their levels), stored resources, speed or sols survived, and missions; with a saved high score.
- 25 achievements in 6 groups with a progress bar (for example "Perfect streak: 3/5"). They are saved separately from the game and are not lost when you start over or lose.

- Sizes: base 6×6 (connects to corridors at the ends of its 4 arms); MOXIE 1×3; habitat, greenhouse, vertical farm, extractor, shelter, reactor and shield 3×3; everything else 2×2; corridors 1×1. You must leave one free tile between different buildings; identical buildings and corridors can go side by side.
- Each colonist consumes oxygen, water and food every sol; almost everything uses energy.
- Face dust storms, solar storms, cold snaps, breakdowns, micrometeorites and decisions without immediate help from Earth (~20 min delay).
- Answer questions from mission control and unlock real NASA facts.
- Win by completing the 12 missions and reaching 30 colonists.

The game saves automatically in the browser.

## Laika, the base AI
- Laika, the base's artificial intelligence, stays with you the whole game with eight expressions (normal, explaining, thoughtful, surprised, happy, sad, worried and alarmed); if several things happen at once she shows the most important one.
- Her speech bubbles replace pop-up alerts; she stops you before ending the sol if something important is going on, announces the weather forecast and gives the step-by-step tutorial.
- Tapping her portrait opens her menu: current goal, general maintenance, science notebook, achievements, log and tip review.
- The images are in `assets/laika_*.png`; the emotion → image mapping is in `MOOD_IMG`, inside `index.html`.
- She tells her own story: tap the central base and press «Who are you?».
- At the start of every game, her button glows with a golden ring and a «Tap me!» sign until you tap it for the first time.

### Laika's voice
- **She speaks with a voice and the text appears little by little** (about 40 letters per second, a beep every 2–3 letters) only when she is the center of attention: welcome and tutorial tips, her story, victory or defeat, important events (storms, meteorites, ships, new mechanics), completed missions, achievements and urgent warnings.
- **Text appears all at once with no voice**: repeated bubble messages (construction underway, crate opened, maintenance, not enough materials), lists (goal, notebook, log, dictionary), things the player asks for by tapping something (Why?, glossary words) and quiz questions.
- So it doesn't get tiring: if she spoke less than 8 s ago, the next message comes out silently (except for the following pages of the same conversation); each type of message only has a voice the first few times (e.g. «construction finished», 2 times); the voice lasts at most 2.5 s even if the text keeps going.
- First tap while she's typing: the whole text appears and the voice stops. Second tap: next page or close the bubble. An event's options appear when the text finishes (or on the first tap), and that tap doesn't press anything underneath.
- The voice can be turned off separately in **Settings → Voice**, without muting music or sound effects. If the device has *reduce motion* turned on, the text appears all at once.

## Difficulty
It's chosen before the crew, for every new game (on the crew screen, «← Change» lets you choose again; hard mode asks for confirmation before starting):
- **Easy:** the base game. Goal of 30 colonists; the score is worth half.
- **Normal:** more disasters and meteorites, 30% more wear, building and research cost 25% more. Goal of 40 colonists.
- **Hard:** even more disasters, 70% more wear, 50% higher costs, buildings use 20% more energy and colonists consume 15% more. You start with more food (110) to make up for the consumption, Laika barely gives advice and the goal is 50 colonists; the score is worth 50% more.

Mission control's questions also depend on the difficulty: 18 on easy (ages 8-10), 18 on normal (11-13) and 25 on hard (14+). When they run out they are shuffled again without immediately repeating the most recent ones.

The regolith shelter doesn't need a connection to the base.

## Ships
- The more free beds and the better the antenna, the more colonists each ship brings (+2 per antenna level and +1 for every 4 free beds).
- From the antenna's info card you can **call a ship** right away by paying 40 materials (more on normal and hard).
- Dismantling returns half of everything paid, upgrades included.

## Glossary
- Difficult words are underlined in info cards, events and questions (only the first time in each text). When you tap them, Laika explains them in her bubble.
- Laika's menu has the **Dictionary**, with all the words grouped and the ones you've already looked up marked. Looking up 40 earns the *Walking dictionary* achievement.

## Music
- In the menus (title screen, story, difficulty, crew, journey and final screen) the menu music loops (`assets/musica_menu.mp3`, placeholder).
- During the game the difficulty's track plays (`assets/musica_facil.mp3`, `musica_normal.mp3`, `musica_dificil.mp3`): it starts at a random moment, fades out during its last 25 seconds and plays again after a 1 to 3 minute silence.
- It can be muted with the 🎵 button on the title screen or from Settings.

## Real space weather (NASA DONKI)
- Solar storms use real flares from NASA's DONKI catalog (CCMC, Goddard): date, GOES class (A, B, C, M, X) and active region. The stronger the class, the more damage they do without a shelter.
- The antenna announces the flare's class before it arrives; the science notebook keeps the flares you've lived through and there's an achievement, *Flare hunter*.
- To add more flares, paste the DONKI JSON response into `DONKI_RAW` inside `index.html`.

## Real science or fiction?
Every building, research project and fun fact has a label: ✅ **Real today** (it exists and is already in use), 🧪 **Being tested** (tested on a small scale or on Earth) or 🔮 **Idea for the future** (it doesn't exist yet). Laika explains it the first time you build something of each kind.

Each regolith shelter protects 12 people: during a solar storm, colonists who don't fit inside take damage.

## Sources
All the scientific data has its official source (priority NASA / JPL / ESA) in [`FUENTES.md`](FUENTES.md). In the game they can be viewed in **Settings → 📚 Sources**, with links to each page.
