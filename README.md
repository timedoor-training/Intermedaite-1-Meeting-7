# Timedoor Training Teen
## Intermediate A - Meeting 7

Pertemuan 7 mempelajari cara js bekerja, apa itu js engine pada browser. Memory Heap dan call stack, 
#### Video pada Meeting 7
>https://www.youtube.com/watch?v=XQpZIEejKDY 

Tips
>Contoh dari LIFO (last in First Out) adalah pada lift.
>Orang yang terakhir masuk (Last In) akan keluar lebih dulu (First Out)


Contoh aplikasi yang akan dibuat :
>https://timedoor-catchthebird.netlify.app/

untuk memulai pembuatan aplikasi download terlebih dahulu di dalam repo
>https://github.com/timedoorAcademy-smp/int1-catch-the-bird-template



###  HTML Code Basic

```html

<body>
    <img width="120px" height="120px" src="image/bird.webp" id="player">
    <p id="scoreMain">Score: <span class="scoreGame">0</span></p>
</body>
```



### Javascript Basic
```html
   <script>

    var bird = document.getElementById('player');
    var score = 0;
    var time = 0;
    const showScore = document.querySelector('.scoreGame');

    //buat function agar bird selalu berpindah tempat secara random
    function randomMove() {
        var x = Math.floor(Math.random() * 481);
        var y = Math.floor(Math.random() * 1052);
        bird.style.top = x + 'px';
        bird.style.left = y + 'px';
    }

    //buat loop dengan wait 1 detik
    var transisi = setInterval(function () {
        randomMove();
        time++;

        if (time == 10) {
            if (score >= 5) {
                document.body.style.backgroundImage = "url(image/win.jpg)";
                reset()
            }
            else {
                document.body.style.backgroundImage = "url(image/lose.png)";
                reset()
            }
        }
    }, 1000);


    function reset() {
        clearInterval(transisi); //perintah untuk menghentikan perulangan
        bird.style.display = 'none';
        document.getElementById('scoreMain').style.display = 'none';
    }

    //buat event agar bird bisa di klik
    bird.onclick = function () {
        //saat bird di klik, score akan bertambah 1
        score++;
        showScore.innerHTML = `${score}  `;
    };


</script>
```
