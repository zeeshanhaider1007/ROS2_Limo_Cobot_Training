# ROS 2 & LIMO Cobot Training

**A hands-on, 4-day course that takes complete beginners from "what is a robot brain?" to driving a real mobile robot — mapping a room, navigating to a goal, and controlling a robot arm.**

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](./LICENSE)
[![ROS 2 Foxy](https://img.shields.io/badge/ROS%202-Foxy-blue.svg)](https://docs.ros.org/en/foxy/)
[![Ubuntu 20.04](https://img.shields.io/badge/Ubuntu-20.04-orange.svg)](https://releases.ubuntu.com/20.04/)
[![Level: Beginner](https://img.shields.io/badge/level-beginner-brightgreen.svg)](#who-is-this-for)

Delivered by the **Automated Systems & Computing Lab (ASCL)** · Funded/acknowledged by the **Research, Development and Innovation Authority (RDIA)**.

---

## 📖 About this course

This is a **free, self-contained slide course** for anyone who wants to learn ROS 2 by actually using it. Every day is one self-contained deck (PDF) built around a live demonstration: you start programs, watch a robot talk to itself, drive a real LIMO Cobot, and make it map and navigate a room.

The course assumes **no prior ROS, robotics, or Python experience**. Concepts are introduced with everyday analogies (a robot is a group chat; a service is a helpline; navigation is food delivery) before any command is run.

**Two trainings, four days:**

| Training | Days | Theme |
|----------|------|-------|
| **Training 1 — Fundamentals** | Days 1–2 | ROS 2 concepts, the CLI, and writing your first nodes |
| **Training 2 — On the Robot** | Days 3–4 | LIMO hardware bring-up, SLAM, navigation, and the cobot arm |

---

## 🎯 Who is this for?

- **Undergraduate / BS-level students** in robotics, mechatronics, computer science, or electrical engineering.
- **Self-learners** who want a guided, practical path into ROS 2.
- **Instructors** looking for ready-to-teach decks, timings, and labs.
- Anyone curious about mobile robots who can comfortably use a Linux terminal.

**Prerequisites:** none required. Basic familiarity with the Linux terminal helps, but Day 2 opens with a "5-minute terminal survival kit."

---

## 🗓️ Course at a glance

| Day | Deck | Focus | Hands-on highlight |
|-----|------|-------|--------------------|
| **1** | [📄 `day1-ros2-concepts.pdf`](./day1-ros2-concepts.pdf) | What is ROS & ROS 2? | Drive **turtlesim** and inspect the live ROS graph |
| **2** | [📄 `day2-ros2-basics.pdf`](./day2-ros2-basics.pdf) | ROS 2 CLI + first nodes | Write a **talker** & **listener** in Python |
| **3** | [📄 `day3-limo-bringup.pdf`](./day3-limo-bringup.pdf) | Meet the LIMO Cobot | Connect, bring up the robot, and **drive it** |
| **4** | [📄 `day4-limo-applications.pdf`](./day4-limo-applications.pdf) | SLAM, Navigation & the Arm | **Map a room**, navigate autonomously, move the arm |

**Each session is ~1 hour:** ~15 min theory → ~30–35 min hands-on → ~5–10 min recap & quiz. The golden rule: **hands-on time is sacred — never cut the demo.**

---

## 📚 Day-by-day breakdown

<details open>
<summary><strong>Day 1 — What is ROS & ROS 2?</strong> · <a href="./day1-ros2-concepts.pdf">deck</a></summary>

Build the mental model behind every robot, then watch it come alive.

- **What is ROS?** — the sense → think → act loop, and the "group chat" that connects a robot's parts.
- **The ROS Graph** — why a robot is many small programs, not one big one; ROS 1 vs ROS 2 in plain words.
- **Core concepts** — node, topic, message, service, action, and parameter, each with an everyday analogy.
- **Lab — turtlesim** — open three terminals, start a real ROS 2 system, and drive a turtle with your keyboard.
- **Be the detective** — `ros2 node list`, `ros2 topic list/echo`, `ros2 topic hz`, `rqt_graph`, and a service call to teleport the turtle.
- **Recap** — a 6-question quick check (answers revealed on each slide).

**By the end of Day 1 you can:** explain ROS in one sentence, map a robot part to each step of sense → think → act, define the 6 core concepts, and inspect a running ROS 2 system.
</details>

<details open>
<summary><strong>Day 2 — ROS 2 Hands-On: CLI + First Nodes</strong> · <a href="./day2-ros2-basics.pdf">deck</a></summary>

Go from *using* ROS 2 to *writing* it.

- **ROS 2 CLI tools** — the `ros2` pattern (`ros2 <thing> <action>`), and the five superpowers: node, topic, interface, service, and param.
- **Watch and measure** — `ros2 topic echo` and `ros2 topic hz` on a live system.
- **Workspaces & packages** — workspace → package → code; create a workspace, create an `ament_python` package, then `colcon build` and source it.
- **Lab — publisher & subscriber** — write `talker.py` and `listener.py` in Python, register them, and run them in two terminals.
- **See it as a picture** — confirm the graph in `rqt_graph` and explain why the two nodes found each other with zero configuration.
- **Recap** — a 6-question quick check.

**By the end of Day 2 you can:** inspect any live ROS 2 system, create and build your own package, and write a publisher and a subscriber that talk over a topic.
</details>

<details open>
<summary><strong>Day 3 — Meet the LIMO Cobot: Hardware & Bring-Up</strong> · <a href="./day3-limo-bringup.pdf">deck</a></summary>

The real robot arrives — the same concepts, now driving hardware.

- **What is the LIMO Cobot?** — a desktop mobile robot by AgileX (partnered with Elephant Robotics), built for learning ROS, running on an NVIDIA **Jetson Orin Nano** with **ROS 2 Foxy**.
- **Four motion modes, one chassis** — and how to read the robot's RGB status light.
- **Sensors & topics** — each sensor is a node publishing a topic (LiDAR → `/scan`, odometry → `/odom`, speed commands → `/cmd_vel`).
- **Safety rules** — wheels on the ground, feet clear, start slow.
- **Connect & bring-up** — remote in with **NoMachine**, live the `limo_base` chassis driver, and verify the topics are alive.
- **Lab — drive & sense** — command motion with a single `Twist` message, drive smoothly with `teleop_twist_keyboard`, and view the LiDAR scan and odometry live in **RViz2**.
- **Troubleshooting** — "I published `/cmd_vel` but it didn't move" and what to check.
- **Recap** — a 6-question quick check.
</details>

<details open>
<summary><strong>Day 4 — Applications: SLAM, Navigation & the Arm</strong> · <a href="./day4-limo-applications.pdf">deck</a></summary>

Put it all together: the robot senses, understands, and acts.

- **SLAM with Cartographer** — the chicken-and-egg problem, loop closure, and building a map live while driving the room.
- **Save the map** — `map_saver_cli` produces a `.pgm` (the picture) and `.yaml` (metadata).
- **Navigation with Nav2** — AMCL, costmaps, and the global/local planners; set a **2D Pose Estimate**, then send a **2D Nav Goal** and watch the robot drive itself.
- **Multi-point navigation** — queue several goals in a row.
- **The cobot arm** — the **myCobot 280 M5**, direct joint control, and path planning with **MoveIt2**.
- **Mobile grasping pipeline** — the full combine-everything flow.
- **Final check** — a 7-question quiz (pass ≥ 70%) plus the **capstone**: *design a delivery robot that carries an object from point A to point B.*

**By the end of Day 4 you can:** build and save a map, make the LIMO navigate autonomously, and control the cobot arm — using the same nodes, topics, and messages from Day 1.
</details>

---

## 🖥️ Requirements

### Software (Ubuntu 20.04 + ROS 2 Foxy)
- **Ubuntu 20.04 LTS** and **ROS 2 Foxy Fitzroy** (desktop install)
- **turtlesim** — Days 1–2 labs
- **colcon** — building packages (Day 2)
- **Cartographer** — SLAM (Day 4)
- **Nav2** — navigation stack (Day 4)
- **MoveIt 2** — arm motion planning (Day 4)
- **RViz2** and **rqt** (`rqt_graph`) — visualisation
- **Python 3** — publisher/subscriber lab
- **NoMachine** (or similar remote desktop) — connecting to the robot (Day 3)

Install ROS 2 Foxy by following the official guide: <https://docs.ros.org/en/foxy/Installation.html>

### Hardware (Days 3–4)
- **LIMO Cobot** (AgileX Robotics / Elephant Robotics): LIMO PRO 4-wheel mobile base, NVIDIA Jetson Orin Nano, and LiDAR.
- **myCobot 280 M5** arm for the Day 4 manipulation lab.
- A laptop running Ubuntu 20.04 + ROS 2 Foxy, on the same network as the robot.

> Don't have the hardware? Days 1–2 (and much of Day 4's theory) run entirely on a laptop with turtlesim and Gazebo.

---

## 🚀 How to use this material

**If you're learning:**
1. Download the deck for the day from the table above (or clone this repo).
2. Read the slides in any PDF viewer — use **full-screen / presentation mode** to click through them like slides.
3. Run every command you see. The labs are copy-paste ready.
4. Take the quiz at the end of each day and aim for **≥ 70%**.

**If you're teaching:**
1. Each deck is a complete ~1-hour session with a built-in agenda and timings.
2. Keep the theory blocks tight — protect the hands-on time.
3. Run the Day 3 and Day 4 labs on the real hardware yourself before class, and pre-save a map as a fallback for Day 4.

---

## 🔗 Going further

- **ROS 2 documentation (Foxy):** <https://docs.ros.org/en/foxy/>
- **turtlesim tutorial:** <https://docs.ros.org/en/foxy/Tutorials/Beginner-CLI-Tools/Introducing-Turtlesim/Introducing-Turtlesim.html>
- **Cartographer ROS:** <https://google-cartographer-ros.readthedocs.io/>
- **Nav2:** <https://navigation.ros.org/>
- **MoveIt 2:** <https://moveit.picknik.ai/>
- **LIMO Cobot:** <https://www.elephantrobotics.com/en/limo-cobot-en/>
- **myCobot 280 M5:** <https://www.elephantrobotics.com/en/mycobot-280-m5-en/>

---

## 🙌 Credits & acknowledgments

**Lab:** Automated Systems & Computing Lab (**ASCL**)

**Lab Leader:** Prof. **Ahmad Taher Azar**

**Trainers:**
- Dr **Saim Ahmed** — Day 1 & Day 3
- Eng. **Zeeshan Haider** — Day 2 & Day 4

**Funding acknowledgment:** Research, Development and Innovation Authority (**RDIA**).

This training material was prepared and delivered as part of ASCL's hands-on robotics training programme. If you use it, please keep the credits above intact.

---

## 📄 License

This work is licensed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license — see [`LICENSE`](./LICENSE).

You are free to **share** and **adapt** the material for any purpose, including commercially, as long as you give **appropriate credit**, link to the license, and indicate if changes were made.

---

## 🤝 Contributing

Found a typo, a broken command, or want to add a language translation? Issues and pull requests are welcome. When reporting a command that fails, please include your ROS 2 distribution and the exact error output.
