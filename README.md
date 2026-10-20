# ECHO --- The Signal That Was Never Sent

**Project:** The Quantathon --- NED University\
**Team:** QUANTUM WARRIOR\
**Author:** Muhammad Mustafa\
**Notebook:** `ECHO_Quantathon_Solution_M.Mustafa.ipynb`\
**Simulator:** Qiskit Aer

## Overview

This project investigates the fictional ECHO case: whether quantum
entanglement can be used to send a message faster than light. Using
quantum circuits and simulations, we examine single-qubit gates,
correlations between observers, error correction, measurement, and
quantum teleportation.

Our conclusion is that **entanglement creates correlations, but it does
not allow faster-than-light communication**. A receiver's local
measurement statistics do not reveal the sender's choices. Quantum
teleportation also requires two classical bits, which cannot travel
faster than light.

## Modules Covered

  -----------------------------------------------------------------------
  Module                  Status                  Main result
  ----------------------- ----------------------- -----------------------
  **01 --- The            Mandatory               `X` flips `0` to `1`;
  Gatekeeper**                                    `H` produces a 50/50
                                                  measurement
                                                  distribution from `0`;
                                                  applying `H` twice
                                                  returns the state to
                                                  `0`. The circuit also
                                                  creates the bit pattern
                                                  `101`.

  **03 --- The Two        Mandatory               A Bell pair produces
  Observers**                                     correlated outcomes. A
                                                  pre-agreed classical
                                                  bit can reproduce
                                                  agreement in one
                                                  measurement setting, so
                                                  agreement alone does
                                                  not establish quantum
                                                  entanglement. A CHSH
                                                  test distinguishes the
                                                  quantum correlations
                                                  from local classical
                                                  models.

  **05 --- The Damaged    Mandatory               Majority voting over 32
  Message**                                       received bit triples
                                                  decodes the message
                                                  `ECHO`. The repetition
                                                  scheme corrects one bit
                                                  flip per triple, but
                                                  two flips can make the
                                                  result silently wrong.
                                                  The notebook also
                                                  demonstrates a
                                                  three-qubit bit-flip
                                                  error-correction
                                                  circuit.

  **04 --- The Erased     Stretch                 Demonstrates reversible
  Measurement**                                   gate sequences and how
                                                  an intermediate
                                                  measurement changes the
                                                  state and prevents the
                                                  original evolution from
                                                  being simply undone.

  **06 --- The Impossible Bonus                   Simulates quantum
  Claim**                                         teleportation and
                                                  compares the receiver's
                                                  state with and without
                                                  the classical
                                                  measurement results and
                                                  correction operations.
                                                  Without the classical
                                                  information, the
                                                  receiver cannot recover
                                                  the message state.
  -----------------------------------------------------------------------

**Not completed:** Module 02 --- The Honest Coin. As a result, this
project does not draw conclusions about the seed circuit's possible
bias.

## Key Findings

-   **Superposition and interference:** Measurement probabilities can
    look random after one gate, while a later gate can make the final
    result deterministic.
-   **Correlation is not communication:** Bell-pair measurements can
    agree, but agreement by itself is not proof that information has
    been sent.
-   **No-signalling:** The receiver's local statistics remain
    independent of the sender's measurement choice.
-   **Error correction:** A three-bit repetition code corrects one bit
    flip per triple by majority vote. It cannot guarantee recovery if
    two bits in the same triple are flipped.
-   **No-cloning:** An unknown quantum state cannot simply be copied
    into three independent identical qubits. Quantum error correction
    instead encodes information across entangled qubits and uses error
    syndromes.
-   **Teleportation needs classical communication:** The receiver needs
    the sender's two classical measurement bits to apply the appropriate
    corrections.

## Final Verdict

**Dr. Zara Mahmud mistook an echo for a voice.** The simulations support
the conclusion that ECHO did not send a message faster than light.
Entanglement can produce non-classical correlations, but the receiver's
local statistics do not depend on the sender's choices. Quantum
teleportation also requires a classical channel.

Our confidence is high in the physics conclusion, but the experiments do
**not** identify who may have altered the logs or explain why Zara
disappeared. The suspects' statements are not treated as proof.

## Run the Notebook

1.  Open [Google Colab](https://colab.research.google.com/).
2.  Upload `ECHO_Quantathon_Solution_M.Mustafa.ipynb`.
3.  Run the notebook cells from top to bottom.
4.  The first code cell installs the required packages; the notebook
    uses Qiskit and Qiskit Aer to build and simulate circuits.

### Main dependencies

-   `qiskit`
-   `qiskit-aer`
-   `numpy`
-   `matplotlib`
-   `pylatexenc`

The notebook is designed for simulation and does not require physical
quantum hardware.

## Limitations

-   Results are from an ideal simulator and do not model all real-device
    noise or detector loopholes.
-   Module 06 uses a teleportation circuit implemented for this
    solution; it may differ from any preloaded circuit in the original
    challenge notebook.
-   Module 02 was not completed, so no claim is made about whether its
    seed circuit was biased.
-   The "note beneath" the Module 05 message was not available in the
    materials used.

## Recommended Next Experiment

Run a CHSH experiment with randomly selected measurement settings on
both sides, then audit the machine logs using timestamps and
tamper-evident hashes. Complete Module 02 separately to measure the seed
circuit's bias and estimate how many shots would be needed to
distinguish it from a fair coin.

## References

-   Nielsen and Chuang, *Quantum Computation and Quantum Information*.
-   Clauser, Horne, Shimony, and Holt (1969), work on the CHSH
    inequality.
-   Qiskit documentation: https://qiskit.org/
-   Wootters and Zurek (1982), work on the no-cloning theorem.

## AI Assistance

AI tools were used to help draft and develop parts of the notebook and
report. The notebook was then run in Google Colab and the outputs were
reviewed by the author. Module 02 and the original preloaded circuits
were not completed or used.
