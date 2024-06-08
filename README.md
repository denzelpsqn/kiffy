# kiffy
Spotify Themed API

home.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400..900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <link rel="icon" type="image/x-icon" href="/image/Icon.png">

    <link rel="stylesheet" href="home.css">
</head>
<body>
    <div class="container-fluid music" data-aos="fade-right" data-aos-duration="3000">
        <div class="row justify-content-center text-center musicc">
            <div class="col">
                <h1 data-text="MUSIC">MIX TAPE</h1>
            </div>
        </div>
      </div>
      <div class="personal">
        <p>Denzel Pasuquin</p>
        <p>BSc Year 3</p>
      </div>
      <div class="player" data-aos="fade-right" data-aos-duration="3000">
        <div class="wrapper">
            <div class="details">
                <div class="track-art"></div>
                <div class="track-name">Track Name</div>
                <div class="track-artist">Track Artist</div>
                <div class="track-description">Genre</div>
            </div>
 
            <div class="slider_container">
                <div class="current-time">00:00</div>
                 <input type="range" min="1" max="100" value="0" class="seek_slider" onchange="seekTo()">
                 <div class="total-duration">00:00</div>
            </div>
 
            <div class="slider_container">
                <i class="fa fa-volume-down"></i>
                 <input type="range" min="1" max="100" value="99" class="volume_slider" onchange="setVolume()">
                 <i class="fa fa-volume-up"></i>
            </div>
 
            <div class="buttons">
                <div class="random-track" onclick="randomTrack()">
                    <i class="fas fa-random fa-2x" title="random"></i>
                </div>
                <div class="prev-track" onclick="prevTrack()">
                     <i class="fa fa-step-backward fa-2x"></i>
                 </div>
                 <div class="playpause-track" onclick="playpauseTrack()">
                     <i class="fa fa-play-circle fa-5x"></i>
                 </div>
                 <div class="next-track" onclick="nextTrack()">
                     <i class="fa fa-step-forward fa-2x"></i>
                 </div>
                 <div class="repeat-track" onclick="repeatTrack()">
                     <i class="fa fa-repeat fa-2x" title="repeat"></i>
                 </div>
            </div>
 
        </div>
    </div>
    <!-- SCRIPT -->
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script>
        AOS.init();
    </script>
    <script src="index.js" defer></script>
</body>
</html>

home.css
body {
  background-image: url("image/background2.gif");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
}

.music h1 {
  color: white;
  font-family:"Orbitron", sans-serif;
  font-size: 100px;
  color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #ff00b0,
      0 0 82px #ff00b0,
      0 0 92px #ff00b0,
      0 0 102px #ff00b0,
      0 0 151px #ff00b0;
}

@-webkit-keyframes animate {
  0% {
    width: 0;
  }
  50% {
    width: 100%;
  }
  100% {
    width: 100%;
    border-right: none;
  }
}

@keyframes animate {
  0% {
    width: 0;
  }
  50% {
    width: 100%;
  }
  100% {
    width: 100%;
    border-right: none;
  }
}

.personal {
  font-family:"Orbitron", sans-serif;
  font-size: 30px;
  left: 10%;
  top: 25%;
  position: absolute;
  color: #FFF;
  color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #ff00b0,
      0 0 82px #ff00b0,
      0 0 92px #ff00b0,
      0 0 102px #ff00b0,
      0 0 151px #ff00b0;
}

.genre {
  font-family:"Orbitron", sans-serif;
  z-index: max;
  width: 50%;
  top: 15%;
  left: 10%;
  color: #fff;
  font-size: 12px;
  position: absolute;
  color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #ff00b0,
      0 0 82px #ff00b0,
      0 0 92px #ff00b0,
      0 0 102px #ff00b0,
      0 0 151px #ff00b0;
}

.player {
  z-index: max;
  right: 10%;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  position: absolute;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
}

.wrapper {
  border: 1px solid transparent;
  padding: 20px;
  border-radius: 20px;
  background-size: cover;
  -webkit-box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
          box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
}

.details {
  font-family:"Orbitron", sans-serif;
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  -webkit-box-orient: vertical;
  -webkit-box-direction: normal;
      -ms-flex-direction: column;
          flex-direction: column;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  color: #fff;
  text-shadow: 0 0 3px #000
  
}

