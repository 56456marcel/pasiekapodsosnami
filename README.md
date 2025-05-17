<!DOCTYPE html>
<html lang="pl">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Pasieka Pod Sosnami - Sklep Pszczelarski</title>
<link rel="stylesheet" href="style.css" />
</head>
<body>

<header>
  <h1>Pasieka Pod Sosnami</h1>
</header>

<section class="opis-pasieki">
  <p>
    🌿 <strong>Witamy w Pasiece Pod Sosnami!</strong> 🌿<br />
    Z pasją i troską zbieramy najwyższej jakości naturalne miody, dbając o zdrowie pszczół i środowiska. <br />
    Nasze produkty to harmonia smaku i natury, które przynoszą słodycz i zdrowie prosto do Twojego domu.
  </p>
</section>

<h2 class="naglowek">Nasze produkty:</h2>

<div class="container">
  <div class="products">
    <!-- produkty (jak wcześniej) -->
    <div class="product" data-name="Miód lipowy" data-img="https://sklep.brat.pl/userdata/public/gfx/8234/lipowy-900ml.jpg" data-price="35 zł / 1 kg" data-desc="Miód lipowy o delikatnym smaku, zbierany z kwiatów lipy.">
      <div class="product-header">
        <img src="https://sklep.brat.pl/userdata/public/gfx/8234/lipowy-900ml.jpg" alt="Miód lipowy" />
        <div class="product-info">
          <h3>Miód lipowy</h3>
          <p>35 zł / 1 kg</p>
        </div>
        <button class="open-btn">Otwórz</button>
      </div>
      <div class="product-details">
        <img alt="" />
        <div class="details-text">
          <h3></h3>
          <p class="price"></p>
          <p class="description"></p>
        </div>
      </div>
    </div>

    <div class="product" data-name="Miód wielokwiatowy" data-img="https://sklep.brat.pl/userdata/public/gfx/8226/miod-wielokwiatowy-900ml.jpg" data-price="30 zł / 1 kg" data-desc="Miód wielokwiatowy o bogatym aromacie i smaku z wielu kwiatów.">
      <div class="product-header">
        <img src="https://sklep.brat.pl/userdata/public/gfx/8226/miod-wielokwiatowy-900ml.jpg" alt="Miód wielokwiatowy" />
        <div class="product-info">
          <h3>Miód wielokwiatowy</h3>
          <p>30 zł / 1 kg</p>
        </div>
        <button class="open-btn">Otwórz</button>
      </div>
      <div class="product-details">
        <img alt="" />
        <div class="details-text">
          <h3></h3>
          <p class="price"></p>
          <p class="description"></p>
        </div>
      </div>
    </div>

    <div class="product" data-name="Miód gryczany" data-img="https://bioshop.com.pl/userdata/public/gfx/8750/Miod-gryczany-1200-g---Pasieki-Rodziny-Sadowskich.jpg" data-price="40 zł / 1 kg" data-desc="Miód gryczany o intensywnym smaku i właściwościach zdrowotnych.">
      <div class="product-header">
        <img src="https://bioshop.com.pl/userdata/public/gfx/8750/Miod-gryczany-1200-g---Pasieki-Rodziny-Sadowskich.jpg" alt="Miód gryczany" />
        <div class="product-info">
          <h3>Miód gryczany</h3>
          <p>40 zł / 1 kg</p>
        </div>
        <button class="open-btn">Otwórz</button>
      </div>
      <div class="product-details">
        <img alt="" />
        <div class="details-text">
          <h3></h3>
          <p class="price"></p>
          <p class="description"></p>
        </div>
      </div>
    </div>

  </div>
</div>

