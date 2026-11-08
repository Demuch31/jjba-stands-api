# jjba-stands-api

JoJo's Bizarre Adventure Stands API - provides stats, abilities, and images for every stand in the JoJo's Bizarre Adventure series

## How to fetch?

Simply by using [jsDelivr](https://www.jsdelivr.com/):

https://cdn.jsdelivr.net/gh/demuch31/jjba-stands-api@0.0.2/data/index.json

## For example:

```js
async function loadStands() {
  const r = await fetch(
    "https://cdn.jsdelivr.net/gh/demuch31/jjba-stands-api@0.0.2/data/index.json",
  );
  const data = await r.json();
  const r2 = await fetch(
    `https://cdn.jsdelivr.net/gh/demuch31/jjba-stands-api@0.0.2/data/${data.parts[0].file}`,
  );
  const stands = await r2.json();
  const stand = stands[2];
  const img = document.createElement("img");
  img.src = `https://cdn.jsdelivr.net/gh/demuch31/jjba-stands-api@0.0.2/${stand.image}`;
  document.getElementById("placeholder").appendChild(img);
  console.log(stand.name); // would return Hermit Purple
}
loadStands();
```

## Data Structure

Every part is separated:

```text
data/parts/part-3.json
```

index.json looks like this:

```json
{
  "parts": [
    {
      "id": 3,
      "name": "Stardust Crusaders",
      "file": "parts/part-3.json"
    },
    {
      "id": 4,
      "name": "Diamond is Unbreakable",
      "file": "parts/part-4.json"
    }
  ]
}
```

Each Stand looks like this:

```json
{
  "id": 0,
  "name": "Star Platinum",
  "user": "Jotaro Kujo",
  "namesake": {
    "reference": "The Star",
    "type": "tarot-card"
  },
  "part": ["Stardust Crusaders", "Diamond is Unbreakable", "Stone Ocean"],
  "type": [
    "Close-range",
    "Range irrelevant",
    "Reconnaissance",
    "Natural Humanoid"
  ],
  "stats": {
    "destructive-power": "A",
    "speed": "A",
    "range": "C",
    "stamina": "A",
    "precision": "A",
    "potential": "A"
  },
  "abilities": [
    {
      "name": "Superhuman capabilities",
      "description": "All physical stats, such as strength, speed and precision are far beyond human limits"
    },
    {
      "name": "Time stop",
      "description": "Can stop time for a few seconds"
    }
  ],
  "techniques": [
    {
      "name": "Ora Ora",
      "description": "A fast, precise rush attack of powerful punches"
    },
    {
      "name": "Star Finger",
      "description": "Star Platinum extends its middle and index fingers to stab opponents"
    }
  ],
  "image": "images/0.png",
  "wiki-url": "https://jojowiki.com/Star_Platinum"
}
```