.track-art {
  margin: 25px;
  height: 200px;
  width: 200px;
  border: 2px solid 	#FFFAFA;
  background-size: cover;
  background-position: center;
  border-radius: 50%;
  -webkit-box-shadow: 0px 6px 5px black;
  box-shadow: 0px 6px 5px black;
  border-radius: 190px;
}

.track-artist,
.current-time,
.total-duration,
.track-name {
  color: #f0f0f0;
}

.track-name {
  font-size: 1.5rem;
}

.track-artist {
  font-size: 1rem;
}

.buttons {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-orient: horizontal;
  -webkit-box-direction: normal;
      -ms-flex-direction: row;
          flex-direction: row;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
  margin-bottom: 30px;
  color: #f0f0f0;
}

.active {
  color: #3faf13;
}

.repeat-track,
.random-track,
.playpause-track,
.prev-track,
.next-track {
  padding: 20px;
  opacity: 0.8;
  -webkit-transition: opacity .2s;
  transition: opacity .2s;
}

.repeat-track:hover,
.random-track:hover,
.playpause-track:hover,
.prev-track:hover,
.next-track:hover {
  opacity: 1.0;
}

.slider_container {
  display: -webkit-box;
  display: -ms-flexbox;
  display: flex;
  -webkit-box-pack: center;
      -ms-flex-pack: center;
          justify-content: center;
  -webkit-box-align: center;
      -ms-flex-align: center;
          align-items: center;
}

.seek_slider, .volume_slider {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  height: 5px;
  background: #ff83f9;
  -webkit-transition: .2s;
  -webkit-transition: opacity .2s;
  transition: opacity .2s;
}

.seek_slider::-webkit-slider-thumb,
.volume_slider::-webkit-slider-thumb {
  -webkit-appearance: none;
  -moz-appearance: none;
  appearance: none;
  width: 15px;
  height: 15px;
  background: white;
  border: 3px solid #ff83f9;
  cursor: -webkit-grab;
  cursor: grab;
  border-radius: 100%;
}

.seek_slider:hover,
.volume_slider:hover {
  opacity: 1.0;
}

.seek_slider {
  width: 60%;
}

.volume_slider {
  width: 30%;
}

.current-time,
.total-duration {
  padding: 10px;
}

i.fa-volume-down,
i.fa-volume-up {
  padding: 10px;
  color: #f0f0f0;
}

i,
i.fa-play-circle,
i.fa-pause-circle,
i.fa-step-forward,
i.fa-step-backward,
p {
  cursor: pointer;
}

.randomActive {
  color: #3faf13;
}

.rotate {
  -webkit-animation: rotation 8s infinite linear;
          animation: rotation 8s infinite linear;
}

.footer {
  padding-top: 5px;
  background-color: #171717;
}

.box p, h1 {
  letter-spacing: 1px;
  color: white;
}

.pop {
  -webkit-box-flex: inherit;
      -ms-flex: inherit;
          flex: inherit;
}

.fa-facebook,
.fa-twitter,
.fa-instagram {
  padding: 10px;
  width: 30px;
  height: 30px;
  text-align: center;
  border-radius: 10px;
  background: #27132C;
  -webkit-text-size-adjust: 30px;
     -moz-text-size-adjust: 30px;
      -ms-text-size-adjust: 30px;
          text-size-adjust: 30px;
  color: #f97b7b;
  text-decoration: none;
}

.fa-twitter {
  color: #61fbfb;
}

.fa-facebook {
  background: #2144e3;
  color: white;
}

.fa:hover {
  opacity: 0.7;
}

@-webkit-keyframes rotation {
  from {
    -webkit-transform: rotate(0deg);
            transform: rotate(0deg);
  }
  to {
    -webkit-transform: rotate(359deg);
            transform: rotate(359deg);
  }
}

@keyframes rotation {
  from {
    -webkit-transform: rotate(0deg);
            transform: rotate(0deg);
  }
  to {
    -webkit-transform: rotate(359deg);
            transform: rotate(359deg);
  }
}
/*# sourceMappingURL=home.css.map */

