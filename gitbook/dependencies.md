# dependencies

{% stepper %}
{% step %}
### Install NPM dev dependencies

{% code title="Install (npm)" %}
```bash
npm install --save-dev @commitlint/{config-conventional,cli} husky
npx husky install
```
{% endcode %}
{% endstep %}

{% step %}
### Create commitlint config

{% code title="commitlintrc.json" %}
```json
{
  "extends": ["@commitlint/config-conventional"]
}
```
{% endcode %}
{% endstep %}

{% step %}
### Enable the Husky hook

{% code title="Add commit-msg hook" %}
```bash
npx husky add .husky/commit-msg "npx --no -- commitlint --edit $1"
git add .husky/commit-msg
```
{% endcode %}
{% endstep %}
{% endstepper %}
