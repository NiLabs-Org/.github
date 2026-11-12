# NiLabs

**Run robot foundation models on any robot chip.**

NiLabs builds an open-source inference engine for vision-language-action (VLA) models. Faster, lower power, real-time, and verified to keep task success.

## The problem

Robotics is moving to large learned models such as OpenVLA, SmolVLA, π0 and GR00T. They are too slow and too power-hungry for the chips inside robots, so teams hand-optimize for weeks, tether robots to big GPUs, or ship jerky behavior.

Robot inference is not chatbot serving. It runs at batch size 1, on fixed-length action chunks, against a hard clock: a model that emits *k* actions per call on a robot running at *f* Hz has *k / f* to produce the next chunk. At one action and 30 Hz, that is 33 ms, on every call.

## What the engine will do

- Optimized code for each stage of a VLA: vision encoder, language backbone and action head
- Asynchronous inference, so the robot keeps moving while the next action chunk is computed
- Quantized model formats and a one-command converter from Hugging Face and LeRobot checkpoints
- Published benchmarks for latency, control rate and power on every supported chip, reported next to task success

## Status

Pre-release. The first target is one open VLA on one chip, benchmarked against stock PyTorch with task success matched. Code, benchmarks and the method will be published here under Apache-2.0.

## Work with us

We're looking for design partners: robot teams running VLAs onboard, and chip makers who want VLAs to run well on their silicon. Email [hello@nilabs.dev](mailto:hello@nilabs.dev).

[nilabs.dev](https://www.nilabs.dev) · [Manifesto](https://www.nilabs.dev/manifesto) · [@NiLabsOrg on X](https://x.com/NiLabsOrg)
