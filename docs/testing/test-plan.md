# Initial QA Test Plan

**Project:** AI-Powered Polyglot Translator (Team 25)
**Author:** Muhammed Cavit DEMİRTAŞ (QA)
**Related Issue:** #7

## 1. Purpose

This document defines the initial testing approach for the AI-Powered Polyglot Translator. It will be refined in later sprints as requirements and implementation mature.

## 2. Scope

**In scope:** user authentication (FR1, FR2), speech-to-text, AI conversation via Gemini API, text-to-speech, grammar feedback (FR10, FR12), conversation history, admin topic management (FR18).

**Out of scope:** phoneme-level pronunciation evaluation (FR9) and audio-based fluency measurement (FR11), excluded because of the zero-budget constraint.

## 3. Test Levels

| Level | Purpose | Tool (proposed) |
|-------|---------|-----------------|
| Unit | Test individual functions in isolation | Jest |
| Integration | Test API, database and Gemini integration | Jest + Supertest |
| End-to-End | Test full user journeys in the browser | Playwright |
| Manual | Test microphone and speech features | Checklist |

Gemini API calls are mocked in automated tests. Target: at least 50% unit-test coverage, tracked in CI.

## 4. Initial Test Scenarios

| ID | Scenario | Expected Result |
|----|----------|-----------------|
| TC01 | Register with valid details | Account is created |
| TC02 | Log in with a wrong password | Login is rejected |
| TC03 | Log in with valid credentials | User is logged in |
| TC04 | Speak with microphone permission granted | Speech is converted to text |
| TC05 | Send a message to the Gemini API | A meaningful response is returned |
| TC06 | Play an AI response | The response is spoken aloud |
| TC07 | Complete a session with grammar mistakes | Errors and corrections are shown in the summary |
| TC08 | Open conversation history | Previous conversations are displayed |

Detailed steps will be added to `docs/testing/test-scenarios.md`.

## 5. Defect Management

Defects are reported as GitHub Issues with the `bug` label. Each report includes steps to reproduce, expected result, actual result and severity (Critical, High, Medium, Low). QA verifies each fix before the issue is closed.
