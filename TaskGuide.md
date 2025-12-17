## Lab Task

You have just joined a fintech startup called **TestLab Payments** as a **Junior DevSecOps Engineer**.

The company is scaling rapidly, and development teams push code directly to GitHub to meet tight deadlines. Unfortunately, security was never part of the development lifecycle:

- There is no formal security review
- No automated quality checks
- No security gates before deployment

Recently, management faced several serious incidents:

- A production outage caused by unvalidated and insecure code
- A sensitive API key leaked through a public repository
- A critical vulnerability discovered in a third-party dependency already running in production

As a response, the company decided to introduce **DevSecOps practices**.

Your mission is to design and enforce a secure CI/CD pipeline that:
- Detects security issues early
- Blocks unsafe code from being deployed
- Forces developers to fix issues before release

**Lab 5** represents the starting point of this transformation.


## Lab Task Overview

This repository intentionally contains insecure code and configuration.  
Your goal is to **analyze, understand, and explain** the problems detected by SonarCloud.

You are NOT expected to refactor the entire project.  
Each issue can be fixed by replacing or removing a small number of lines.


## Task Part 1 — `config.js` Analysis Questions

Review `src/config.js` and answer the following questions:

1. Which configuration values contain hardcoded secrets, and why is this dangerous in a real production environment?
2. Which configuration options enable insecure behavior by default, and what risk does this introduce?
3. How could environment variables improve secret management in this file?
4. Which debug-related settings should never be enabled in production, and why?
5. How would a misconfigured default value in this file impact the CI/CD pipeline and deployment security?

---

## Task Part 2 — `server.js` Analysis Questions

Review `src/server.js` and answer the following questions:

1. Where does the application allow authentication or authorization to be bypassed, and what is the security impact?
2. Which endpoints expose sensitive information or internal configuration, and why is this considered a security risk?
3. How does the application handle external requests, and what potential risk does this create?
4. Where is sensitive information logged, and why should this be avoided?
5. How do these issues affect the Quality Gate decision in the CI/CD pipeline?


## Task Part 3 — `package.json` Analysis Questions

Review `package.json` and answer the following questions:

1. Which dependencies are outdated or vulnerable, and how does this represent a supply chain risk?
2. Why is using deprecated or unmaintained libraries dangerous in production systems?
3. How can vulnerable dependencies affect applications even if the application code itself is secure?
4. How do dependency vulnerabilities impact CI/CD pipelines and automated security checks?
5. What best practices should be applied to dependency management in DevSecOps workflows?


## Expected Outcome

By completing this lab, you should be able to:

- Explain why the CI/CD pipeline fails
- Identify security issues across configuration, application code, and dependencies
- Understand how SonarCloud enforces security and quality
- Demonstrate how Quality Gates prevent unsafe deployments
- Describe how DevSecOps practices reduce real-world risk

This lab prepares you for fixing the issues in the next phase, where you will remediate vulnerabilities and restore a secure deployment pipeline.
