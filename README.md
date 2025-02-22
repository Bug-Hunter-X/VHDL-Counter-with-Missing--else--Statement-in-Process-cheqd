# VHDL Counter Bug

This repository demonstrates a common error in VHDL code: a missing `else` statement in a conditional assignment within a process. The `buggy_counter.vhdl` file contains the buggy code, while `fixed_counter.vhdl` provides the corrected version.

## The Bug

The buggy counter has a process that increments a counter on the rising edge of a clock signal.  However, the condition for resetting the counter to 0 is missing an `else` case, creating a problem.  Without an `else`, only the condition `internal_count = 15` is handled and the `internal_count` value will not be updated if the condition is not true.  This leads to unexpected behavior.

## The Solution

The `fixed_counter.vhdl` file corrects this error by including an `else` statement in the conditional assignment. The `else` statement handles the case when `internal_count` is not equal to 15, preventing the infinite loop and allowing the counter to increment correctly.