home.css.map
{
    "version": 3,
    "mappings": "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",
    "sources": [
        "home.scss"
    ],
    "names": [],
    "file": "home.css"
}

home.scss
body{
    background-image: url('image/background2.webp');
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
}
  .music h1{
    color: white;
    font-family: 'Source Code Pro', monospace;
    font-size: 100px;
  }
  @keyframes animate {
    0%{
      width: 0;
    }
    50%{
      width: 100%;
    }
    100%{
      width: 100%;
      border-right: none;
    }
  
  }
  .personal{
    font-family: 'Source Code Pro', monospace;
    font-size: 30px;
    left: 10%;
    top: 25%;
    position: absolute;
    color: #FFF;
  }
    .genre {
    font-family: 'Source Code Pro', monospace;
      z-index: max;
      width: 50%;
      top: 15%;
      left: 10%;
      color: #fff;
      font-size: 12px;
      position: absolute;
    }
    .player{
      z-index: max;
      right: 10%;
      display: flex;
      position: absolute;
      align-items: center;
      flex-direction: column;
      justify-content: center;
  }
    .wrapper{
      border: 1px solid transparent;
      padding: 20px;
      border-radius: 20px;
      background-size: cover;
      box-shadow: rgba(0, 0, 0, 0.3) 0px 19px 38px, rgba(0, 0, 0, 0.22) 0px 15px 12px;
    }
    
    .details {
    font-family: 'Source Code Pro', monospace;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    color: #fff;
    }
    
    .track-art {
    margin: 25px;
    height: 200px;
    width: 200px;
    border:2px solid 	#FFFAFA;
    background-size: cover;
    background-position: center;
    border-radius: 50%;
    -moz-box-shadow: 0px 6px 5px black;
    -webkit-box-shadow: 0px 6px 5px black;
    box-shadow: 0px 6px 5px black;
    -moz-border-radius:190px;
    -webkit-border-radius:190px;
    border-radius:190px;
    }
    .track-artist,
    .current-time,
    .total-duration,
    .track-name{
      color: rgb(240, 240, 240);
    }
    
    .track-name {
    font-size: 1.5rem;
    }
    
    .track-artist {
    font-size: 1rem;
    }
    
    .buttons {
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-bottom: 30px;
    color: rgb(240, 240, 240);
    }
    .active{
        color: #3faf13;
    }
    
    .repeat-track,
    .random-track,
    .playpause-track,
    .prev-track,
    .next-track {
    padding: 20px;
    opacity: 0.8;
    transition: opacity .2s;
    }
    
    .repeat-track:hover,
    .random-track:hover,
    .playpause-track:hover,
    .prev-track:hover,
    .next-track:hover {
    opacity: 1.0;
    }
    
    .slider_container {
    display: flex;
    justify-content: center;
    align-items: center;
    }
    
    .seek_slider, .volume_slider {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    height: 5px;
    background: #83A9FF;
    -webkit-transition: .2s;
    transition: opacity .2s;
    }
    
    .seek_slider::-webkit-slider-thumb,
    .volume_slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    width: 15px;
    height: 15px;
    background: white;
    border: 3px solid #3774FF;
    cursor: grab;
    border-radius: 100%;
    }
    
    .seek_slider:hover,
    .volume_slider:hover {
    opacity: 1.0;
    }
    
    .seek_slider {
    width: 60%;
    }
    
    .volume_slider {
    width: 30%;
    }
    
    .current-time,
    .total-duration {
    padding: 10px;
    }
    
    i.fa-volume-down,
    i.fa-volume-up {
    padding: 10px;
    color: rgb(240, 240, 240);
    }
    
    i,
    i.fa-play-circle,
    i.fa-pause-circle,
    i.fa-step-forward,
    i.fa-step-backward,
    p {
    cursor: pointer;
    }
    .randomActive{
        color: #3faf13;
    }
    .rotate {
        animation: rotation 8s infinite linear;
    }
    .footer {
      padding-top: 5px;
      background-color: rgb(23, 23, 23);
    }
    .box p, h1 {
      letter-spacing: 1px;
      color: white;
    }
    .pop{
      flex: inherit;
    }
    .fa-facebook,
    .fa-twitter,
    .fa-instagram{
      padding: 10px;
      width: 30px;
      height: 30px;
      text-align: center;
      border-radius: 10px;
      background: #27132C;
      text-size-adjust: 30px;
      color: rgb(249, 123, 123);
      text-decoration: none;
    }
  .fa-twitter{
      color: rgb(97, 251, 251);
  }
  .fa-facebook{
      background: #2144e3;
      color: rgb(255, 255, 255);
  }
  .fa:hover{
      opacity: 0.7;
  }
    @keyframes rotation {
        from {
          transform: rotate(0deg);
        }
        to {
          transform: rotate(359deg);
        }
    }

