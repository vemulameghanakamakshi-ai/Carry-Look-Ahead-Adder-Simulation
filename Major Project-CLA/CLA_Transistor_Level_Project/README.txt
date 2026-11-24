# 4-bit Carry Look-Ahead Adder at Transistor Level

## Files
- `CLA_4bit_Transistor_Level.cir` — LTspice-ready transistor-level CMOS netlist and transient testbench.
- `Expected_Truth_Table.csv` — expected result for all 256 combinations of A and B (Cin = 0).
- `Project_Report.md` — project report.
- `Verification_Notes.txt` — important simulation and checking notes.

## Run in LTspice
1. Open LTspice.
2. Select **File -> Open**, then choose `CLA_4bit_Transistor_Level.cir`.
3. Click the **Run** button.
4. In the waveform viewer, right-click the plot area and choose **Add Trace**.
5. Add `V(A0)` through `V(A3)`, `V(B0)` through `V(B3)`, `V(S1)` through `V(S3)`, `V(P0)` (which is S0), and `V(C4)` (final carry).
6. Compare the stable output levels against `Expected_Truth_Table.csv`.

## Output interpretation
- A3..A0 and B3..B0 are the two 4-bit inputs.
- S3..S1 are the upper three sum bits.
- S0 = P0 because Cin is tied to 0.
- C4 is the final carry-out.
- The 5-bit result is `C4 S3 S2 S1 S0`.

## Important
This design uses generic Level-1 MOSFET models for an educational transistor-level demonstration. They are not calibrated to a specific fabrication process, so delay and power values are illustrative and will depend on LTspice settings and model parameters. The transient testbench sweeps all 256 input pairs. 
