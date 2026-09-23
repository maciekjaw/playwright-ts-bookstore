## Running locally

The suite requires the `TEST_USER_PASSWORD` environment variable. There is
no hardcoded fallback anywhere in the code — passwords must never live in
git, so the tests fail loudly at startup if it's missing.

The password must meet DemoQA's rules: min 8 characters, at least one
uppercase, one lowercase, one digit, and one special character. You can use
the example password below or set your own, as long as it meets these rules.

```bash
npm install
npx playwright install --with-deps
cp .env.example .env         # copy the template, then open .env and set your own password
npm test                     # run tests
npm run test:headed          # run tests in headed mode
npm run test:ui              # Playwright's interactive UI mode
npm run report                # open the last HTML report
``'