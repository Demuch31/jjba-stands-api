# jjba-stands-api
JoJo's Bizarre Adventure Stands API - provides stats, abilities, and images for every stand in the series

How to fetch?
Simply by using jsDelivr:
https://cdn.jsdelivr.net/gh/demuch31/jjba-stands-api@main/stands-api.json

For example:
async function loadStands() {
  const r = await fetch(
    "https://cdn.jsdelivr.net/gh/demuch31/jjba-stands-api@main/stands-api.json",
  );
  const data = await r.json();
  const stand = data[3];
  const img = document.createElement("img");
  img.src = `https://cdn.jsdelivr.net/gh/demuch31/jjba-stands-api@main/${stand.image}`;
  document.getElementById("placeholder").appendChild(img);
  console.log(stand.name); // would return Hermit Purple
}
loadStands();
