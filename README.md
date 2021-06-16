#INSTALAR NODEJS
curl -fsSL https://deb.nodesource.com/setup_16.x | sudo -E bash -
sudo apt-get install -y nodejs

##MODIFY

#INSTALAR YARN
curl -sL https://dl.yarnpkg.com/debian/pubkey.gpg | gpg --dearmor | sudo tee /usr/share/keyrings/yarnkey.gpg >/dev/null
echo "deb [signed-by=/usr/share/keyrings/yarnkey.gpg] https://dl.yarnpkg.com/debian stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update && sudo apt-get install yarn

#CONFIGURAR PROJETO
yarn init -y
yarn add express
yarn add typescript -D
yarn tsc --init
yarn add @types/express -D
yarn add ts-node-dev -D
yarn add eslint -D
yarn eslint --init
##RESPONDER PRIMEIRO E NÃO REPETIR IMPORT ESLINT
yarn add -D @typescript-eslint/eslint-plugin@latest eslint-config-airbnb-base@latest eslint-plugin-import@^2.22.1 @typescript-eslint/parser@latest
yarn add -D eslint-import-resolver-typescript
