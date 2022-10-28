<style>
.callout {
  border-inline-start: 5px solid #bbb;
  background-color: #eee;
  border-radius: 10px;
  padding: 12px 12px 12px 40px;
  /* height: auto; */
  display: block;
  position: relative;
  overflow: auto
}


.callout:before {
  background-image: url("data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIGZpbGw9IiMwMTUzODAiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+ICAgIDxwYXRoIGQ9Ik0wIDBoMjR2MjRIMHoiIGZpbGw9Im5vbmUiLz4gICAgPHBhdGggZD0iTTEyIDJDNi40OCAyIDIgNi40OCAyIDEyczQuNDggMTAgMTAgMTAgMTAtNC40OCAxMC0xMFMxNy41MiAyIDEyIDJ6bTEgMTVoLTJ2LTZoMnY2em0wLThoLTJWN2gydjJ6Ii8+PC9zdmc+");
  background-repeat: no-repeat;
  content: "";
  width: 1.2em;
  height: 1.2em;
  left: 8px;
  /* top: 50%; */
  margin-top: 0px;
  display: inline-block;
  posit7ion: absolute;
  line-height: 1;
  opacity: .8
}

.callout.success {
  border-left-color: #0f7d15;
  background-color: #eafdeb;
  color: #063409
}

html.dark-mode .callout.success {
  background-color: #031904
}

html.dark-mode .callout.success {
  color: #129419
}

.callout.success:before {
  background-image: url("data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIGZpbGw9IiMzNzZjMzkiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+ICAgIDxwYXRoIGQ9Ik0wIDBoMjR2MjRIMHoiIGZpbGw9Im5vbmUiLz4gICAgPHBhdGggZD0iTTEyIDJDNi40OCAyIDIgNi40OCAyIDEyczQuNDggMTAgMTAgMTAgMTAtNC40OCAxMC0xMFMxNy41MiAyIDEyIDJ6bS0yIDE1bC01LTUgMS40MS0xLjQxTDEwIDE0LjE3bDcuNTktNy41OUwxOSA4bC05IDl6Ii8+PC9zdmc+")
}

.callout.danger {

  border-left-color: #ab0f0e;
  background-color: #fcdbdb;
  color: #4d0706
}

html.dark-mode .callout.danger {
  background-color: #1e0302
}

html.dark-mode .callout.danger {
  color: #c31110
}

.callout.danger:before {
  background-image: url("data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIGZpbGw9IiNiOTE4MTgiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+ICAgIDxwYXRoIGQ9Ik0xNS43MyAzSDguMjdMMyA4LjI3djcuNDZMOC4yNyAyMWg3LjQ2TDIxIDE1LjczVjguMjdMMTUuNzMgM3pNMTIgMTcuM2MtLjcyIDAtMS4zLS41OC0xLjMtMS4zIDAtLjcyLjU4LTEuMyAxLjMtMS4zLjcyIDAgMS4zLjU4IDEuMyAxLjMgMCAuNzItLjU4IDEuMy0xLjMgMS4zem0xLTQuM2gtMlY3aDJ2NnoiLz4gICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPjwvc3ZnPg==")
}

.callout.info {
  border-left-color: #0288d1;
  color: #01466c;
  background-color: #d3efff
}

html.dark-mode .callout.info {
  color: #09a7fd
}

html.dark-mode .callout.info {
  background-color: #001520
}

.callout.warning {
  border-left-color: #cf4d03;
  background-color: #fee3d3;
  color: #6a2802
}

html.dark-mode .callout.warning {
  background-color: #1a0a00
}

html.dark-mode .callout.warning {
  color: #cf4d03
}

.callout.warning:before {
  background-image: url("data:image/svg+xml;base64,PHN2ZyB2aWV3Qm94PSIwIDAgMjQgMjQiIGZpbGw9IiNiNjUzMWMiIHhtbG5zPSJodHRwOi8vd3d3LnczLm9yZy8yMDAwL3N2ZyI+ICAgIDxwYXRoIGQ9Ik0wIDBoMjR2MjRIMHoiIGZpbGw9Im5vbmUiLz4gICAgPHBhdGggZD0iTTEgMjFoMjJMMTIgMiAxIDIxem0xMi0zaC0ydi0yaDJ2MnptMC00aC0ydi00aDJ2NHoiLz48L3N2Zz4=")
}

.callout a {
  color: inherit;
  text-decoration: underline
}

code {
  background-color: #eee;
  border-radius: 3px;
  font-family: monospace;
  font-weight: bold;
  padding: 0 3px;
}

ol li {
  padding: 5px 0px;
}

ul li {
  padding: 5px 0px;
}

.container,
.row .col {
  padding: 0 var(--ifm-spacing-horizontal);
  width: 100%
}

.row .col,
img {
  max-width: 100%
}
</style>

# Minecraft forge in Crafty Controller

- Select Forge from the list of servers when adding

- After it runs once, you'll get an error: `X11 Display Variable not set` or something like that

- Go to the `config` tab and change the executable path to include `--installServer` at the end..

<p class="callout info"><code>--installServer</code> is case sensitive.</p> 

- After that runs, Go through the ssh console and `chmod +x run.sh` as the `crafty` user.

- Change the full executable path in the web ui to be `./run.sh` 

- The server should run successfully.

{% note %}

**Note:** To install mods, manually download them to the <code>mods</code> folder

{% endnote %}

