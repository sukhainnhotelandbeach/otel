<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Otel rezervasyon sitesi - Plaj, sessizlik ve deniz kenarında huzurlu bir tatil.">
    <title>Otel Rezervasyon Sitesi</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }

        /* Navbar */
        .navbar {
            background-color: #333;
            overflow: hidden;
            position: sticky;
            top: 0;
        }
        .navbar a {
            float: left;
            display: block;
            color: white;
            text-align: center;
            padding: 14px 20px;
            text-decoration: none;
            transition: 0.3s;
        }
        .navbar a:hover {
            background-color: #575757;
        }

        /* Mobile Optimization */
        @media (max-width: 768px) {
            .navbar a {
                float: none;
                text-align: left;
                padding-left: 20px;
            }
            .gallery img {
                width: 100%;
            }
            .room-gallery img {
                width: 100%;
                margin: 5px 0;
            }
            .info-box {
                width: 90%;
            }
        }

        .section {
            padding: 40px 20px;
            display: none;
            animation: fadeIn 1s forwards;
        }
        .active {
            display: block;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Gallery */
        .gallery {
            display: flex;
            justify-content: space-around;
            margin-top: 20px;
        }
        .gallery img {
            width: 30%;
            height: auto;
            border-radius: 8px;
        }

        /* Comments Section */
        .comments {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
        }
        .comment-box {
            margin-bottom: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }
        label {
            display: block;
            margin-bottom: 5px;
        }
        select, input, textarea {
            width: 100%;
            padding: 8px;
            margin: 5px 0 10px 0;
        }

        .reserve-btn {
            padding: 10px 20px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .reserve-btn:hover {
            background-color: #218838;
        }

        .room-gallery img {
            width: 25%;
            margin: 5px;
            height: auto;
            border-radius: 8px;
        }

        footer {
            background-color: #333;
            color: white;
            text-align: center;
            padding: 20px 0;
            position: relative;
            width: 100%;
            bottom: 0;
        }

        .footer-info {
            margin-top: 20px;
            font-size: 16px;
        }

        .price-display {
            font-size: 20px;
            font-weight: bold;
            margin-top: 20px;
        }

        .rating {
            display: flex;
            flex-direction: row-reverse;
            justify-content: flex-end;
        }
        .rating input {
            display: none;
        }
        .rating label {
            font-size: 20px;
            color: lightgray;
            cursor: pointer;
        }
        .rating input:checked ~ label {
            color: gold;
        }

        /* Hero Section */
        .hero {
            background-image: url('https://via.placeholder.com/1200x400?text=Otel+Kapak+Resmi');
            background-size: cover;
            height: 400px;
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            text-align: center;
            font-size: 30px;
            font-weight: bold;
        }

        .info-box {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0px 0px 10px rgba(0,0,0,0.1);
            width: 60%;
            margin: 20px auto;
            text-align: center;
        }

    </style>
</head>
<body>

<!-- Ana Sayfa -->
<div class="hero">
    Otelimize Hoş Geldiniz!
</div>

<div class="navbar">
    <a href="#home" onclick="showSection('home')">Ana Sayfa</a>
    <a href="#comments" onclick="showSection('comments')">Yorumlar</a>
    <a href="#reservation" onclick="showSection('reservation')">Rezervasyon</a>
</div>

<div id="home" class="section active">
    <h1>Otelimize Hoş Geldiniz!</h1>
    <p>Rahat ve konforlu odalarımızla size eşsiz bir deneyim sunuyoruz.</p>

    <div class="gallery">
        <img src="https://via.placeholder.com/400x300" alt="Otel 1">
        <img src="https://via.placeholder.com/400x300" alt="Otel 2">
        <img src="https://via.placeholder.com/400x300" alt="Otel 3">
    </div>

    <div class="info-box">
        <h2>Neden Bizi Seçmelisiniz?</h2>
        <p>Plaj imkanı, sessiz ve sakin bir ortam, denize yakınlık ve eşsiz müşteri hizmetlerimizle unutulmaz bir tatil deneyimi yaşayın.</p>
        <p>Otelimiz, geniş ve temiz plaj alanı sunarak, deniz kenarında huzurlu bir tatil geçirmenizi sağlar. Özel plaj alanımızda güneşlenebilir, şezlonglarda dinlenebilir ve denizin tadını çıkarabilirsiniz.</p>
        <p>Şehrin gürültüsünden uzak, doğayla iç içe bir konumda bulunan otelimiz, huzur arayan misafirlerimize mükemmel bir kaçış noktası sunuyor. Tüm odalarımız, gürültüden uzak ve rahat bir uyku için tasarlandı.</p>
        <p>Denize sadece birkaç adım mesafede yer alan otelimiz, sabahları deniz manzarası eşliğinde uyanmanızı sağlayacak. Tatilinizin tadını çıkarmak için doğru adres burası.</p>
    </div>
</div>

<!-- Yorumlar Bölümü -->
<div id="comments" class="section">
    <h2>Yorumlar</h2>
    <div class="comments">
        <!-- Yorumların listelendiği kısım -->
    </div>

    <!-- Yorum Ekleme -->
    <h3>Yorum Ekle</h3>
    <form id="comment-form" onsubmit="addComment(event)">
        <div class="form-group">
            <label for="photo">Fotoğraf Yükleyin:</label>
            <input type="file" id="photo" name="photo" accept="image/*" required>
        </div>
        <div class="rating">
            <input type="radio" name="star" value="5" id="star5" required>
            <label for="star5">★</label>
            <input type="radio" name="star" value="4" id="star4">
            <label for="star4">★</label>
            <input type="radio" name="star" value="3" id="star3">
            <label for="star3">★</label>
            <input type="radio" name="star" value="2" id="star2">
            <label for="star2">★</label>
            <input type="radio" name="star" value="1" id="star1">
            <label for="star1">★</label>
        </div>
        <div class="form-group">
            <label for="comment">Yorumunuz:</label>
            <textarea id="comment" name="comment" rows="4" required></textarea>
        </div>
        <button type="submit" class="reserve-btn">Yorumu Ekle</button>
    </form>
</div>

<!-- Rezervasyon Bölümü -->
<div id="reservation" class="section">
    <h2>Rezervasyon Yap</h2>
    <div class="form-group">
        <label for="checkin">Giriş Tarihi:</label>
        <input type="date" id="checkin" name="checkin">
    </div>
    <div class="form-group">
        <label for="checkout">Çıkış Tarihi:</label>
        <input type="date" id="checkout" name="checkout">
    </div>
    <div class="form-group">
        <label for="adults">Yetişkin Sayısı:</label>
        <input type="number" id="adults" name="adults" value="2" min="1">
    </div>
    <div class="form-group">
        <label for="children">Çocuk Sayısı:</label>
        <input type="number" id="children" name="children" value="0" min="0">
    </div>
    <div class="form-group">
        <label for="room">Oda Tipi:</label>
        <select id="room" name="room" onchange="showRoomImages()">
            <option value="450" data-images="https://via.placeholder.com/200x150?text=Kısmi+Deniz+Manzaralı+1,https://via.placeholder.com/200x150?text=Kısmi+Deniz+Manzaralı+2">Kısmi Deniz Manzaralı Oda - 450 TL/gece</option>
            <option value="600" data-images="https://via.placeholder.com/200x150?text=Deniz+Manzaralı+1,https://via.placeholder.com/200x150?text=Deniz+Manzaralı+2">Deniz Manzaralı Oda - 600 TL/gece</option>
        </select>
    </div>

    <div id="room-gallery" class="room-gallery"></div>
    
    <button class="reserve-btn" onclick="calculatePrice()">Fiyatı Hesapla</button>
    <div id="price-result" class="price-display">Toplam Fiyat: -</div>
</div>

<!-- İletişim Bölümü -->
<footer>
    <p>Otel Rezervasyon Sitesi | Tüm Hakları Saklıdır © 2024</p>
    <div class="footer-info">
        <p>Email: info@otelsec.com | Telefon: +90 555 555 5555</p>
    </div>
</footer>

<script>
    function showSection(sectionId) {
        var sections = document.getElementsByClassName('section');
        for (var i = 0; i < sections.length; i++) {
            sections[i].classList.remove('active');
        }
        document.getElementById(sectionId).classList.add('active');
    }

    function addComment(event) {
        event.preventDefault();
        const starRating = document.querySelector('input[name="star"]:checked').value;
        const commentText = document.getElementById("comment").value;
        const commentsDiv = document.querySelector(".comments");
        const photoFile = document.getElementById("photo").files[0];

        const newComment = document.createElement("div");
        newComment.classList.add("comment-box");

        const reader = new FileReader();
        reader.onload = function(event) {
            const photo = document.createElement("img");
            photo.src = event.target.result;
            photo.style.width = "100px";
            photo.style.borderRadius = "8px";
            newComment.appendChild(photo);

            newComment.innerHTML += `<p><strong>Yeni Yorum (${starRating} Yıldız):</strong> ${commentText}</p>`;
            commentsDiv.appendChild(newComment);
            document.getElementById("comment-form").reset();
        };
        reader.readAsDataURL(photoFile);
    }

    function showRoomImages() {
        const selectedOption = document.getElementById("room").selectedOptions[0];
        const images = selectedOption.getAttribute("data-images").split(",");
        const roomGallery = document.getElementById("room-gallery");
        
        roomGallery.innerHTML = "";
        images.forEach(function(imageUrl) {
            const img = document.createElement("img");
            img.src = imageUrl;
            roomGallery.appendChild(img);
        });
    }

    function calculatePrice() {
        let checkinDate = new Date(document.getElementById("checkin").value);
        let checkoutDate = new Date(document.getElementById("checkout").value);
        let roomPrice = parseInt(document.getElementById("room").value);
        let timeDifference = checkoutDate - checkinDate;
        let dayDifference = timeDifference / (1000 * 3600 * 24);

        if (dayDifference <= 0) {
            alert("Lütfen geçerli bir giriş ve çıkış tarihi seçin.");
            return;
        }

        let adults = parseInt(document.getElementById("adults").value);
        let children = parseInt(document.getElementById("children").value);
        let totalPrice = dayDifference * (roomPrice * (adults + (children * 0.5)));

        document.getElementById("price-result").innerHTML = "Toplam Fiyat: " + totalPrice + " TL";
    }
</script>

</body>
</html>
