Ksx Platform

.Ksx is a universal platform for hosting and running custom programming languages entirely in the browser. It automates contributions and runtime generation so anyone can add their language with minimal effort.

With .Ksx, you can:
	•	Submit your own custom coding language.
	•	Include commands and sample code.
	•	Automatically generate a browser-compatible runtime for your language.
	•	See your language run instantly without backend setup.

⸻

How It Works

The .Ksx repository is powered by three automated workflows:

1. Validate PR Workflow

File: .github/workflows/validate-pr.yml
Purpose: Ensures all pull requests meet contribution standards before acceptance.

Checks include:
	•	custom-lango.txt exists and contains metadata (Name, Description, Files)
	•	language.txt exists and defines commands
	•	At least one .language sample code file exists
	•	Minimum of 200 lines for language.txt and .language code

This ensures each submitted language is complete and functional.

⸻

2. Auto-Merge Workflow

File: .github/workflows/auto-merge.yml
Purpose: Automatically merges pull requests that pass validation, keeping contributions seamless.

How it works:
	•	Triggered automatically when the validation workflow succeeds.
	•	Merges PRs using squash merge to maintain a clean commit history.

⸻

3. Generate Runtime Workflow

File: .github/workflows/generate-runtime.yml
Purpose: Generates a runtime JavaScript file for each contributed language and optionally an HTML interface.

What it does:
	•	Scans hsx/Flows/projects/* for new languages.
	•	Generates runtime.js for each language from language.txt commands.
	•	Optionally generates an HTML page (example.html) to run the language in a browser.
	•	Ensures every language is immediately usable in-browser.
