# commit-hooks

Some usefull or funny commit hooks :)

## Use husky to run commit hooks

### Init husky in your project:
- `pnpm init`
- `pnpm add husky @commitlint/cli @commitlint/config-conventional --save-dev`
- `pnpm exec husky init`

### Copy hooks to your project:
- copy `.husky/commit-msg` to `.husky/commit-msg`
- copy `.husky/prepare-commit-msg` to `.husky/prepare-commit-msg`
- copy `.hooks/add-emoji-to-commit-message.js` to `.hooks/add-emoji-to-commit-message.js`
- copy `.hooks/emojis.js` to `.hooks/emojis.js`
- copy `commitlint.config.js` to `commitlint.config.js`
