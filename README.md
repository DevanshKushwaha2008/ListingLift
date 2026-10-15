ListingLift — Local AI Listing Studio
A polished, responsive product-listing generator for independent marketplace sellers. It uses HTML, CSS, JavaScript, and a locally running open-weight model through Ollama to generate SEO-friendly titles, product descriptions, search tags, and calls to action.
Why this fits the Side Hustle challenge
- Open innovation is the core, not a label: generation happens through Ollama's local API using a model installed on the user's own machine.
- Privacy by default: product notes are sent to the local Ollama process, not to a hosted AI provider. The app itself has no analytics, login, or remote backend.
- Model choice: the app prefers llama3.2 but will use another installed model if it isn't available. Change DEFAULT_MODEL in app.js to prefer a different model.
- Lower marginal cost: once a model is downloaded, there is no per-listing API bill. Hardware and electricity still have costs.
- Useful output: title, description, tags, and CTA can be copied independently or exported to a text file.
Requirements
- A recent browser
- Ollama installed
- A model pulled locally, such as llama3.2
Run it
1. Install Ollama from https://ollama.com/
2. Open a terminal and run:
   ollama pull llama3.2
   ollama serve
   If Ollama is already running as a background service, ollama serve may say the port is already in use; that's okay.
3. Serve the project folder over localhost. From this folder, run:
   python -m http.server 8000
4. Open http://localhost:8000 in your browser.
5. Look for Local AI connected, load the sample product, edit the details, and click Generate listing.
If the browser cannot connect, check that Ollama is running at http://localhost:11434 and that your local browser origin is allowed by Ollama. Avoid exposing Ollama's API to the public internet.
Project files
- index.html — app structure and form
- styles.css — responsive dark UI
- app.js — Ollama connection, prompt construction, generation, copy and export
Important notes
- Generated copy can contain mistakes. Verify every claim, product detail, tag, and marketplace requirement before publishing.
- The app sends product details to your local Ollama server. If you configure Ollama to use a remote host or a cloud model, your privacy and cost assumptions change.
- This is a frontend prototype. A production paid product would benefit from model download/setup guidance, a more robust local service wrapper, saved drafts, marketplace-specific character checks, and user testing.
- The interface does not upload product photos; add image understanding as a future feature if desired.
Suggested first-user test
Show it to one Etsy, eBay, or Instagram seller and ask them to bring three real products. Measure:
1. How much time they spend writing a listing before and after.
2. How many edits they make before publishing.
3. Whether the output fits their shop voice and marketplace.
4. Whether they would pay for a local-first tool, and what would make it worth paying for.
Do not claim a first user or revenue until you've actually tested it.