index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DENZEL</title>
    <!-- CSS only -->
    <link href="https://unpkg.com/aos@2.3.1/dist/aos.css" rel="stylesheet">
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-rbsA2VBKQhggwzxH7pPCaAqO46MgnOM80zW1RWuH61DGLwZJEdK2Kadq2F9CUG65" crossorigin="anonymous">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400..900&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.13.0/css/all.min.css">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <link rel="icon" type="image/x-icon" href="/image/Icon.png">
    <link rel="stylesheet" href="index.css">

</head>
<body>
    <!-- Introduction -->
    <div class="container-fluid">
        <div class="row header" data-aos="fade-right" data-aos-duration="3000">
            <div class="col-3 justify-content-md-center">
                <h1>Kiffy</h1><hr class="line">
                <h2>Ekup</h2>
            </div>
            <div class="col-4"> 
                <a href="home.html">MIX TAPE</a>
            </div>
        </div>
    </div>
    <!-- SCRIPT -->
    <script src="https://unpkg.com/aos@2.3.1/dist/aos.js"></script>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
    <script>
        AOS.init();
    </script>
    <script src="index.js" defer></script>
</body>
</html>

index.css
* {
  -webkit-box-sizing: border-box;
          box-sizing: border-box;
  margin: 0;
}

body {
  background-image: url("image/background.gif");
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
}

.line {
  border: 1px solid white;
  border-radius: 5px;
}

.header h2 {
  font-family:"Orbitron", sans-serif;
  font-size: 50px;
  color: white;
  color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #ff00b0,
      0 0 82px #ff00b0,
      0 0 92px #ff00b0,
      0 0 102px #ff00b0,
      0 0 151px #ff00b0;
}

.header h1 {
  color: white;
  font-family:"Orbitron", sans-serif;
  font-size: 100px;
  color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #ff00b0,
      0 0 82px #ff00b0,
      0 0 92px #ff00b0,
      0 0 102px #ff00b0,
      0 0 151px #ff00b0;
}

.header a {
  position: absolute;
  top: 15%;
  right: 20%;
  font-family:"Orbitron", sans-serif;
  color: white;
  font-size: 50px;
  text-decoration: none;
  color: #fff;
  text-shadow:
      0 0 7px #fff,
      0 0 10px #fff,
      0 0 21px #fff,
      0 0 42px #ff00b0,
      0 0 82px #ff00b0,
      0 0 92px #ff00b0,
      0 0 102px #ff00b0,
      0 0 151px #ff00b0;
}
/*# sourceMappingURL=index.css.map */

index.css.map
{
    "version": 3,
    "mappings": "AAEA,AAAA,CAAC,CAAA;EACG,UAAU,EAAE,UAAU;EACtB,MAAM,EAAE,CAAC;CACZ;;AACD,AAAA,IAAI,CAAC;EACD,gBAAgB,EAAE,2BAA2B;EAC7C,iBAAiB,EAAE,SAAS;EAC5B,qBAAqB,EAAE,KAAK;EAC5B,eAAe,EAAE,KAAK;CACzB;;AACD,AAAA,KAAK,CAAC;EACJ,MAAM,EAAE,GAAG,CAAC,KAAK,CAAC,KAAkB;EACpC,aAAa,EAAE,GAAG;CACnB;;AACD,AAAA,OAAO,CAAC,EAAE,CAAA;EACR,WAAW,EAAE,4BAA4B;EACzC,SAAS,EAAE,IAAI;EACf,KAAK,EAAE,KAAK;CACb;;AACD,AAAA,OAAO,CAAC,EAAE,CAAA;EACR,KAAK,EAAE,KAAK;EACZ,WAAW,EAAE,4BAA4B;EACzC,SAAS,EAAE,KAAK;CACjB;;AACD,AAAA,OAAO,CAAC,CAAC,CAAA;EACP,QAAQ,EAAE,QAAQ;EAClB,GAAG,EAAE,GAAG;EACR,KAAK,EAAE,GAAG;EACV,WAAW,EAAE,4BAA4B;EACzC,KAAK,EAAE,KAAK;EACZ,SAAS,EAAE,IAAI;EACf,eAAe,EAAE,IAAI;CACtB",
    "sources": [
        "index.scss"
    ],
    "names": [],
    "file": "index.css"
}

