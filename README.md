# SecureBank Mini EDR — Automated Testing Contribution

This repository documents my **Automated Testing & Quality Assurance** contribution to the collaborative cybersecurity class project **[SecureBank Mini EDR](https://github.com/calebifechidere/securebank-mini-edr-class-project)**.

## Role & Scope
While my teammates developed the core Python 3 file-monitoring and burst-detection engine (`securebank_edr/core.py` and `cli.py`), I focused on automated testing using Python's built-in `unittest` framework (`tests/test_severity.py`).

### Key Contributions
* **Edge-Case Test Implementation:** Added `test_rapid_consecutive_bursts_respect_cooldown` to `tests/test_severity.py` to test immediate follow-up bursts of 5 modified `.txt` files within the cooldown window and verify that `alerts_total` remains `1`.
* **Local Verification:** Executed the full test suite (`python3 -m unittest discover -s tests -v`), confirming **20 unit tests passing in 0.201s**.
* **Git Workflow:** Developed on branch `feature/automated-tests` and merged into `main` via **[Pull Request #5](https://github.com/calebifechidere/securebank-mini-edr-class-project/pull/5)**.

## Security Boundary Note
Per project design, SecureBank Mini EDR is an educational prototype that monitors `.txt` files strictly inside the local `training_files` directory and simulates incident response states without killing processes or isolating endpoints.


## Visual Proof

### 1. Cooldown Edge-Case Unit Test (`tests/test_severity.py`)
[Cooldown edge-case unit test in tests/test_severity.py] <img width="1106" height="621" alt="Screenshot (294)" src="https://github.com/user-attachments/assets/fdaf26c8-6ea2-49d9-ab70-200c2633a5ec" />

### 2. Local Test Suite Verification (`20 tests` passing)
[Kali Linux terminal showing 20 unit tests passing in 0.201s] <img width="896" height="504" alt="Screenshot (295)" src="https://github.com/user-attachments/assets/0f444647-b33e-4b1d-b507-0051ddf80462" />

### 3. Pull Request #5 Merged into `main`
[Pull Request #5 merged into main on GitHub] <img width="1093" height="614" alt="Screenshot (296)" src="https://github.com/user-attachments/assets/28dd73db-8e88-4aee-bffa-ff66a2fdd176" />


## Reproducing the Tests

To clone and run the integrated project and test suite on Kali Linux:

```bash
cd ~/Downloads
git clone https://github.com/calebifechidere/securebank-mini-edr-class-project.git securebank-mini-EDR
cd securebank-mini-EDR
python3 -m unittest discover -s tests -v
python3 main.py
