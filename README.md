<!DOCTYPE html>
<html lang="zh-Hant">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>致我們一年的友誼</title>

<style>
* {
  box-sizing: border-box;
  -webkit-tap-highlight-color: transparent;
}

body {
  margin: 0;
  min-height: 100vh;
  background:
    radial-gradient(circle at 20% 20%, rgba(255,255,255,.15), transparent 25%),
    radial-gradient(circle at 80% 70%, rgba(70,45,20,.12), transparent 30%),
    #6f5a3f;
  color: #3e3020;
  font-family: "Noto Serif TC", "PMingLiU", serif;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 28px 16px;
}

/* =========================
   主紙張
========================= */

.paper {
  width: min(900px, 100%);
  min-height: 650px;
  padding: 55px clamp(25px, 7vw, 85px);

  background:
    repeating-linear-gradient(
      0deg,
      rgba(100,70,30,.025) 0px,
      rgba(100,70,30,.025) 1px,
      transparent 1px,
      transparent 4px
    ),
    radial-gradient(circle at 15% 15%, rgba(120,80,30,.08), transparent 18%),
    radial-gradient(circle at 85% 80%, rgba(120,80,30,.07), transparent 20%),
    #eee0b9;

  box-shadow:
    0 18px 40px rgba(30,20,10,.35),
    inset 0 0 35px rgba(105,70,25,.18);

  border: 1px solid rgba(80,55,25,.25);
  position: relative;
  overflow: hidden;
}

.paper::before {
  content: "";
  position: absolute;
  pointer-events: none;
  inset: 14px;
  border: 1px solid rgba(100,70,30,.12);
}

.paper::after {
  content: "";
  position: absolute;
  inset: 0;
  pointer-events: none;
  background:
    radial-gradient(
      ellipse at center,
      transparent 55%,
      rgba(80,50,15,.12)
    );
}

/* =========================
   密碼頁
========================= */

.lock-screen {
  min-height: 535px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  position: relative;
  z-index: 5;
}

.small {
  font-size: 14px;
  letter-spacing: 4px;
  opacity: .65;
  margin-bottom: 15px;
}

.lock-screen h1 {
  font-size: clamp(34px, 7vw, 58px);
  font-weight: 500;
  letter-spacing: 8px;
  margin: 0 0 38px;
}

.password-box {
  width: min(380px, 90%);
}

input {
  width: 100%;
  padding: 14px 18px;
  border: none;
  border-bottom: 1px solid #766043;
  background: rgba(255,250,225,.35);
  color: #3e3020;
  outline: none;
  font: inherit;
  text-align: center;
  font-size: 17px;
  letter-spacing: 3px;
}

input::placeholder {
  color: #806f52;
  letter-spacing: 2px;
}

button {
  margin-top: 22px;
  padding: 11px 34px;
  border: 1px solid #675137;
  background: transparent;
  color: #463620;
  font: inherit;
  letter-spacing: 3px;
  cursor: pointer;
  transition: .25s;
}

button:hover {
  background: #675137;
  color: #f4e9c8;
}

#error {
  height: 22px;
  margin-top: 14px;
  color: #865348;
  font-size: 14px;
}

/* =========================
   信封場景
========================= */

.envelope-screen {
  display: none;
  min-height: 535px;
  position: relative;
  z-index: 3;
  overflow: hidden;
  touch-action: pan-y;
}

.envelope-intro {
  text-align: center;
  margin-top: 35px;
  font-size: 14px;
  letter-spacing: 3px;
  opacity: .7;
  transition: opacity .4s;
}

.envelope-area {
  position: absolute;
  left: 50%;
  top: 52%;
  width: min(620px, 88%);
  height: 390px;
  transform: translate(-50%, -50%);
  touch-action: none;
}

/* =========================
   信封
========================= */

.envelope {
  position: absolute;
  left: 50%;
  bottom: 20px;

  width: min(570px, 100%);
  height: 340px;

  transform: translateX(-50%);

  background:
    repeating-linear-gradient(
      0deg,
      rgba(80,45,20,.025) 0px,
      rgba(80,45,20,.025) 2px,
      transparent 2px,
      transparent 7px
    ),
    #d8bd8d;

  box-shadow:
    0 18px 30px rgba(50,30,10,.28),
    inset 0 0 25px rgba(90,55,20,.15);

  border: 1px solid rgba(85,55,25,.3);

  transition:
    transform .9s cubic-bezier(.22,.8,.25,1),
    opacity .8s;
}

/* 紙張皺褶 */

