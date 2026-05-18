<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Canım Ailem</title>
    <style>
        /* Google Fonts - Şık ve Okunaklı Yazı Tipi */
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600&family=Great+Vibes&display=swap');

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body, html {
            height: 100%;
            font-family: 'Poppins', sans-serif;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Canlı ve Dinamik Arka Plan Animasyonu */
        .background-animated {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(-45deg, #0f172a, #1e1b4b, #3b0764, #1e3a8a);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            z-index: -2;
        }

        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }

        /* Aile Fotoğrafı Arka Planı (Hafif Flu ve Şık) */
        .photo-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: url('aile.png') no-repeat center center/cover;
            opacity: 0.25;
            filter: blur(4px);
            z-index: -1;
        }

        /* Ana Kart Tasarımı (Cam Efekti - Glassmorphism) */
        .container {
            width: 90%;
            max-width: 750px;
            min-height: 550px;
            background: rgba(255, 255, 255, 0.06);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.15);
            border-radius: 24px;
            padding: 40px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            align-items: center;
            text-align: center;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.4);
            position: relative;
            overflow: hidden;
        }

        /* Kartın İçindeki Küçük Orijinal Fotoğraf Alanı */
        .mini-photo {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            border: 3px solid rgba(255, 255, 255, 0.6);
            background: url('aile.png') no-repeat center center/cover;
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
            margin-bottom: 10px;
            transition: transform 0.5s ease;
        }

        .mini-photo:hover {
            transform: scale(1.05);
        }

        /* Sayfa Geçiş Animasyonları */
        .page {
            display: none;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.6s ease, transform 0.6s ease;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            flex-grow: 1;
            width: 100%;
        }

        .page.active {
            display: flex;
            opacity: 1;
            transform: translateY(0);
        }

        /* Başlıklar İçin Estetik Font */
        h1 {
            font-family: 'Great Vibes', cursive;
            font-size: 3.5rem;
            color: #fbbf24; /* Altın Sarısı */
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
        }

        /* Duygusal Sözler */
        p {
            font-size: 1.15rem;
            line-height: 1.8;
            color: #f8fafc;
            font-weight: 300;
            max-width: 600px;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.4);
        }

        /* Şık Buton Tasarımı */
        .btn-next {
            background: linear-gradient(135deg, #fbbf24, #d97706);
            color: #0f172a;
            border: none;
            padding: 14px 35px;
            font-size: 1rem;
            font-weight: 600;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 4px 15px rgba(251, 191, 36, 0.4);
            transition: all 0.3s ease;
            margin-top: 25px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .btn-next:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 20px rgba(251, 191, 36, 0.6);
            background: linear-gradient(135deg, #fef08a, #fbbf24);
        }

        .btn-next:active {
            transform: translateY(-1px);
        }

        /* Müzik Simgesi Alt Köşe */
        .music-indicator {
            position: absolute;
            bottom: 15px;
            right: 20px;
            font-size: 0.85rem;
            color: rgba(255, 255, 255, 0.4);
            display: none;
            align-items: center;
            gap: 5px;
        }

        .music-indicator.visible {
            display: flex;
        }

        /* Küçük Ekranlar İçin Uyum */
        @media (max-width: 480px) {
            h1 { font-size: 2.8rem; }
            p { font-size: 1rem; }
            .container { padding: 25px; min-height: 500px; }
            .mini-photo { width: 110px; height: 110px; }
        }
    </style>
</head>
<body>

    <div class="background-animated"></div>
    <div class="photo-bg"></div>

    <audio id="bg-music" loop>
        <source src="sarki.mp3" type="audio/mpeg">
    </audio>

    <div class="container">
        
        <div class="mini-photo"></div>

        <div class="page active" id="page-1">
            <h1>Canım Ailem...</h1>
            <p>Hayattaki en güvenli sığınağım, her düştüğümde elimden tutanım, yüzümdeki tebessümün en güzel sebepleri... İyi ki varsınız. Bu küçük köşe, size olan sonsuz sevgimin ufak bir nişanesidir.</p>
            <button class="btn-next" onclick="nextPage(1)">Başla & Dinle</button>
        </div>

        <div class="page" id="page-2">
            <h1>Anneme & Babama</h1>
            <p>Sizler benim bu hayattaki en sağlam çınarlarımsınız. Annemin duaları, babamın gölgesi yetiyor her fırtınayı atlatmama. Bizleri sevgiyle, emekle büyütüp bu güzel aileyi bir arada tuttuğunuz için size minnettarım. Ömrüm yettikçe başımın tacısınız.</p>
            <button class="btn-next" onclick="nextPage(2)">Devam Et</button>
        </div>

        <div class="page" id="page-3">
            <h1>Canım Ablalarıma</h1>
            <p>Abla demek, anne yarısı demekmiş; her sıkıştığımda arkama baktığımda gördüğüm o güven veren güç demekmiş. Sizin sevginiz, neşeniz ve hayata kattığınız zarafet olmasaydı bu aile hep bir kişi eksik kalırdı. Kalbi güzel ablalarım, sizi çok seviyorum.</p>
            <button class="btn-next" onclick="nextPage(3)">Devam Et</button>
        </div>

        <div class="page" id="page-4">
            <h1>Değerli Eniştelerime</h1>
            <p>Sadece ailemize katılmakla kalmadınız, bu yuvanın birer abisi, kardeşi ve en büyük destekçileri oldunuz. Samimiyetiniz, duruşunuz ve ailemize kattığınız tüm güzellikler için teşekkür ederim. İyi ki bizimlesiniz, iyi ki varsınız.</p>
            <button class="btn-next" onclick="nextPage(4)">Devam Et</button>
        </div>

        <div class="page" id="page-5">
            <h1>Geleceğimiz, Yeğenlerime</h1>
            <p>Evin neşesi, gözlerimizin ışığı canım yeğenlerim... Sizin o masum gülüşleriniz dünyadaki her şeye değer. Bu güzel ailenin yarını sizlersiniz. Hep birlikte, sağlıkla, sevgi dolu ve nice mutlu anılar biriktireceğimiz upuzun yıllara...</p>
            <button class="btn-next" onclick="nextPage(5)">Baştan Oku</button>
        </div>

        <div class="music-indicator" id="music-status">
            🎵 Arka planda müzik çalıyor...
        </div>

    </div>

    <script>
        // Sayfa Değiştirme ve Müzik Kontrol Fonksiyonu
        function nextPage(currentPageNumber) {
            // Aktif olan sayfayı bul ve kapat
            const currentBox = document.getElementById(`page-${currentPageNumber}`);
            currentBox.classList.remove('active');

            // Müzik kontrolü: İlk sayfadan geçişte müziği başlat
            if (currentPageNumber === 1) {
                const music = document.getElementById('bg-music');
                music.play().then(() => {
                    document.getElementById('music-status').classList.add('visible');
                }).catch(error => {
                    console.log("Müzik otomatik başlatılamadı, tarayıcı izni gerekiyor:", error);
                });
            }

            // Bir sonraki sayfa numarasını belirle (5'ten sonra 1'e dönecek şekilde)
            let nextPageNumber = currentPageNumber + 1;
            if (nextPageNumber > 5) {
                nextPageNumber = 1;
            }

            // Yeni sayfayı aktif et ve pürüzsüz animasyon için kısa bir delay koy
            const nextBox = document.getElementById(`page-${nextPageNumber}`);
            setTimeout(() => {
                nextBox.classList.add('active');
            }, 50);
        }
    </script>
</body>
</html>
