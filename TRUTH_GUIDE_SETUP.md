# Truth Guide setup

Truth Guide is the AI companion for The Truth Movement. The public interface lives at `truth-guide.html`; the secure server endpoint lives at `api/truth-guide.js`.

## Security

Never put an OpenAI API key in `index.html`, `truth-guide.html`, client-side JavaScript, or a GitHub commit. The endpoint reads `OPENAI_API_KEY` from the deployment environment.

## Deployment requirements

The current backend uses a Vercel-style serverless function. Configure these environment variables in the deployment platform:

- `OPENAI_API_KEY` — required, secret
- `OPENAI_MODEL` — optional; defaults to `gpt-5.6`

The browser sends chat messages to `/api/truth-guide`. The server adds The Truth Movement's behavior and safety instructions and sends the request to OpenAI's Responses API with `store: false`.

## Before public launch

1. Deploy the feature branch to a preview environment.
2. Add the secret `OPENAI_API_KEY` in the deployment platform, never in GitHub.
3. Test normal recovery, faith, family-restoration, and purpose questions.
4. Test crisis and medical prompts to verify the guide redirects users toward appropriate real-world help rather than pretending to provide emergency care.
5. Test mobile layout and keyboard submission.
6. Add a visible link from the main `index.html` after the preview is approved.

## Product boundaries

Truth Guide must remain clearly identified as AI. It must not claim to be Robert Grabow, claim that generated responses were personally written by Robert, diagnose users, prescribe treatment, provide definitive legal advice, fabricate Truth Movement services, or replace real recovery/community/professional support.
