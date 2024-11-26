# commit-hooks

Some usefull or funny commit hooks :)

## Use husky to run commit hooks

### Init husky in your project:
- `pnpm init`
- `pnpm add husky --save-dev`
- `pnpm exec husky init`

### Create a hook:
- `.husky/prepare-commit-msg`

### Add code to the hook:
```shell
#!/bin/sh
. "$(dirname "$0")/_/husky.sh"

node ./hooks/add-emoji-to-commit-message.js "$@"
```

### Create a hook script:
- `hooks/add-emoji-to-commit-message.js`

### Add code to the hook script:
```javascript
const fs = require('fs');

// Array of emojis to choose from
const emojis = [
  '(⊙_⊙;)',
  '༼ つ ◕_◕ ༽つ',
  'ᓚᘏᗢ',
  '(╯°□°）╯︵ ┻━┻',
  '(•_•)',
  '(*/ω＼*)',
  'ಠ_ಠ',
  '(⌐■_■)',
  '(T_T)',
  `(●'◡'●)`,
  '¯_(ツ)_/¯',
  '(❁´◡`❁)',
  '╰(*°▽°*)╯',
  'o(≧▽≦)o',
  '(^///^)',
  '(┬┬﹏┬┬)',
  'ಥ_ಥ',
  '( ´･･)ﾉ(._.`)',
  '(ˉ﹃ˉ)',
  '(☞ﾟヮﾟ)☞',
  '☜(ﾟヮﾟ☜)',
  '(¬‿¬)',
  '(¬_¬ )',
];

// Choose a random emoji
const randomEmoji = emojis[Math.floor(Math.random() * emojis.length)];

const commitMsgFile = process.argv[2];

// Read the commit message
let commitMessage = fs.readFileSync(commitMsgFile, 'utf8');

// Append the text
commitMessage = `${commitMessage.trim()} ${randomEmoji}\n`;
fs.writeFileSync(commitMsgFile, commitMessage, 'utf8');
```