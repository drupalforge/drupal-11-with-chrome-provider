# OOB Demo Onboarding Plan

## Goal
Improve first-run experience so a user immediately understands how to access and test the Chrome Prompt API demo.

## Outcomes
- First anonymous page clearly directs user to sign in.
- First authenticated page is a concise tutorial with steps and screenshots.
- Tutorial source-of-truth content lives in `.agents/reference/` with supporting assets.

## Scope
- Drupal site routing and login behavior.
- Tutorial page copy and image assets.
- Project-level agent docs and planning artifacts.

## Implementation Steps
1. Verify current entry flow.
- Confirm current front page and anonymous user experience.
- Confirm current post-login destination behavior.

2. Set anonymous entry page to login.
- Configure the site front page to `/user/login`.
- Ensure login form includes clear demo credentials guidance for local/demo use.

3. Set first authenticated destination to tutorial.
- Use existing redirect capability (`redirect_after_login`) to send users to the tutorial page.
- Keep admin users on tutorial unless an explicit destination parameter is provided.

4. Publish a tutorial page from `.agents/reference/Google Prompt API Copy.md`.
- Use the updated markdown as page source.
- Upload images from `.agents/reference/GooglePromptAPI Assets/`.
- Keep content short, task-oriented, and ordered by likely first actions.

5. Validate end-to-end onboarding.
- Test as anonymous user: visit site, land on login, sign in, arrive at tutorial.
- Test each tutorial action path (content edit, summarize, translate, alt text, local AI actions).
- Verify no broken images or dead links.

6. Document and handoff.
- Keep plan in `.agents/plan/current/`.
- Keep tutorial copy and assets in `.agents/reference/` for future updates.

## Acceptance Criteria
- Anonymous users land on `/user/login`.
- After successful login, users land on tutorial page.
- Tutorial includes one-time setup notes and feature walkthrough with screenshots.
- Documentation locations in `.agents/` are clear and discoverable.

## Risks And Mitigations
- Upstream AI module instability on `1.3.x-dev` can break setup.
- Mitigation: wait for upstream fix or pin to known-good version before rebuilding environments.

## Suggested Execution Order
1. Apply Drupal routing/redirect config.
2. Update/publish tutorial content.
3. Validate journey in browser.
4. Export config if this repo is intended to persist Drupal config changes.