.envelope::before {
  content: "";
  position: absolute;
  inset: 0;
  pointer-events: none;

  background:
    linear-gradient(
      25deg,
      transparent 45%,
      rgba(80,50,20,.10) 46%,
      transparent 48%
    ),
    linear-gradient(
      155deg,
      transparent 45%,
      rgba(80,50,20,.08) 46%,
      transparent 48%
    ),
    linear-gradient(
      90deg,
      transparent 48%,
      rgba(255,255,255,.16) 50%,
      transparent 52%
    );

  opacity: .8;
}

/* 信封背面 */

.envelope-back {
  position: absolute;
  inset: 0;
  background:
    linear-gradient(
      135deg,
      transparent 49%,
      rgba(100,65,30,.18) 50%,
      transparent 51%
    ),
    linear-gradient(
      225deg,
      transparent 49%,
      rgba(100,65,30,.16) 50%,
      transparent 51%
    );
}

/* 信封下方折線 */

.envelope-bottom {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 52%;

  background:
    linear-gradient(
      145deg,
      transparent 49.5%,
      rgba(100,65,30,.22) 50%,
      transparent 50.5%
    ),
    linear-gradient(
      215deg,
      transparent 49.5%,
      rgba(100,65,30,.20) 50%,
      transparent 50.5%
    );

  pointer-events: none;
}

/* =========================
   信封上蓋
========================= */

.envelope-flap {
  position: absolute;
  top: 0;
  left: 0;

  width: 100%;
  height: 58%;

  background:
    repeating-linear-gradient(
      0deg,
      rgba(80,45,20,.025) 0px,
      rgba(80,45,20,.025) 2px,
      transparent 2px,
      transparent 7px
    ),
    #dfc99d;

  clip-path: polygon(0 0, 100% 0, 50% 100%);

  transform-origin: top center;

  z-index: 5;

  transition:
    transform 1.1s cubic-bezier(.22,.8,.25,1);
}

/* 上蓋皺褶 */

.envelope-flap::after {
  content: "";
  position: absolute;
  inset: 0;

  background:
    linear-gradient(
      145deg,
      transparent 47%,
      rgba(100,65,30,.13) 48%,
      transparent 50%
    ),
    linear-gradient(
      215deg,
      transparent 47%,
      rgba(100,65,30,.10) 48%,
      transparent 50%
    );

  opacity: .8;
}

/* =========================
   火漆
========================= */

.wax-seal {
  position: absolute;
  z-index: 10;

  left: 50%;
  top: 48%;

  width: 78px;
  height: 78px;

  transform: translate(-50%, -50%);

  border-radius: 50%;

  background:
    radial-gradient(
      circle at 35% 30%,
      #c9574b,
      #8e2927 55%,
      #641c1c 100%
    );

  box-shadow:
    0 5px 10px rgba(50,20,10,.35),
    inset 3px 3px 6px rgba(255,150,130,.25),
    inset -4px -5px 8px rgba(50,0,0,.35);

  cursor: pointer;

  transition:
    transform .55s,
    opacity .5s;
}

.wax-seal:hover {
  transform: translate(-50%, -50%) scale(1.06) rotate(-2deg);
}

.wax-seal::before {
  content: "✦";

  position: absolute;
  inset: 0;

  display: flex;
  justify-content: center;
  align-items: center;

  color: rgba(255,220,190,.7);
  font-size: 27px;
}

.wax-seal::after {
  content: "郵";
  position: absolute;

  left: 50%;
  top: 50%;

  transform: translate(-50%, -50%);

  color: rgba(255,220,190,.75);
  font-size: 19px;
  font-weight: bold;
}

.wax-seal.removed {
  transform: translate(-50%, -50%) scale(1.8) rotate(15deg);
  opacity: 0;
  pointer-events: none;
}

/* =========================
   信封提示
========================= */

.seal-hint {
  position: absolute;
  left: 50%;
  bottom: -18px;

  transform: translateX(-50%);

  width: 100%;

  text-align: center;

  font-size: 13px;
  letter-spacing: 2px;

  opacity: .65;

  transition: opacity .5s;
}

.seal-hint.hidden {
  opacity: 0;
}

/* =========================
   信紙
========================= */

