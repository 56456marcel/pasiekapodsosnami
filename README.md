<!DOCTYPE html>
<html lang="pl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Pasieka Pod Sosnami</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #fffbe6;
      color: #333;
    }

    .topbar {
      background-color: #ffcc00;
      padding: 1rem;
      text-align: center;
      box-shadow: 0 2px 4px rgba(0,0,0,0.1);
    }

    .topbar h1 {
      margin: 0;
      font-size: 2rem;
    }

    .about, .products, .details {
      max-width: 1000px;
      margin: 2rem auto;
      padding: 1rem;
    }

    .about h2, .products h2 {
      font-size: 1.5rem;
      margin-bottom: 1rem;
      text-align: center;
    }

    .about p {
      font-size: 1.1rem;
      text-align: center;
      line-height: 1.6;
    }

    .products {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem;
    }

    .product {
      background: #fff;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
      overflow: hidden;
      width: 250px;
      text-align: center;
      cursor: pointer;
      transition: transform 0.2s;
    }

    .product:hover {
      transform: scale(1.03);
    }

    .product img {
      width: 100%;
      height: auto;
    }

    .product h3 {
      margin: 0;
      padding: 0.5rem;
      background: #ffe680;
    }

    .details .product-detail {
      display: flex;
      flex-wrap: wrap;
      gap: 2rem;
      background: #fff;
      padding: 2rem;
      border-radius: 10px;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
    }

    .details img {
      max-width: 300px;
      width: 100%;
      border-radius: 10px;
    }

    .details .price {
      font-weight: bold;
      margin-top: 1rem;
    }

    .details .desc {
      margin-top: 1rem;
      line-height: 1.5;
    }

    .details .contact {
      margin-top: 2rem;
      font-size: 1.1rem;
      color: #d2691e;
    }

    footer {
      text-align: center;
      padding: 1rem;
      background: #ffcc00;
      margin-top: 3rem;
    }

    @media (max-width: 600px) {
      .product, .details .product-detail {
        flex-direction: column;
        align-items: center;
      }

      .details img {
        max-width: 100%;
      }
    }
  </style>
</head>
<body>
  <header class="topbar">
    <h1>Pasieka Pod Sosnami</h1>
  </header>

  <section class="about">
    <h2>O naszej pasiece</h2>
    <p>Pasieka Pod Sosnami to rodzinna pasieka prowadzona z pasją i miłością do pszczół. Od lat produkujemy naturalne miody z czystych terenów leśnych i łąkowych. Nasze produkty są w pełni ekologiczne i pochodzą bezpośrednio od naszych pszczół.</p>
  </section>

  <section class="products">
    <h2>Nasze produkty:</h2>

    <div class="product" onclick="showProduct(0)">
      <img src="images/miod-lipowy.jpg" alt="Miód lipowy" />
      <h3>Miód lipowy</h3>
    </div>

    <div class="product" onclick="showProduct(1)">
      <img src="images/miod-wielokwiatowy.jpg" alt="Miód wielokwiatowy" />
      <h3>Miód wielokwiatowy</h3>
    </div>

    <div class="product" onclick="showProduct(2)">
      <img src="images/miod-gryczany.jpg" alt="Miód gryczany" />
      <h3>Miód gryczany</h3>
    </div>
  </section>

  <section class="details" id="product-details">
    <!-- szczegóły pojawią się po kliknięciu -->
  </section>

  <footer>
    <p>&copy; 2025 Pasieka Pod Sosnami</p>
  </footer>

  <script>
    const products = [
      {
        name: "Miód lipowy",
        img: "images/miod-lipowy.jpg",
        price: "35 zł / 1 kg",
        desc: "Naturalny miód lipowy o delikatnym smaku i aromacie lipy."
      },
      {
        name: "Miód wielokwiatowy",
        img: "images/miod-wielokwiatowy.jpg",
        price: "30 zł / 1 kg",
        desc: "Miód z różnych kwiatów łąkowych, idealny na co dzień."
      },
      {
        name: "Miód gryczany",
        img: "images/miod-gryczany.jpg",
        price: "40 zł / 1 kg",
        desc: "Ciemny i intensywny miód gryczany, bogaty w składniki mineralne."
      }
    ];

    function showProduct(index) {
      const p = products[index];
      document.getElementById('product-details').innerHTML = `
        <div class="product-detail">
          <img src="${p.img}" alt="${p.name}" />
          <div>
            <h3>${p.name}</h3>
            <p class="price">${p.price}</p>
            <p class="desc">${p.desc}</p>
            <p class="contact">Zamów telefonicznie: 123-456-789</p>
          </div>
        </div>
      `;
    }
  </script>
</body>
</html>
