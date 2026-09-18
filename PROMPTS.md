# Air 2 3D Lab — Voice prompt catalog

Paste-ready lines for the optional Voice assistant. Copy one into the prompt field (or say it with **Mic**), then tap **Send**.

The agent picks tools from your wording. You do not need to name tools.

Play listing: [Air 2 3D Lab](https://play.google.com/store/apps/details?id=com.xreal.handshapes)  
How to move in XR: [`VR-UI-NAVIGATE.md`](VR-UI-NAVIGATE.md)  
Privacy (what **Send** uploads): [`PRIVACY.md`](PRIVACY.md)

---

## How to use Voice

1. Poke **Menu** → **Environment** → enable **Voice**.
2. Enter your own cloud API key (Gemini, Claude, OpenAI, Kimi, or xAI) and pick a **vision** model if you want the agent to see photos or the live view.
3. Tap **Mic**, edit the text if you want, then **Send**. Nothing is uploaded until Send.
4. **Conv** keeps the session. The model sees the last 6 user turns. Log: `Home/Conversations/{Env}.txt`.

**Tips**

- Dimensions are **meters** unless you say mm or cm.
- **Name** objects so later prompts can say “the wall” instead of “object 2”.
- Prefer **one** request per Send for CAD, arrays, and surfaces (not “and then also…” ten times).
- Punch / poke-to-score uses a **closed fist** or pinch-grab — not poking Menu buttons.
- Assemble mates are **hands**, not Voice. Poke **Assemble**, hold two features, Apply.

---

## Contents

- [First five minutes](#first-five-minutes)
- [Spawn, look, name](#spawn-look-name)
- [Duplicate / group](#duplicate--group)
- [Color, texture, scale, lock, text](#color-texture-scale-lock-text)
- [Move and animate](#move-and-animate)
- [Sketch and solids](#sketch-and-solids)
- [Scripting and arrays](#scripting-and-arrays)
- [Surfaces](#surfaces)
- [Images and drawing](#images-and-drawing)
- [Models (STL / glTF)](#models-stl--gltf)
- [Video](#video)
- [Physics, throw, punch](#physics-throw-punch)
- [Kinematic joints](#kinematic-joints)
- [PhysX gravity hinges](#physx-gravity-hinges)
- [Temporary effects](#temporary-effects)
- [Games and behaviors](#games-and-behaviors)
- [Email and SMS](#email-and-sms)
- [Agent pokes VR buttons](#agent-pokes-vr-buttons)
- [Save](#save)

---

## First five minutes

Starter set. Say them in order in an empty room.

- "Add a cube named Plate blank and a cylinder named Peg in front of me."
- "On an XY plane, sketch a 12 by 12 centimeter square, extrude it 4 centimeters, name it Plate, then cut a 3 centimeter circular hole through the middle."
- "Group Plate and Peg into one object named Fixture."
- "Paint Fixture blue."
- "Spin Fixture slowly around Y."
- "Look at what I see."
- "Save this environment as first session."

If the sketch line splits, send two:

- "Sketch a 12 cm square on XY and extrude 4 cm. Name it Plate."
- "Cut a 3 cm circular hole through the middle."

---

## Spawn, look, name

- "Make a red cube named Target in front of me, then a smaller blue sphere 30 cm to its right."
- "Spawn a red cube named Block."
- "What's in the scene? Name the closest object to me."
- "Name that solid Rocket."

---

## Duplicate / group

- "Duplicate that cube 4 times in a row, 20 cm apart, then group them as wall."
- "Group Plate and Peg into one object named Fixture."
- "Group the last two objects as Fixture."
- "Ungroup Fixture."

---

## Color, texture, scale, lock, text

- "Make the cube red."
- "Paint Fixture blue."
- "Make Fixture orange."
- "Wood texture on object 0."
- "Scale the sphere up."
- "Lock the cube."
- "Unlock Target."
- "Change that label to Hello."
- "Write Hello on the cube."
- "Make that surface text blue and bold."
- "Put the text on the other side."
- "Yellow background on that text."
- "Mirror it horizontally."

---

## Move and animate

- "Move the cube 0.3 meters along X."
- "Place Oval 20 cm to my right, 10 cm up, 40 cm in front."
- "Animate the sphere rotating 90 degrees around Y over 2 seconds."
- "Animate that sphere in an elliptic orbit around me, looping."
- "Animate the cube along a sine-wave path 40 cm forward."
- "Spin Fixture slowly around Y."
- "Create a loop animation called spin that rotates Fixture around Y."
- "Create a composite animation on Fixture: rotate, then spiral, then a square path."
- "Stop the spin animation."
- "Stop all animations."

---

## Sketch and solids

These should stay **one** Send when you can.

- "On a vertical plane, sketch a 10 cm circle and extrude it 3 cm. Name it washer."
- "Sketch a sine-wave profile and revolve it into a vase."
- "On an XY plane, sketch a 12 by 12 centimeter square, extrude it 4 centimeters, name it Plate, then cut a 3 centimeter circular hole through the middle."
- "Create an XY sketch, add a 10 cm rectangle, extrude 3 cm."
- "Add a 2 cm circle on the selected region and cut a hole through."
- "Next to the fixture, sketch a 6 centimeter tall profile and revolve it 360 degrees into a solid. Name it Knob."
- "Add a vertical construction axis and revolve the selected region 360 degrees."

---

## Scripting and arrays

Each line should be **one** tool round (not dozens of separate spawn calls). Grab the result; **Save Env** keeps it.

- "Make a white canvas named RosePlate and draw a 4-petal polar rose in dark red, centered."
- "On RosePlate, overlay a yellow 3-cycle sine wave, unfilled polyline."
- "On a horizontal sketch plane, add a closed 16×10 cm ellipse as a parametric curve, then extrude 2 cm. Name it Oval."
- "On the active plane, add an open 20 cm sine-wave stroke, 2 cycles — do not close it."
- "Spawn 12 yellow spheres in a 30 cm ring and group them as Halo."
- "Make a 3 by 4 grid of blue cubes, 15 cm apart."
- "Spawn 8 red cubes along a sine wave 40 cm forward, 8 cm amplitude."
- "Using one local script, spawn 10 small cyan spheres on a 25 cm circle. Do not call spawn_shape ten times."
- "With one run_script: 8 cubes in a 20 cm ring; odd indices red, even blue. Use if on the loop index."
- "One script: white canvas Locus, then 5 parametric circles radius 0.12+0.04*i on that canvas."
- "run_script: spawn cube peg, then repeat 6: duplicate and place each 8 cm further up."

---

## Surfaces

Thin sheets, not sketch solids. Holes still only cut planar extrudes.

- "Make a torus in front of me, ring 12 cm, tube 4 cm, named Donut."
- "Make a 30 cm wavy square sheet with a 3 cm sine bump, named Ripple."
- "Loft a vase: 8 cm circle at the base, 12 cm at 8 cm up, 5 cm at 16 cm up. Name it Vase."
- "Sweep a 2 cm tube along a helix, 8 cm radius, 20 cm tall. Name it Spring."
- "Sweep a 3 cm tube 40 cm forward, tapering to 1 cm. Name it Horn."
- "Make a flat 3×3 NURBS plane 20 cm square, named NurbsFlat."
- "Make a bicubic NURBS pillow from a 4×4 net, center CVs raised 8 cm, named Pillow."

---

## Images and drawing

Needs a **vision** model. `load_image` only places the plate — the agent does not see pixels until you ask it to look. Drawing does not overwrite Home until you save.

Put a `.jpg` / `.png` / `.webp` in your Home folder first (Menu → **STLs** → **Add**), or load by Voice.

### Load a photo

- "List images in Home, then place photo.jpg in front of me."
- "Load the kitchen photo from Home in front of me."

### Look and draw

- "Look at that image and tell me what it says."
- "Look at that Image and read the title."
- "Look at that photo and read the label."
- "Look at that photo and circle the title in red."
- "Look at the floor-plan photo and circle the kitchen in red."
- "Highlight that paragraph in yellow, then label it Title with a box."
- "Copy the logo from the kitchen photo onto the top-left of canvas Sketch."
- "Stamp the top-right quarter of photo A onto the center of canvas B."
- "On that photo, blur everything except a rectangle around the title."
- "Rotate the kitchen region 15 degrees clockwise."
- "Paint a soft red brush stroke along the path I describe."
- "Draw a smooth spline through those four corners in blue."
- "Circle the title in red."

### Canvas

- "Make a white canvas named Sketch and draw a house: brown rect, triangle roof, blue door."
- "Make a white canvas named RosePlate and draw a 4-petal polar rose in dark red, centered."
- "On the canvas, draw a 12-petal rose with a parametric curve."
- "Undo the last drawing on the canvas. Reset the photo to the original."

### Save to Home

- "Save image Sketch as house_plan.png"
- "Save that photo as photos/kitchen_marked.png"
- "Save image RosePlate as rose.png"
- "Save image as kitchen_marked.png"

### Live view

- "Look at what I see."
- "Take a picture of the view."

---

## Models (STL / glTF)

Files live in the Home folder you granted (same place as photos).

- "What's in my Home folder? List the glb files."
- "Load the drone glb from Home and play its animation."
- "Load the bracket STL from Home."
- "What animations does the robot have?"
- "Loop Walk on Robot."
- "Wave once."
- "Stop the robot animation."
- "Walk the robot forward 1 meter."

---

## Video

Spawn a **Video screen** first (Menu → Shapes, or Voice). Share clips from Gallery → **Air 2 3D Lab videos**.

- "What videos do I have?"
- "Play the holiday clip on the video screen."
- "Stop the video."

---

## Physics, throw, punch

Shapes **float** until you turn physics on. Spawn a **large flat locked cube as a floor** first, or things fall away. Then pinch-throw or fist-punch.

- "Spawn a large flat cube, lock it as the floor, then a sphere a meter above. Turn on gravity and bounce."
- "Spawn a sphere a meter above the table, turn on gravity and make it bouncy."
- "Give that cube physics with friction so it slides then stops on the floor. Freeze Y so it can't fall through."
- "Give that cube physics with friction so it slides then stops. Freeze Y so it can't fall through."
- "Flick the ball forward with an impulse. I should be able to pinch-throw it too."
- "Flick the ball forward. I should be able to pinch-throw it too."
- "Give that cube physics so I can punch it with a fist."
- "Put the center of mass off to the side so it tumbles when it falls."
- "Hollow that cube into a pool (open top), lock it, and drop a sphere in with gravity."

---

## Kinematic joints

Leftover motion (hinge, slide, ball) — not gravity. Lock the frame. Pinch-grab the moving part. These refuse objects that already have an Assemble mate.

- "Hinge the cube named Door to the locked cube named Frame."
- "Put a ball joint between those two spheres."
- "Make the small cube slide on the tall cube's Y axis."
- "Spawn a tall thin box named Door and a tall box named Frame next to it. Lock the Frame. Set a kinematic hinge between Door and Frame along their vertical axes with limits 0 to 90 degrees."
- "Spawn a flat locked board and a small cube on top of it. Set a planar joint between the cube's bottom face and the board's top face with limits -45 to 45 degrees."
- "Spawn a long locked rail box and a small slider cube. Set a prismatic joint along the rail's longest axis with limits -0.3 to 0.3."
- "Spawn three capsules in a row named Arm1, Arm2, Arm3. Ball-joint Arm1 to Arm2 and Arm2 to Arm3, then animate Arm1 in a circle."

If a 0–90° hinge stops on the wrong side, retry with −90–0.

---

## PhysX gravity hinges

Real swing with momentum (door, pendulum). Exclusive with Assemble mates **and** kinematic joints. Not saved in `.hse`.

- "Hinge the door on its left edge to the locked frame so it swings shut on a spring."
- "Make that capsule a pendulum swinging from its top."
- "Spawn a capsule named Bob about 1.5 m up and give it a physics hinge to the world at its top point with the axis on Z."
- "Spawn a locked frame box and a door panel beside it. Hinge the door on its edge to the frame with physics, limits 0 to 110 degrees, and a light spring pulling it closed. Then push it open with an impulse."
- "Spawn a locked post and a paddle. Physics-hinge the paddle to the post around Y with motor velocity 90 and motor force 10."

Sanity checks (should **refuse**):

- After a physics hinge is on: "Mate that door to the frame."
- After the pendulum is swinging: "Set a kinematic hinge on the pendulum."

---

## Temporary effects

Overlays, not grabable scene objects. Not saved. Not in the 64-object cap.

### Beams

- "Draw a cyan laser 1.5 m forward from in front of me, fade out in half a second."
- "Fire a red tracer from the cube named Blaster along its forward axis, lasting 0.4 seconds."
- "Draw a green laser from Blaster to Target."

### Clusters

- "Puff a white smoke cloud in front of me that rises and fades in 3 seconds."
- "Flash a yellow burst on the cube named Target."
- "Orange explosion puff at Target — expand and fade."

### Ribbons and sheets

- "Sweep a thin orange trail 1 meter forward from in front of me."
- "Make a small orange flame sheet in front of me that rises and fades for 4 seconds."
- "Put a waving flag sheet 40 cm in front of me for 10 seconds."
- "Shockwave: a thin expanding sheet around Target that fades in a second."

### Steer a live overlay

Ask for a long duration (up to 30 seconds) so there is time to steer it.

- "Make a cloud in front of me that lasts 20 seconds, then orbit it slowly on XZ."
- "Spin that smoke overlay around Y for 8 seconds."
- "Move the flame 30 cm up over 2 seconds."

### Hits and repeating shots

Punch with a **closed fist**, or pinch-grab.

- "Make a cube named Target. When any laser hits it, turn it green, beep, and add a point."
- "Cube named Blaster in my hand space, cube named Target a meter in front. When I punch Blaster, fire a colliding red tracer along its forward. When a tracer hits Target, score and flash."
- "When I punch the cube named Blaster, fire a red tracer along its forward axis."
- "Every half second, fire a short cyan laser from Blaster along forward."
- "When I punch Blaster, puff smoke from its muzzle."

---

## Games and behaviors

Rules keep running without another LLM round-trip.

- "Make a game: three cubes in a row and score starting at 0. When I poke a cube it turns green, beeps, and adds a point. At 3 points make them gold and play a win tone."
- "This sphere is an alarm: within 15 cm of my hand it flashes red and beeps; when I leave it goes blue and quiet."

Poke-to-score: **closed fist** or pinch-grab, not Menu pokes.

---

## Email and SMS

Uses the **phone address book**. The first Send after you name a person may ask for **Contacts**. Drafts open Messages / mail on the phone — glance at the phone to save or tap Send.

- "Who in my contacts is named Dana?"
- "Draft a text to Dana that I'm 10 minutes late."
- "Email Alex a draft about the bracket review — subject Workshop notes."
- "Send an SMS to +40 721 000 000 saying the print is done."

If several people match, the agent should ask which one.

---

## Agent pokes VR buttons

The agent does **not** move your hands. It looks at the view, then pokes a named control.

- "What buttons am I looking at?"
- "Poke Hide on the menu."
- "Look at what I see."

---

## Save

- "Save this environment as poke game."
- "Save this environment as first session."
- "Load environment poke game."

You can also Save / Load from Menu → **Environment**.