.letter-paper {
  position: absolute;

  left: 50%;
  bottom: 30px;

  width: min(510px, 88%);
  min-height: 480px;

  padding: 55px clamp(22px, 5vw, 55px);

  transform:
    translateX(-50%)
    translateY(260px)
    rotate(-1deg);

  opacity: 0;

  z-index: 2;

  background:
    repeating-linear-gradient(
      0deg,
      rgba(100,70,30,.025) 0px,
      rgba(100,70,30,.025) 2px,
      transparent 2px,
      transparent 6px
    ),
    #f1e5c5;

  box-shadow:
    0 15px 30px rgba(50,30,10,.25),
    inset 0 0 30px rgba(100,70,30,.12);

  transition:
    transform 1.25s cubic-bezier(.18,.8,.25,1),
    opacity .8s;
}

/* 信紙褶皺 */

.letter-paper::before {
  content: "";
  position: absolute;
  inset: 0;

  pointer-events: none;

  background:
    linear-gradient(
      18deg,
      transparent 42%,
      rgba(90,60,25,.10) 43%,
      transparent 45%
    ),
    linear-gradient(
      165deg,
      transparent 46%,
      rgba(90,60,25,.08) 47%,
      transparent 49%
    ),
    linear-gradient(
      90deg,
      transparent 47%,
      rgba(255,255,255,.18) 49%,
      transparent 51%
    ),
    radial-gradient(
      ellipse at center,
      transparent 55%,
      rgba(80,50,15,.10)
    );
}

/* =========================
   開信動畫
========================= */

.envelope-screen.opened .envelope-flap {
  transform: rotateX(180deg);
}

.envelope-screen.opened .letter-paper {
  transform:
    translateX(-50%)
    translateY(-100px)
    rotate(-1deg);

  opacity: 1;
}

.envelope-screen.opened .envelope {
  transform: translateX(-50%) translateY(190px);
}

.envelope-screen.opened .envelope-intro {
  opacity: 0;
}

.envelope-screen.opened .seal-hint {
  opacity: 0;
}

/* =========================
   真正信件
========================= */

.letter {
  display: none;
  position: relative;
  z-index: 5;
}

.letter h2 {
  margin: 0 0 38px;

  font-size: clamp(32px, 6vw, 52px);
  font-weight: 500;

  letter-spacing: 5px;
  line-height: 1.4;

  text-align: left;

  border-bottom: 1px solid rgba(70,50,25,.3);

  padding-bottom: 20px;
}

.letter-content {
  white-space: pre-wrap;
  word-break: break-all;
  overflow-wrap: anywhere;

  font-size: 18px;
  line-height: 2.15;
  letter-spacing: 1px;

  text-align: left;

  min-height: 400px;
}

/* =========================
   返回按鈕
========================= */

.back {
  display: block;
  margin: 45px 0 0;

  font-size: 13px;
  padding: 8px 18px;
}

/* =========================
   手機版
========================= */

@media (max-width: 600px) {

  body {
    padding: 0;
  }

  .paper {
    min-height: 100vh;
    padding: 30px 20px;
  }

  .lock-screen {
    min-height: 90vh;
  }

  .lock-screen h1 {
    letter-spacing: 5px;
  }

  .envelope-screen {
    min-height: 90vh;
  }

  .envelope-area {
    width: 94%;
    height: 360px;
  }

  .envelope {
    height: 255px;
  }

  .letter-paper {
    width: 88%;
    min-height: 400px;
    padding: 35px 25px;
  }

  .wax-seal {
    width: 65px;
    height: 65px;
  }

  .letter-content {
    font-size: 16px;
    line-height: 2;
  }

  .letter h2 {
    font-size: 30px;
    letter-spacing: 3px;
  }
}
</style>
</head>


<body>

<main class="paper">

<!-- =========================
     密碼頁
========================= -->

<section class="lock-screen" id="lockScreen">

  <div class="small">
    A LETTER FOR YOU
  </div>

  <h1>
    致我們一年的友誼
  </h1>

  <div class="password-box">

    <input
      id="password"
      type="password"
      placeholder="請輸入密碼"
      autocomplete="off"
    >

    <button onclick="unlock()">
      解開信件
    </button>

    <div id="error"></div>

  </div>

</section>


<!-- =========================
     信封頁
========================= -->

<section
  class="envelope-screen"
  id="envelopeScreen"
>

  <div class="envelope-intro">
    一封只屬於你的信
  </div>


  <div
    class="envelope-area"
    id="envelopeArea"
  >

    <!-- 信紙 -->

    <div class="letter-paper">
      <div style="
        text-align:center;
        font-size:14px;
        letter-spacing:3px;
        opacity:.6;
        margin-top:150px;
      ">
        TO YOU
      </div>
    </div>


    <!-- 信封 -->

    <div class="envelope" id="envelope">

      <div class="envelope-back"></div>

      <div class="envelope-bottom"></div>

      <div class="envelope-flap"></div>

      <!-- 火漆 -->

      <div
        class="wax-seal"
        id="waxSeal"
        onclick="removeSeal(event)"
        title="點擊火漆郵戳"
      ></div>

    </div>


    <div
      class="seal-hint"
      id="sealHint"
    >
      點擊紅色火漆郵戳
    </div>

  </div>

