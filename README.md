The following bash script can be used to help with setting up the project:
```
#!/bin/bash

GREEN=$(tput setaf 2)
NORMAL=$(tput sgr0)

npm init -f

npm install --save-dev hardhat

npm install --save-dev @nomicfoundation/hardhat-toolbox

echo "require(\"@nomicfoundation/hardhat-toolbox\");

/** @type import('hardhat/config').HardhatUserConfig */
module.exports = {
  solidity: \"0.8.17\",
};" > hardhat.config.js

echo "setup.sh
/node_modules" > .gitignore

echo "The following bash script can be used to help with setting up the project:" > README.md

echo "\`\`\`" >> README.md

cat setup.sh >> README.md

echo "\`\`\`" >> README.md

git init && git add . && git commit -m "Initial commit"

printf "\n${GREEN}≡≡≡ Setup complete. The following files are tracked by git: ≡≡≡${NORMAL}\n\n"

git ls-tree --full-tree --name-only -r HEAD

printf "\n${GREEN}≡≡≡ An initial commit has been made for you: ≡≡≡${NORMAL}\n\n"

git log | cat```
