# Cyril // 0xCyrildev

I build tools to answer questions I can't answer by just reading code.

Security work, for me, isn't a checklist — it's modeling a system until you understand its invariants well enough to know exactly where they'll break. Most of what's in this profile exists because I hit a wall doing research manually and decided to write something that wouldn't hit that wall again.

## How I think about problems

Model the system first — state, ownership, trust boundaries, who can call what and under what assumption. The checklist bugs are the easy 80%. The interesting bugs live in composed attack chains: things that are individually fine but break when chained across transactions, across modules, across chains. I'd rather spend an extra hour understanding *why* something is safe than assume it is because nothing on a checklist flagged it.

That mindset is basically what every tool below is trying to encode.

## Tools I've built

- **[`sui-invariant-fuzzer`](https://github.com/0xCyrildev/sui-invariant-fuzzer)** — property-based fuzzer for Sui Move. Typed object-pool resolution, boundary-biased value generation, a shrinker that actually delta-debugs instead of just backing off randomly.
- **[`sui-sec`](https://github.com/0xCyrildev/sui-sec)** — static bytecode scanner for Sui Move. Catches ability drift between source and bytecode, unsafe entry points, premature UID deletion — the stuff that's invisible unless you're diffing bytecode against source.
- **[`necropsy`](https://github.com/0xCyrildev/necropsy)** — post-exploit forensics for EVM. Replays historical transactions for free via Foundry, reconstructs the call tree, ranks net fund flow. Built because reading a block explorer after a hack is not how you actually figure out what happened.
- **[`echo`](https://github.com/0xCyrildev/echo)** — conflict scanner for Monad's parallel execution model. Caught its own false-positive bug mid-build (97.5% false conflict rate from a tracer misconfiguration) — fixing that taught me more about the execution model than the spec did.
- **[`rouge-kali`](https://github.com/0xCyrildev/rouge-kali)** — the framework that ties the above together into an actual audit workflow, with a confidence gate that refuses to let a finding call itself "confirmed" without a passing local PoC.
- `flank` — recon tooling for oracle architecture risk and RPC misconfiguration across EVM and Sui.
- `creed` — scans public repos at scale for leaked credentials, with verification (not just pattern matching) as the whole point.

## What I'm curious about right now

Cross-chain systems that decouple signing from settlement — threshold-signature architectures, MPC coordination, and where the failure modes hide when a system doesn't have single-chain liveness assumptions to lean on. It's the same question as everything else I work on: what does this system assume is always true, and what happens the one time it isn't.

---

Always interested in a hard bug or an interesting systems question. Reach out.
### Stack
`Rust` `Go` `Solidity` `Move` `Python` `Java` `C` `Foundry` `Sui CLI` `Typescript`

---

### Other interests 
When I'm not coding or breaking stuff, I'm watching anime, playing games or playing basketball. If you've got any tips for my bag, tell me please. I'm also open to anime recommendations.


### Find me
X : @zeroxcyril
Telegram : @zeroxCyril