</section>


<!-- =========================
     真正的信件
========================= -->

<section class="letter" id="letter">

  <h2>
    人被流星砸中的機率為百分之一
    與你相遇更是奇蹟
  </h2>

  <div
    class="letter-content"
    id="letterContent"
  >
曾經，我不理解為什麼會有人在網路上交友，直到我開始覺得現生沒有人在乎我，沒有人懂我的梗，沒有人能接住我的情緒，所以我開始追星，因為滑到了一句話「同擔是偶像送我的最好的禮物」。我希望能遇見比現生朋友更好的人，在你之前我只跟幾個人混熟過，有的現在已經淡忘在我的生活裡，有些到現在還有在斷斷續續的聯絡，可是直到遇見了你，我才明白我給出去的愛也可以得到回應，很感謝當初決定找你混熟的我，也很感謝那個你的朋友（就那個你說你吃醋的那個）能讓我們變得這麼熟、變得無話不談。每次在班上又沒人接我的話，沒人跟我一起去合作社，沒人下課陪我聊天，又或者說，我又在羨慕別人的友誼時我總是想起你，我想如果你是我的現生朋友，我們一定會很好很好，一定每節下課就很吵，一定會一起蛐蛐別人！然後想著想著我就想哭了。

我的個性很奇怪，常常把話憋在心裏，別人問起，我總是說「沒關係」但是其實我都快哭了！但是唯獨在你面前，我可以放下一切，什麼都不管，不用裝大度不用裝開朗。

很慶幸我們兩個本不應有交集的人最後玩在了一起。不曾對你說過，但是我想趁機告訴你，你就像陽光一樣，灑落在我的世界，我的世界因為你感受到了溫暖。明明我們隔著一個螢幕，卻好像從來沒有因為距離而陌生，開心的時候，我會想和你分享，難過的時候，也會因為想到還有你在，而覺得沒那麼孤單。升上九年級之後我就一直陷入一個焦慮中，那股焦慮感就像颱風天的大海，洶湧的海浪一陣一陣沖進我的心裡，但是你總是像一塊浮木一樣，拯救我於水火之中（這樣說會不會太誇張），不管，我就是很謝謝你，也很愛你。

不在乎自己在別人心裡的地位算長大嗎？我有一個從小一就很好的閨蜜，說是閨蜜，但我最近總是在想他到底把我放在他人生中的哪一個層次。他的性格很好，好到我身邊的朋友都是他的朋友，而且很喜歡他，是真的很喜歡很喜歡的那種，平常會發便利貼誇她，在聊天的時候也總是說道「xxx為什麼可以跟所有人當朋友」「xxx為什麼長的那麼好看」「xxx上次跟我幹嘛幹嘛...」說說話吧，其實我一點都不想聽，一點都不在乎，但是我身邊的人全部都是他的朋友，不管是我先認識的人還是我湊合他們認識的，好像跟他玩都比跟我玩還要玩得好，我一直在說服我自己「明明是你讓他們認識的，現在他們熟了你怎麼又不開心了」但是我藏不住事，有開心的事我就想分享，所以我身邊的朋友他都知道，但是我問起他身邊的人他總是敷衍帶過。以前上加強班只有我們兩個熟，我們每次下課都一起玩，一起回家，但是現在多了兩個人，一開始我還覺得大家都是朋友，我們都很好，什麼都可以聊，可以聊八卦可以抱怨，但是我越來越覺得我聽不懂他們在說什麼了，我們之間的隔閡越來越厚。我把這一切的錯都怪在我的分享欲太強，我總是管不住自己的嘴而且又很愛多管閒事，我總是希望大家可以開開心心的，希望大家都有朋友，我真的很矛盾。所以我很喜歡你，你的好我可以一個人享受，我可以不需要聽到身邊的人一直說著關於你的我不知道的那一面，我可以不讓他知道你的存在，這樣你就屬於我一個人了（好像變態），而且跟你玩安全感很足夠，你會主動把我標在主頁、你會無條件的支持我，所以我可以不用揣測你給我的愛，我真的很怕我把別人放在第一順位但是別人並不覺得我們是最好的，但是我相信我們是對方的第一（吧），反正你在我心裡是第一。

