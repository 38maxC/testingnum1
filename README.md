# Tidal Fleet

A responsive two-player Battleship website with private invite links, shuffled fleets, sonar, and triple salvo abilities. Node.js 22 or newer; no external packages or credentials needed.

## Run

```sh
npm start
```

The server listens on `0.0.0.0:3000`. Set `PORT` to change it. Open the website, create a battle, copy the invite link, and have your friend open it on another phone or browser. Shuffle and lock both fleets to begin. Shots and abilities each consume a turn. Sonar counts remaining ship cells in a 3×3 area; salvo strikes up to three adjacent horizontal cells. Sink all four ships to win.

## Verify

```sh
npm test
```

## Share with players on the Internet

Deploy this folder to a Node-compatible host using `npm start`, and use the host's public HTTPS URL. Invite links automatically use that website's address. A local server address is only reachable on your own machine or network; this repository does not provision a public domain.

Rooms live in server memory and expire after 24 hours of inactivity. Restarting the server clears rooms. Run a single server instance; multi-instance deployments need shared storage. Captain sessions are kept in each browser's local storage. Anyone with the invite can claim the second slot; invites are for two trusted players. No accounts or chat are included. Google Fonts is optional; system fonts work offline.

## Deploy on Render

Push this project to your GitHub repository. In Render, choose **New → Blueprint**, connect `38maxC/testingnum1`, and deploy using `render.yaml`. The blueprint runs the tests and starts one Node web service on the host's assigned port. Once deployment completes, open the public HTTPS URL shown by Render, create a room, and share its invite link.

The blueprint selects Render's free plan. Free services may sleep when idle; a wake-up can restart the process and erase existing rooms. Finish a match while both players stay connected. Check the provider's current plan terms before deploying. Do not scale beyond one instance while rooms use in-memory storage.