#index.scss
$colorpalette1: #010508;
$colorpalette2: #cbfdff;
*{
    box-sizing: border-box;
    margin: 0;
}
body {
    background-image: url('image/background.jpg');
    background-repeat: no-repeat;
    background-attachment: fixed;
    background-size: cover;
}
.line {
  border: 1px solid rgb(255, 255, 255);
  border-radius: 5px;
}
.header h2{
  font-family: 'Source Code Pro', monospace;
  font-size: 50px;
  color: white;
}
.header h1{
  color: white;
  font-family: 'Source Code Pro', monospace;
  font-size: 100px;
}
.header a{
  position: absolute;
  top: 15%;
  right: 20%;
  font-family: 'Source Code Pro', monospace;
  color: white;
  font-size: 50px;
  text-decoration: none;
}

index.js
let track_art = document.querySelector('.track-art');
let track_name = document.querySelector('.track-name');
let track_artist = document.querySelector('.track-artist');
let track_genre = document.querySelector('.track-description');
let track_background = document.querySelector('.wrapper');

let playpause_btn = document.querySelector('.playpause-track');
let next_btn = document.querySelector('.next-track');
let prev_btn = document.querySelector('.prev-track');

let seek_slider = document.querySelector('.seek_slider');
let volume_slider = document.querySelector('.volume_slider');
let curr_time = document.querySelector('.current-time');
let total_duration = document.querySelector('.total-duration');
let randomIcon = document.querySelector('.fa-random');
let curr_track = document.createElement('audio');

let track_index = 0;
let isPlaying = false;
let isRandom = false;
let updateTimer;

const music_list = [
    
    {
        img : 'image/keshi.jpg',
        name : 'LIMBO',
        artist : 'Keshi',
        music : 'music/LIMBO.mp3',
        background : 'image/keshibg.jpg',
        genre : 'R&B',
    },

    {
        img : 'image/snooze.jpg',
        name : 'SNOOZE',
        artist : 'SZA',
        music : 'music/Snooze.mp3',
        background : 'image/snoozebg.jpg',
        genre : 'R&B',
    },

    {
        img : 'image/agorahills.jpg',
        name : 'Agora Hills',
        artist : 'Doja Cat',
        music : 'music/Agora Hills.mp3',
        background : 'image/agorahillsbg.jpg',
        genre : 'R&B',
    },
    
    {
        img : 'image/boodup.jpg',
        name : 'Boo\'d Up',
        artist : 'Ella Mai',
        music : 'music/Boo\'d Up.mp3',
        background : 'image/boodupbg.jpg',
        genre : 'R&B',
    },
    
    {
        img : 'image/jimmycooks.jpg',
        name : 'Jimmy Cooks',
        artist : 'Drake',
        music : 'music/Jimmy Cooks.mp3',
        background : 'image/jimmycooksbg.jpg',
        genre : 'Hip-Hop',
    },
     
    {
        img : 'image/notlikeus.jpg',
        name : 'Not Like Us',
        artist : 'Kendrick Lamar',
        music : 'music/Not Like Us.mp3',
        background : 'image/notlikeusbg.jpg',
        genre : 'Hip-Hop',
    },
     
    {
        img : 'image/MurderOnMyMind.jpg',
        name : 'Murder On My Mind',
        artist : 'YNW Melly',
        music : 'music/Murder on My Mind.mp3',
        background : 'image/murderonmymindbg.jpg',
        genre : 'Hip-Hop',
    },
     
    {
        img : 'image/luciddreams.jpg',
        name : 'Lucid Dreams',
        artist : 'Juice WRLD',
        music : 'music/Lucid Dreams.mp3',
        background : 'image/luciddreamsbg.jpg',
        genre : 'Hip-Hop',
    },
     
    {
        img : 'image/dont.jpg',
        name : 'Don\'t',
        artist : 'Bryson Tiller',
        music : 'music/Don\'t.mp3',
        background : 'image/dontbg.jpg',
        genre : 'R&B',
    },
     
    {
        img : 'image/mockingbird.jpg',
        name : 'Mockingbird',
        artist : 'EMINEM',
        music : 'music/Mockingbird.mp3',
        background : 'image/mockingbirdbg.jpg',
        genre : 'Hip-Hop',
    },
    
];

