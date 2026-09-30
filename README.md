# Task 1: Identify Operations
## Smart Museum Artifact Conservation System

| OP-Id | Operation | Purpose |
|-------|-----------|---------|
| OP-01 | PerformSelfCheck | Test all sensors and environmental-control devices at power-on; if all essential sensors work, start monitoring |
| OP-02 | RegisterArtifact | Record the artifact's identification information and required environmental limits, and load its profile |
| OP-03 | StartConservation | Begin normal conservation only when the door is closed and the artifact's profile is loaded |
| OP-04 | CompareEnvironmentalReadings | Compare actual temperature and humidity with the artifact's permitted limits |
| OP-05 | CorrectEnvironment | Send a correction command to restore temperature or humidity to the permitted range |
| OP-06 | VerifyRecovery | Confirm through sensor readings that the condition has really returned to the permitted range |
| OP-07 | ActivateProtectionResponse | Reduce light exposure, activate additional controls and alert the operator when recovery fails in time |
| OP-08 | SuspendForVibration | Temporarily suspend risky activities when significant vibration is detected |
| OP-09 | SuspendConservation | Immediately stop normal conservation operation when the chamber door is opened |
| OP-10 | VerifyResumeConditions | Check vibration stability, environmental conditions and sensor status before returning to normal operation |
| OP-11 | HandlePowerLoss | Switch to emergency power if available; otherwise record the incident and shut down safely |
| OP-12 | ConfirmSafeRemoval | Allow the operator to remove the artifact only when the chamber is safe and no protection response is active |
