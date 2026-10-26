# Atari7800XT

[Video](https://youtu.be/LSctGXLyQ7Q)

The Atari 7800XT research and fantasy console initiative uses a fork of [test7800](https://github.com/jetsetilly/test7800) by JetSetIlly, which is licensed under the GNU General Public License v3.0, for prototyping, testing, demonstration, and research purposes. For usage information, see his page.

Atari 7800XT is currently in Phase 2, so what is present consists of:

- a simulation of a register that receives signals to change the background color instead of the active background color when a scanline is in the process of being displayed, which fixes visual flickering seen in the games Karateka and Super Huey UH-IX
- a simulated implementation of a dual bus concept which should increase CPU cycle counts from as low as 10% of its capability closer to 100% (tested with Double Dragon and appears to be operational)
- a simulated implementation of zero-wait on RAM for MARIA, which should have the same effect.

To see the MARIA v1.01 latch fix for Karateka and Super Huey UH-IX in action, compile the emulator with go build, open the command line from the file directory, and use `test7800.exe -delaybg=TRUE -run "directory of ROM file here"`. To run a game with zero-wait on RAM, the flag is `-fastram`. To run a game on a simulated dual bus layout, the flag is `-dualbus`.

This project is assisted by consultation with Gemini for historical and technological research, as well as understanding the existing codebase (I was not familiar with Go at the start and had never worked on emulators), troubleshooting, and evaluation of general approaches (getting a second opinion on if things would work the way I envisioned). All code is hand-written.

This project is licensed under the GNU General Public License v3.0.