loadTrack(track_index);

function loadTrack(track_index){
    clearInterval(updateTimer);
    reset();

    curr_track.src = music_list[track_index].music;
    curr_track.load();

    track_art.style.backgroundImage = "url(" + music_list[track_index].img + ")";
    track_name.textContent = music_list[track_index].name;
    track_genre.textContent = music_list[track_index].genre;
    track_artist.textContent = music_list[track_index].artist;
    track_background.style.backgroundImage = "url(" + music_list[track_index].background + ")";

    updateTimer = setInterval(setUpdate, 1000);

    curr_track.addEventListener('ended', nextTrack);
}

function reset(){
    curr_time.textContent = "00:00";
    total_duration.textContent = "00:00";
    seek_slider.value = 0;
}
function randomTrack(){
    isRandom ? pauseRandom() : playRandom();
}
function playRandom(){
    isRandom = true;
    randomIcon.classList.add('randomActive');
}
function pauseRandom(){
    isRandom = false;
    randomIcon.classList.remove('randomActive');
}
function repeatTrack(){
    let current_index = track_index;
    loadTrack(current_index);
    playTrack();
}
function playpauseTrack(){
    isPlaying ? pauseTrack() : playTrack();
}
function playTrack(){
    curr_track.play();
    isPlaying = true;
    track_art.classList.add('rotate');
    playpause_btn.innerHTML = '<i class="fa fa-pause-circle fa-5x"></i>';
}
function pauseTrack(){
    curr_track.pause();
    isPlaying = false;
    track_art.classList.remove('rotate');
    playpause_btn.innerHTML = '<i class="fa fa-play-circle fa-5x"></i>';
}
function nextTrack(){
    if(track_index < music_list.length - 1 && isRandom === false){
        track_index += 1;
    }else if(track_index < music_list.length - 1 && isRandom === true){
        let random_index = Number.parseInt(Math.random() * music_list.length);
        track_index = random_index;
    }else{
        track_index = 0;
    }
    loadTrack(track_index);
    playTrack();
}
function prevTrack(){
    if(track_index > 0){
        track_index -= 1;
    }else{
        track_index = music_list.length -1;
    }
    loadTrack(track_index);
    playTrack();
}

function seekTo(){
    let seekto = curr_track.duration * (seek_slider.value / 100);
    curr_track.currentTime = seekto;
}
function setVolume(){
    curr_track.volume = volume_slider.value / 100;
}
function setUpdate(){
    let seekPosition = 0;
    if(!isNaN(curr_track.duration)){
        seekPosition = curr_track.currentTime * (100 / curr_track.duration);
        seek_slider.value = seekPosition;

        let currentMinutes = Math.floor(curr_track.currentTime / 60);
        let currentSeconds = Math.floor(curr_track.currentTime - currentMinutes * 60);
        let durationMinutes = Math.floor(curr_track.duration / 60);
        let durationSeconds = Math.floor(curr_track.duration - durationMinutes * 60);

        if(currentSeconds < 10) {currentSeconds = "0" + currentSeconds; }
        if(durationSeconds < 10) { durationSeconds = "0" + durationSeconds; }
        if(currentMinutes < 10) {currentMinutes = "0" + currentMinutes; }
        if(durationMinutes < 10) { durationMinutes = "0" + durationMinutes; }

        curr_time.textContent = currentMinutes + ":" + currentSeconds;
        total_duration.textContent = durationMinutes + ":" + durationSeconds;
    }
}
