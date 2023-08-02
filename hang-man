const readline = require('readline');
function getRandomWord(words) {
  if (!Array.isArray(words) || words.length === 0) {
    return null;
  }
  const randomIndex = Math.floor(Math.random() * words.length);
  return words[randomIndex];}
  var kelimeler = [
    'ELMA',
    'KİTAP',
    'KALEM',
    'KAPI',
    'AYAK',
    'BİLGİSAYAR',
    'MERHABA',
    'GÜNEŞ'
  ]
  const randomWord = getRandomWord(kelimeler);
  //console.log( randomWord);
 function altCizgiYazdir(harf){
  var altCizgi = "_".repeat(harf);
  return altCizgi;
 }
 const rl = readline.createInterface({
  input: process.stdin,
  output: process.stdout
});

const kelime = "merhaba";
let tamamlananKelime = "_".repeat(kelime.length);
let yanlisHarfSayisi = 0;

const asmaAdimlari = [
  `
   +---+
   |   |
       |
       |
       |
       |
 =========`,
  `
   +---+
   |   |
   O   |
       |
       |
       |
 =========`,
  `
   +---+
   |   |
   O   |
   |   |
       |
       |
 =========`,
  `
   +---+
   |   |
   O   |
  /|   |
       |
       |
 =========`,
  `
   +---+
   |   |
   O   |
  /|\\  |
       |
       |
 =========`,
  `
   +---+
   |   |
   O   |
  /|\\  |
  /    |
       |
 =========`,
  `
   +---+
   |   |
   O   |
  /|\\  |
  / \\  |
       |
 =========`
];

function tamamlaKelime() {
  rl.question("Bir harf girin (Çıkmak için 'exit' yazın): ", (harf) => {
    if (harf.length !== 1) {
      console.log("Lütfen sadece 1 harf girin!");
      tamamlaKelime();
    } else if (harf.toLowerCase() === 'exit') {
      console.log("Programdan çıkılıyor.");
      rl.close();
    } else {
      let harfIndex = kelime.indexOf(harf);
      if (harfIndex === -1) {
        yanlisHarfSayisi++;
        console.log("Yanlış harf! Yanlış harf sayısı: " + yanlisHarfSayisi);
        console.log(asmaAdimlari[yanlisHarfSayisi - 1]);
      } else {
        while (harfIndex !== -1) {
          tamamlananKelime = tamamlananKelime.slice(0, harfIndex) + harf + tamamlananKelime.slice(harfIndex + 1);
          harfIndex = kelime.indexOf(harf, harfIndex + 1);
        }
        console.log("Tamamlanan kelime: " + tamamlananKelime);
      }

      if (tamamlananKelime === kelime) {
        console.log("Tebrikler! Kelimeyi doğru tamamladınız: " + tamamlananKelime);
        rl.close();
      } else if (yanlisHarfSayisi === asmaAdimlari.length) {
        console.log("Üzgünüm, adam asıldı! Doğru kelime: " + kelime);
        rl.close();
      } else {
        tamamlaKelime();
      }
    }
  });
}

console.log("Tamamlanan kelime: " + tamamlananKelime);
tamamlaKelime();



