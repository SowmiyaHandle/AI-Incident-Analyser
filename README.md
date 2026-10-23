# AI Incident Analyzer – Fintech Technology Operations

An AI-powered application that helps Technology Operations teams analyze application logs, identify recurring failures, classify incident severity, investigate possible root causes, and generate structured incident reports.

## Overview

During application failures, support engineers often need to investigate multiple logs to understand what went wrong. The AI Incident Analyzer simplifies this process by analyzing simulated logs and recommending evidence-based troubleshooting steps.

This project was developed as a prototype for fintech and payment technology operations.

## Features

- **Log Input:** Paste application logs or upload `.txt` and `.log` files.
- **Sample Scenarios:** Test payment API timeouts, database connection failures, single warnings, and fraud engine latency.
- **Error Pattern Detection:** Identify recurring errors and affected services.
- **Severity Classification:** Classify incidents as Critical, High, Medium, or Low with explanations.
- **Evidence vs. Hypotheses:** Separate facts observed in logs from possible root causes.
- **Troubleshooting Recommendations:** Suggest prioritized investigation steps and escalation guidance.
- **Incident Reports:** Preview, copy, and download incident reports as text; JSON export is also supported by the prototype.
- **Fallback Analysis:** Use a rule-based analysis engine when AI analysis is unavailable, if supported by the configured application.
- **Input Validation:** Handle empty or invalid log input.

## Technology Stack

- **Frontend:** React, TypeScript
- **AI Integration:** Google Gemini API
- **Server:** Node.js / TypeScript
- **Log Analysis:** AI-assisted analysis and rule-based fallback
- **Development Environment:** Google AI Studio

*Confirm the final dependencies and model name from the generated source code before submission.*

## How It Works

1. The user pastes logs or selects a sample incident.
2. The application processes the supplied logs.
3. The analysis identifies errors, repeated patterns, and affected services.
4. Incident severity is classified with a supporting explanation.
5. Confirmed evidence is separated from possible root causes.
6. Troubleshooting and escalation recommendations are generated.
7. A structured incident report can be exported.

## Sample Test Scenarios

| Scenario | Expected Severity | Key Finding |
|---|---|---|
| Payment API Timeouts | Critical | Repeated HTTP 504 errors and circuit breaker activation |
| Database Connection Failures | Critical | Connection pool exhaustion and SQLSTATE 53300 |
| Single Warning | Low | Temporary FX provider latency with successful cache fallback |
| Fraud Engine Latency | Medium | Slow ML evaluation with fallback processing |

These are simulated scenarios. Severity depends on the evidence and the actual operational impact.

## Setup Instructions

1. Export or download the source code from Google AI Studio.
2. Install Node.js if it is not already installed.
3. Open a terminal in the project directory.
4. Install dependencies:

   ```bash
   npm install
   ```

5. Configure the Gemini API key using the application's supported environment-variable or server-side secret configuration.
6. Start the application using the script defined in `package.json`, for example:

   ```bash
   npm run dev
   ```

7. Open the local URL displayed in the terminal.

**Note:** Verify the actual scripts in `package.json` and the environment-variable name in the source code. Do not commit API keys or `.env` files to GitHub.

## Testing

The prototype was tested using four simulated incident scenarios:

- Payment API timeouts
- Database connection failures
- Single warning
- Fraud engine latency

Additional checks included incident report generation, report export, evidence and hypothesis separation, and input validation.

## AI Approach

The application uses an existing Gemini model to analyze supplied logs and generate structured incident findings. It does not train a new AI model.

The intended approach distinguishes
