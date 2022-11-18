## Boolgram

Clone del sito web di Instagram, popolato con dati ottenuti da API.
<br>
Progetto realizzato con Vue-cli.

## Funzionamento

All'hook mounted vengono fatte due chiamate API per ottenere i dati da stampare in pagina.
Queste chiamate sono ritardate di 3 secondi tramite l'uso di setTiemout().

Nel main ho creato componenti per gestire, in particolare, le singole storie, il singolo post e i singoli suggerimenti.

Questi componenti si popolano dei dati ricevuti tramite API utilizzando le props.

Infine, ho creato alcune funzioni, soprattutto nel componente dei singoli post, per gestire le situazioni richieste dalle milestone.

## Preview
![Alt text](/public/preview.png "Sito")

<br>
<br>

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
