# Explication de fetch

## Définition

Fetch est une fonction javascript permettant de faire une requête HTTP dans un code Javascript et de recevoir en retour une réponse HTTP avec éventuellement des données qu'on pourra convertir sous différents formats.

## Explication simplifié

Bon concrétement, en français, ça donne quoi ? Qu'est-ce que ça veut dire tout ça ?

Déjà qu'est-ce qu'une requête/réponse HTTP ?

### Requête/Réponse HTTP

Lorsque tu surfes sur le web via ton navigateur, tu l'auras remarqué, il y a en haut ce qu'on appelle la barre url<br>

Le principe est simple lorsque tu mets une url, un lien dans cette barre, par exemple youtube.com, tu es entrain de dire à ton navigateur que tu voudrais aller sur YouTube<br>

Néanmoins, tu te doutes bien que ce soit pour youtube ou un autre site comme facebook, gmail, instagram, etc... Ton navigateur n'a pas tout les sites stockés au chaud, pret à l'emploi.<br>

Alors comment il fait ? Si on reprend l'exemple de Youtube, il va faire une requête HTTP à YouTube, une requête à leur serveur.<br>

Il n'y a pas de piège sur le sens du mot requête, tout simplement ton navigateur va dire à Youtube<br>

Ton navigateur : "Hello ! J'aimerais bien avoir votre site Internet"
Serveur Youtube : "Pas de soucis, je vous le donne (N'oublie pas de prendre abonnement premium, au passage, on aime l'argent)"<br>

De même qu'il n'y a pas de piège de le sens du mot réponse dans une réponse HTTP, On demande à Youtube, répond en revoyant le site Internet.<br>

HTTP c'est juste un protocole, une manière de communiquer pour que les 2 puissent se comprendre.
On se met d'accord afin que le serveur comprenne la requête et le navigateur comprenne la réponse.<br>

### L'utilité de fetch

La fonction fetch est une manière de refaire tout ce mécanique de requête-réponse non pas en utilisant la barre url du navigateur mais directement dans un code Javascript ce qui donne beaucoup plus de liberté et de possibilités.<br>

## Les avantages de `fetch`

Qu'elle est l'intêret de faire cela ?<br>

Il y en a beaucoup. Par exemple, clique sur les différents liens de ton projet.
La navigateur recharge à chaque fois, n'est-ce pas ?<br>

Et maintenantc fais la même chose sur le site de YouTube.
Tu vois la différence ? Le navigateur ne recharge pas mais on change bien de page et le contenu change à chaque fois.<br>

`fetch` permet de récupérer des données stockées sur le net sans avoir à recharger la page, cela permet notamment de donner une expérience utilisateur plus agréable, plus fluide.<br>

Cependant `fetch` peut aussi être utilisé à l'extérieur du navigateur, notamment dans ton projet node JS.<br>

## Exemple concret

Admettons, qu'on a une chaîne Youtube avec une playlist où chaque vidéo, son title et son contenu correspondent à une carte en particulier.<br>

On voudrait que sur la page du détails de la carte, on est la vidéo YouTube associé disponible juste en dessous. <br>

Voici un exemple de code qui permet de récupérer la vidéo depuis la playlist :

```javascript
async function retrieveCardVideo(cardName) {
  const playlistId = process.env.PLAYLIST_ID;
  const apiKey = process.env.API_KEY;
  const accessToken = process.env.ACCESS_TOKEN;

  // On récupère la playlist Youtube avec la liste de vidéo au format JSON
  const playlist = await fetch(
    `https://youtube.googleapis.com/youtube/v3/playlistItems?part=snippet&playlistId=${playlistId}&key=${apiKey}`,
    {
      headers: {
        Accept: "application/json",
        Authorization: `Bearer ${accessToken}`
      },
    }
  ).then((res) => res.json());


  // On récupère les données de la vidéo concernant la carte
  const cardVideo = playlist.items.find(
    (video) => video.snippet.title === cardName
  ).snippet;
  
  // On renvoie l'id de la vidéo YouTube et le title de la vidéo
  return {
    videoUrl: `https://www.youtube.com?watch=${cardVideo.resourceId.videoId}`,
    title: cardVideo.title
  }
}

```

Reste plus qu'à appeler cette fonction dans le controller qui permet d'afficher les données d'une carte.<br>

On rajoute une `iframe` dans la view, on y met le lien youtube.<br>

Et voilà, le travail ! Normalement le vidéo s'affiche en fin de page.

Je te laisse essayé de faire marcher tout cela sur ton projet 😉️

## Ressources

[API Youtube](https://developers.google.com/youtube/v3/)
[Documentation sur Fetch](https://developer.mozilla.org/fr/docs/Web/API/Fetch_API)
[Node-Fetch](https://github.com/node-fetch/node-fetch)