對了，你最近一直在說你淡坑徐明浩，雖然我總是叫你不要退，但其實我更希望你能開心，追星本就是為自己生活增添一筆色彩的事，如果總是要想著虧欠了哪位偶像，又或者覺得誰讓你不開心了、誰讓你內耗了，那我覺得你就退吧！反正也愛過了，真正努力愛過了那還有什麼好遺憾的呢？如果nct或者黃冠亨更能帶給你幸福，那我支持你。雖然是這樣說但是還是會有點遺憾啦，畢竟是因為seventeen才認識你的，我們也還沒有一起去看過徐明浩，但是等到天時地利人和時我們再一起去看吧！如果你當時已經退坑了，那就當作致敬你13歲（還是12歲）的青春男主吧！

笑死我真的不會什麼很厲害的敘事法，也不會華麗的詞藻，但是我真的想讓你知道我很喜歡你，我很珍惜你，希望我們可以一直一直都這麼好，希望我們付出給對方的愛是平等、互相的。

李璇聿，很高興認識你！

祝在人際關係這題我們都會得到各自人生中的最優解。

—— 申晶㬊的老婆
  </div>


  <button
    class="back"
    onclick="lockAgain()"
  >
    重新上鎖
  </button>

</section>

</main>


<script>

/* =========================
   密碼
========================= */

const CORRECT_PASSWORD = "1242";


/* =========================
   元件
========================= */

const lockScreen =
  document.getElementById("lockScreen");

const envelopeScreen =
  document.getElementById("envelopeScreen");

const letter =
  document.getElementById("letter");

const passwordInput =
  document.getElementById("password");

const error =
  document.getElementById("error");

const waxSeal =
  document.getElementById("waxSeal");

const sealHint =
  document.getElementById("sealHint");

const envelopeArea =
  document.getElementById("envelopeArea");


/* =========================
   開鎖
========================= */

function unlock() {

  if (passwordInput.value === CORRECT_PASSWORD) {

    lockScreen.style.display = "none";

    envelopeScreen.style.display = "block";

    error.textContent = "";

    passwordInput.value = "";

  } else {

    error.textContent =
      "密碼不正確，請再試一次。";

    passwordInput.value = "";

    passwordInput.focus();

  }

}


/* =========================
   點擊火漆
========================= */

let sealRemoved = false;

function removeSeal(event) {

  event.stopPropagation();

  if (sealRemoved) return;

  sealRemoved = true;

  waxSeal.classList.add("removed");

  sealHint.textContent =
    "火漆已解開，向上滑動信封";

  sealHint.classList.remove("hidden");

}


/* =========================
   上滑開信
========================= */

let startY = 0;
let endY = 0;

envelopeArea.addEventListener(
  "touchstart",
  function(e) {

    startY = e.touches[0].clientY;

  },
  { passive: true }
);


envelopeArea.addEventListener(
  "touchend",
  function(e) {

    endY = e.changedTouches[0].clientY;

    const distance = startY - endY;

    if (
      sealRemoved &&
      distance > 60
    ) {

      openEnvelope();

    }

  },
  { passive: true }
);


/* =========================
   電腦滑鼠拖曳
========================= */

let mouseStartY = 0;

envelopeArea.addEventListener(
  "mousedown",
  function(e) {

    mouseStartY = e.clientY;

  }
);


envelopeArea.addEventListener(
  "mouseup",
  function(e) {

    const distance =
      mouseStartY - e.clientY;

    if (
      sealRemoved &&
      distance > 60
    ) {

      openEnvelope();

    }

  }
);


/* =========================
   開信
========================= */

function openEnvelope() {

  if (
    envelopeScreen.classList.contains("opened")
  ) {
    return;
  }

  envelopeScreen.classList.add("opened");

  setTimeout(function() {

    envelopeScreen.style.display = "none";

    letter.style.display = "block";

    window.scrollTo({
      top: 0,
      behavior: "smooth"
    });

  }, 1700);

}


/* =========================
   重新上鎖
========================= */

function lockAgain() {

  letter.style.display = "none";

  envelopeScreen.classList.remove("opened");

  envelopeScreen.style.display = "none";

  waxSeal.classList.remove("removed");

  sealRemoved = false;

  sealHint.textContent =
    "點擊紅色火漆郵戳";

  error.textContent = "";

  lockScreen.style.display = "flex";

}


/* =========================
   Enter 解鎖
========================= */

passwordInput.addEventListener(
  "keydown",
  function(e) {

    if (e.key === "Enter") {

      unlock();

    }

  }
);

</script>

</body>
</html>
