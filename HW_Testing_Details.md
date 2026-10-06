# HW Testing Details

## Coverage

The custom tests verify:

- `ValueError` exception bounds
- Exact boundaries for discount tiers
- Correct routing of the highest-tier discounts
- Accurate floating-point arithmetic for VIP bonuses
- Correct application of maximum discount caps

## Run Command

```bash
python HW/test_discount.py
```

## Test Count

**6 custom specification-driven tests**

---

## 🧪 Experiment Results: The "Misleading Green" Trap

During the homework, an experiment was conducted where AI was prompted to generate tests based **only on the broken `discount.py` implementation code**, instead of the specification.

### Result

The AI-generated tests passed immediately on the broken code without any fixes being applied.

The AI incorrectly assumed that the bugs were intentional features. For example, it asserted that a **$50 cart should receive a 10% discount** because of the seeded boundary bug.

### Conclusion

This demonstrates the danger of **"Misleading Green."**

> Fixing is not proving.

A test failing before the implementation is fixed provides stronger evidence than simply having confidence that the test is correct. A test that never fails against the broken implementation does not prove that it can detect the bug.

Therefore:

- Tests must be written from the **specification**, not from the implementation.
- Tests should be **independent of the implementation code**.
- A failing test before the fix is valuable evidence that the test can detect the defect.
- Passing tests alone do not prove that the implementation is correct.

The key lesson is:

**Tests must verify what the software is supposed to do, not what the current code happens to do.**
