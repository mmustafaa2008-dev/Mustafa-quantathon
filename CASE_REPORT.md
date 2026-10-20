# ECHO — Case Report

**Team:** QUANTUM WARRIOR · **Author:** MUHAMMAD MUSTAFA · **Entangled Minds: The Quantathon, NED
Notebook:** `ECHO\_Quantathon.ipynb` (runs top to bottom; Qiskit + Aer simulator)
**Modules:** 01, 03, 05 (mandatory) · 04 (stretch) · 06 (bonus)

\---

## 1\. Verdict

**Dr. Zara Mahmud mistook an echo for a voice.** ECHO did not send a message faster than light. Her twin detectors always agreed, but agreement is correlation, not communication. Every test we ran shows the receiver's statistics are completely independent of anything the sender does.

**Confidence:** about 95% on the physics claim (ECHO was not faster-than-light). Low on the human question: the modules we completed do not identify who, if anyone, helped her or tampered with the logs.

## 2\. Key evidence (module by module)

|Module|What we did|What it tells us|
|-|-|-|
|01 Gatekeeper|X gives 1 every shot; H gives \~50/50; H,H gives 0 every shot; X on qubits 0 and 2 gives `101`|Superposition is not randomness: two H gates interfere and the result becomes certain.|
|03 Two Observers|Bell pair (H + CNOT) gives only `00`/`11`. A classical pre-agreed secret coin gives an identical histogram. CHSH S ≈ 2.82 (classical limit 2). Bob's marginal stays 50/50 whether Alice measures in Z or X.|"Always agreeing" does not prove a quantum link, and even a real quantum link cannot carry a message (no-signalling). **This is the crack in ECHO.**|
|05 Damaged Message|Majority vote over 32 triples decodes to the bits of **`ECHO`**. 20 of 32 triples had one flipped bit. Two flips in a triple make the vote silently wrong. A 3-qubit bit-flip code corrects a single error without copying the qubit.|The repetition code corrects 1 flip and detects 2; a qubit cannot simply be copied three times (no-cloning).|
|04 Erased Measurement|`X,H,H` gives 1; `H,X,H` gives 0 (because HXH = Z). H, measure, H gives 50/50.|Reversible (unitary) steps can be undone; a mid-circuit measurement cannot. ARIA's "it changed when observed" is real physics, but it is not evidence of tampering.|
|06 Impossible Claim|Teleportation circuit: with the 2 classical bits and corrections, fidelity is 1.0 for every outcome. Without them, Bob's state averages to I/2 (fidelity 0.5, and independent of the message).|Teleportation needs a classical channel, so it cannot be faster than light.|

## 3\. The crux: could the detectors send a message, or only agree?

They only agreed. (1) A hidden shared coin reproduces the "always agree" data exactly, so Zara's observation alone does not prove entanglement. (2) Even for a genuinely entangled pair (CHSH S ≈ 2.82 > 2), Bob's outcomes are 50/50 regardless of Alice's measurement choice, so Alice cannot encode a bit. (3) Teleportation, her "grand claim", requires 2 ordinary classical bits, which travel no faster than light.

## 4\. Strongest competing theory

*"ECHO was a real breakthrough."* We reject it because no-signalling held in every test, and the one protocol that does move a quantum state (teleportation) needs a classical channel. If Zara had shown Bob's statistics changing with Alice's choice, we would revise this.

## 5\. The human mystery (what we can and cannot say)

Our quantum modules cannot name a culprit. The suspects' claims (Vance, Rao, Noor, ARIA) are **claims**, not facts. We did **not** complete Module 02 (the "honest coin" seed), which is where evidence about whether the trigger was deliberately biased would come from, so we make no accusation. The one thing physics does let us say: ARIA's excuse that logs "changed because they were observed" does not by itself explain a deleted or altered log.

## 6\. Limitations

* Everything ran on an ideal, noiseless simulator: no detector loopholes, no hardware noise.
* The Module 06 teleportation circuit was built by us from the standard protocol, not the recovered circuit from the original notebook.
* We did not complete Module 02, so we cannot say anything about the seed bias.
* The note "beneath" the Module 05 message was not available to us.

## 7\. Next experiment

A CHSH run with randomly chosen measurement settings on both sides, plus a timestamped, hash-checked audit of the machine logs and ARIA's schedule configuration history (who configured the schedule, and when). Finishing Module 02 (measure the seed circuit, quantify the bias, and compute how many shots are needed to be sure it is not a fair coin).

## 8\. References and AI use

* Nielsen \& Chuang, *Quantum Computation and Quantum Information* (Bell states, teleportation, error correction).
* Clauser–Horne–Shimony–Holt (1969), the CHSH inequality.
* Qiskit documentation (qiskit.org), Qiskit Aer simulator.
* Wootters \& Zurek (1982), the no-cloning theorem.
* **AI use:** I used Claude (Anthropic) to help write the notebook code and the first draft of this report. I then ran the whole notebook myself in Google Colab and checked that every cell produces the outputs shown. I went through each module to understand why it works (for example why H,H returns 0 because of interference, why a classical shared secret gives the same histogram as a Bell pair, why CHSH above 2 still cannot send a message, and why teleportation needs two classical bits). Module 02 and the original preloaded circuits were not completed or used, as stated in the limitations.

