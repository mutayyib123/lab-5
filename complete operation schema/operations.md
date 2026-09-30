# Task 2: Complete Operation Schema
## Smart Museum Artifact Conservation System

| Id | Operation | Precondition | Events / Input | Post-conditions |
|----|-----------|--------------|----------------|-----------------|
| OP-01 | PerformSelfCheck | Chamber is powered on | Power-on signal; sensor and device status | Sensors and devices tested; if all essential sensors work, system enters MONITORING mode, otherwise it stays out of normal conservation mode |
| OP-02 | RegisterArtifact | System is in MONITORING mode; artifact placed inside chamber | Artifact ID and name; required temperature and humidity limits | Artifact information and limits stored; profile loaded; artifact monitoring begins |
| OP-03 | StartConservation | System is in MONITORING mode; door is closed; artifact profile is loaded | Door-closed status; profile-loaded status | System enters CONSERVATION_ACTIVE mode (if door is open, monitoring continues without conservation) |
| OP-04 | CompareEnvironmentalReadings | System is in CONSERVATION_ACTIVE mode | Actual temperature and humidity readings; artifact limits | Each reading marked as within or outside the permitted range |
| OP-05 | CorrectEnvironment | Temperature or humidity is outside the permitted range; control device available | Out-of-range reading; permitted range | Correction command issued; recovery timer started; artifact not yet declared safe |
| OP-06 | VerifyRecovery | Correction command has been issued; recovery period running | New sensor readings; recovery period | Condition confirmed in range (conservation continues), or not recovered in time (protection needed) |
| OP-07 | ActivateProtectionResponse | Condition not corrected within the allowed recovery period | Recovery-timeout signal | System enters PROTECTION_MODE; light exposure reduced; additional controls activated; alert sent to operator |
| OP-08 | SuspendForVibration | Artifact is inside the chamber | Vibration reading above threshold | Risky activities suspended; system enters VIBRATION_RESPONSE |
| OP-09 | SuspendConservation | System is in CONSERVATION_ACTIVE mode | Door-open event | Normal conservation and environmental operation stopped while chamber is open |
| OP-10 | VerifyResumeConditions | Vibration has stopped, or door has been closed again | Vibration readings and stabilization period; environmental readings; sensor status | Conditions and sensors confirmed OK, normal conservation resumes; otherwise system stays suspended |
| OP-11 | HandlePowerLoss | Power lost during conservation | Power-loss event; emergency power status | Emergency power available: system switches to it and continues. Not available: incident recorded and system enters safe shutdown state |
| OP-12 | ConfirmSafeRemoval | Chamber is in a safe condition; no protection response active | Operator's removal request | Removal permitted; artifact record updated as removed |