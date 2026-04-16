# Repository Guidelines

## Scope
- Applies to this repository root: `/Users/jamesabrahams/code/ai/PromptAPI`.
- Prefer DDEV commands for Drupal operations.
- Do not run authentication-required commands on behalf of the user (for example, `git push`); provide the exact command for the user to run.
- Keep this file as the lightweight entry point; put detailed agent docs under `.agents/`.

## Project Structure
- Drupal docroot: `web/`.
- Config sync: `config/`.
- Private files: `private/`.
- Composer dependencies: `vendor/`.
- DDEV config and commands: `.ddev/`.
- Agent workspace: `.agents/`.
- Working notes: `.agents/Analysis/`.
- Implementation planning: `.agents/plan/` (`.agents/plan/current/`, `.agents/plan/archive/`).
- Repository-local skills: `.agents/skills/<skill-name>/SKILL.md`.
- Optional Claude compatibility path: `.claude/skills/<skill-name>/SKILL.md`.

## Development Commands
- Start environment: `ddev start`
- Check Drupal status: `ddev drush status`
- Rebuild cache: `ddev drush cr`
- Install dependencies: `ddev composer install`
- Validate composer config: `composer validate --no-check-lock`

## Testing And Linting
- If custom modules are added, use:
- `ddev exec vendor/bin/phpunit -c web/core/phpunit.xml.dist`
- `ddev exec vendor/bin/phpcs --standard=Drupal,DrupalPractice web/modules/custom`
- For this repository, detect available lint/test commands before running broad suites.

## Git Workflow
- Keep commits focused and small.
- Use plain git commands when committing:
- `git add <files> && git commit -m "<message>"`
- If push/auth is required, ask the user to run the command in their terminal.

## Documentation Conventions
- Store analysis notes in `.agents/Analysis/`.
- Keep active plans in `.agents/plan/current/`.
- Move completed plans to `.agents/plan/archive/`.