<script>
  document.querySelectorAll('.product').forEach(product => {
    const btn = product.querySelector('.open-btn');
    const details = product.querySelector('.product-details');
    const imgElem = details.querySelector('img');
    const nameElem = details.querySelector('h3');
    const priceElem = details.querySelector('.price');
    const descElem = details.querySelector('.description');

    btn.addEventListener('click', () => {
      const isActive = details.classList.contains('active');

      document.querySelectorAll('.product-details.active').forEach(openDetails => {
        openDetails.classList.remove('active');
      });

      if (!isActive) {
        imgElem.src = product.getAttribute('data-img');
        imgElem.alt = product.getAttribute('data-name');
        nameElem.textContent = product.getAttribute('data-name');
        priceElem.textContent = product.getAttribute('data-price');
        descElem.textContent = product.getAttribute('data-desc');
        details.classList.add('active');
        btn.textContent = 'Zamknij';
      } else {
        details.classList.remove('active');
        btn.textContent = 'Otwórz';
      }

      document.querySelectorAll('.product').forEach(p => {
        if (p !== product) {
          p.querySelector('.open-btn').textContent = 'Otwórz';
        }
      });
    });
  });
</script>

</body>
</html>
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: #fffbee;
  color: #4b3b00;
  margin: 0;
  padding: 0 20px;
}

header h1 {
  text-align: center;
  padding: 25px 0 10px;
  font-size: 2.8rem;
  font-weight: 700;
  color: #b28500;
  text-shadow: 1px 1px 3px #d6b800;
}

.opis-pasieki {
  max-width: 900px;
  margin: 0 auto 40px auto;
  padding: 25px 35px;
  background: linear-gradient(135deg, #fff4c2, #ffe066);
  border-radius: 15px;
  box-shadow: 0 8px 20px rgba(255, 211, 80, 0.5);
  color: #6b4f00;
  font-size: 1.25rem;
  font-style: italic;
  text-align: center;
  line-height: 1.6;
  border: 2px solid #d6b800;
  letter-spacing: 0.03em;
  user-select: none;
}

.naglowek {
  text-align: center;
  font-size: 2rem;
  margin-bottom: 25px;
  color: #aa7a00;
  text-shadow: 1px 1px 2px #f5e28a;
}

.container {
  max-width: 950px;
  margin: 0 auto;
}

.products {
  display: flex;
  flex-direction: column;
  gap: 25px;
}

.product {
  background: #fffdf3;
  border-radius: 12px;
  box-shadow: 0 3px 10px rgba(0,0,0,0.08);
  padding: 15px 20px;
  transition: background 0.3s ease;
}

.product:hover {
  background: #fff8b0;
}

.product-header {
  display: flex;
  align-items: center;
  gap: 20px;
}

.product-header img {
  width: 120px;
  height: auto;
  border-radius: 10px;
  box-shadow: 0 0 8px #d6b800a0;
}

.product-info h3 {
  margin: 0 0 8px;
  font-size: 1.5rem;
  color: #8a6000;
}

.product-info p {
  margin: 0;
  font-weight: 600;
  color: #6b4f00;
}

.open-btn {
  margin-left: auto;
  padding: 8px 16px;
  background-color: #deb800;
  border: none;
  border-radius: 25px;
  color: #fff9d3;
  font-weight: 700;
  cursor: pointer;
  transition: background-color 0.3s ease;
  box-shadow: 0 4px 10px #d6b800cc;
}

.open-btn:hover {
  background-color: #a57f00;
}

.product-details {
  margin-top: 20px;
  display: none;
  border-top: 2px solid #d6b800;
  padding-top: 20px;
  gap: 15px;
  align-items: center;
}

.product-details.active {
  display: flex;
}

.product-details img {
  max-width: 220px;
  border-radius: 10px;
  box-shadow: 0 0 12px #d6b800cc;
}

.details-text {
  max-width: 600px;
  margin-left: 20px;
  color: #5a4000;
}

.details-text h3 {
  margin-top: 0;
  font-size: 1.8rem;
  color: #8a6000;
}

.details-text .price {
  font-size: 1.4rem;
  font-weight: 700;
  margin: 10px 0;
  color: #aa7a00;
}

.details-text .description {
  font-size: 1.1rem;
  line-height: 1.5;
}

/* Responsywność */
@media (max-width: 720px) {
  .products {
    flex-direction: column;
  }

  .product-details.active {
    flex-direction: column;
    align-items: flex-start;
  }

  .product-details img {
    margin-bottom: 15px;
    max-width: 100%;
  }

  .details-text {
    margin-left: 0;
  }

  .product-header {
    flex-direction: column;
    align-items: flex-start;
  }

  .open-btn {
    margin-left: 0;
    margin-top: 10px;
  }
}
