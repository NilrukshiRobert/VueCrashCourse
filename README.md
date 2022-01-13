

Components in Vue can have its own state which determines how specific a components behaves and
what data should be displayed.
Some states may be local to a components and some are global components that needs to be shared
with multiple components.
Vuex is a state manager for global state in larger applications
Vue 3 has something new called composition API.
https://v3.vuejs.org/
Key words in Vue language:
V-bind:src - instead of using v-bind:src to attach variable values into source ':src' can be used in short.
Vue js installation
1. In terminal type 'sudo npm install-g @vue/cli'.
2. To check if the version is installed correctly, check with 'vue --version'.
3. To view the GUI of Vue projects type in 'vue ui'.
Create a Vue project
After navigating to the project in which the project is expected to be created in
Type in the command 'vue create %project-name%' - this will ask few questions.
Preset to pick: Manually select features.
i. Choose Vue version
ii. Babel
iii. Router : can be optionally selected from here to make things easy.
a.
b. Choose version 3 or >
c. Select dedicated config file
d. And no presets.
1.
2. Navigate into the project created.
3. Open code in VS Code by typing in 'code .'
Run Dev Server from VSCode
1. Open the integrated terminal.
2. Type in 'npm run server'.
Build for production deployment.
run 'npm run build' -> this will create a 'dist' folder that is used for deployment.
Run 'sudo npm i -g serve'
Then 'server -s dist' to serve
Installing json server -> 'npm i json-server'
Configure the server in package.json
- Under scripts tag create 'backend' with value 'json-server --watch db.json --port 5000'.
- Run 'npm run backend' in the terminal from root folder to run the backend server.
Installing Router
- npm i vue-router@next
