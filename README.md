
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Horizon Auto — Trusted Car Dealership</title>
  <meta name="description" content="Horizon Auto — 30+ quality used and new cars. Browse, calculate payments, book test drives." />
  <style>
    :root {
      --bg: #0f1724;
      --card: #0b1220;
      --muted: #94a3b8;
      --accent: #00b4d8;
      --glass: rgba(255,255,255,0.03);
    }
    * {
      box-sizing: border-box;
    }
    body {
      margin: 0;
      font-family: Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
      background: linear-gradient(180deg, #071025 0%, #071625 100%);
      color: #e6eef8;
    }
    .container {
      max-width: 1200px;
      margin: 28px auto;
      padding: 20px;
    }
    header {
      display: flex;
      gap: 12px;
      align-items: center;
      justify-content: space-between;
    }
    .brand {
      display: flex;
      gap: 12px;
      align-items: center;
    }
    .logo {
      width: 56px;
      height: 56px;
      border-radius: 8px;
      background: linear-gradient(135deg, #091124, #0c2332);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 700;
      color: var(--accent);
      font-size: 18px;
    }
    h1 {
      margin: 0;
      font-size: 20px;
    }
    p.lead {
      margin: 4px 0 0;
      color: var(--muted);
      font-size: 13px;
    }
    nav {
      display: flex;
      gap: 10px;
      align-items: center;
    }
    .btn {
      background: var(--accent);
      color: #002028;
      padding: 8px 12px;
      border-radius: 8px;
      text-decoration: none;
      font-weight: 600;
    }
    .link {
      background: transparent;
      border: 1px solid rgba(255,255,255,0.04);
      padding: 8px;
      border-radius: 8px;
      color: inherit;
      text-decoration: none;
      cursor: pointer;
    }

    /* search + filters */
    .controls {
      display: grid;
      grid-template-columns: 1fr 320px;
      gap: 12px;
      margin: 18px 0;
      align-items: center;
    }
    .search {
      display: flex;
      gap: 8px;
      background: var(--glass);
      padding: 8px;
      border-radius: 10px;
    }
    .search input {
      flex: 1;
      background: transparent;
      border: 0;
      color: inherit;
      padding: 8px;
      font-size: 14px;
    }
    .filters {
      display: flex;
      gap: 8px;
      align-items: center;
    }
    select, input[type=range] {
      background: #001a2b;
      color: #e6eef8;
      border: 1px solid rgba(255,255,255,0.06);
      padding: 8px;
      border-radius: 8px;
      appearance: none;
      -webkit-appearance: none;
      -moz-appearance: none;
    }
    select {
      min-width: 140px;
    }

    /* grid */
    .grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(260px,1fr));
      gap: 16px;
    }
    .card {
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      padding: 12px;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,0.03);
    }
    .card img {
      width: 100%;
      height: 150px;
      object-fit: cover;
      border-radius: 8px;
    }
    .meta {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 8px;
    }
    .title {
      font-weight: 700;
    }
    .price {
      font-weight: 800;
      color: var(--accent);
    }
    .specs {
      font-size: 13px;
      color: var(--muted);
      margin-top: 6px;
    }
    .card .actions {
      display: flex;
      gap: 8px;
      margin-top: 10px;
    }

    /* calculator sidebar */
    .sidebar {
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.015));
      padding: 12px;
      border-radius: 12px;
      border: 1px solid rgba(255,255,255,0.03);
    }
    .calc-row {
      display: flex;
      gap: 8px;
      margin-top: 8px;
    }
    label {
      font-size: 13px;
      color: var(--muted);
    }
    input, select {
      width: 100%;
      padding: 8px;
      border-radius: 8px;
      border: 1px solid rgba(255,255,255,0.04);
      background: transparent;
      color: inherit;
    }
    .result {
      font-size: 20px;
      font-weight: 800;
      margin-top: 12px;
    }

    /* modal */
    .modal-backdrop {
      position: fixed;
      inset: 0;
      background: rgba(0,0,0,0.6);
      display: none;
      align-items: center;
      justify-content: center;
      padding: 20px;
      z-index: 1000;
    }
    .modal {
      max-width: 900px;
      width: 100%;
      background: linear-gradient(180deg, #001026, #001a2b);
      padding: 18px;
      border-radius: 12px;
    }
    .modal-grid {
      display: grid;
      grid-template-columns: 1fr 360px;
      gap: 12px;
    }
    .gallery img {
      width: 100%;
      height: 240px;
      object-fit: cover;
      border-radius: 8px;
    }
    .close {
      background: transparent;
      border: 0;
      color: var(--muted);
      cursor: pointer;
      font-size: 18px;
    }

    footer {
      margin-top: 30px;
      padding: 18px;
      border-top: 1px solid rgba(255,255,255,0.03);
      display: flex;
      justify-content: space-between;
      align-items: center;
      color: var(--muted);
    }

    /* responsive media queries */
    @media (max-width: 1024px) {
      .controls {
        grid-template-columns: 1fr 1fr;
      }
      .modal-grid {
        grid-template-columns: 1fr 1fr;
      }
    }
    @media (max-width: 768px) {
      .container {
        padding: 12px;
      }
      header {
        flex-direction: column;
        align-items: start;
        gap: 8px;
      }
      .controls {
        grid-template-columns: 1fr;
      }
      main {
        display: block;
      }
      .sidebar {
        margin-top: 20px;
      }
      .modal-grid {
        grid-template-columns: 1fr;
      }
      .gallery img {
        height: auto;
      }
    }
    @media (max-width: 480px) {
      h1 {
        font-size: 18px;
      }
      .btn, .link {
        padding: 6px 10px;
        font-size: 13px;
      }
      select, input[type=number] {
        padding: 6px;
        font-size: 14px;
      }
      .card img {
        height: 120px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <header>
      <div class="brand">
        <div class="logo">HA</div>
        <div>
          <h1>Horizon Auto</h1>
          <p class="lead">30+ quality cars — transparent pricing • easy financing • book a test drive</p>
        </div>
      </div>
      <nav>
        <a class="btn" href="#inventory">Inventory</a>
        <a class="link" href="#contact">Contact</a>
        <a class="link" id="view-faves">Saved</a>
      </nav>
    </header>

    <section class="controls">
      <div class="search">
        <input id="search" placeholder="Search by make, model, year..." />
        <button class="link" id="clear-search">Clear</button>
      </div>
      <div class="filters">
        <select id="filterMake"><option value="">All Makes</option></select>
        <select id="sortBy">
          <option value="newest">Newest</option>
          <option value="priceLow">Price: Low → High</option>
          <option value="priceHigh">Price: High → Low</option>
        </select>
        <button class="btn" id="resetFilters">Reset</button>
      </div>
    </section>

    <main style="display:grid;grid-template-columns:1fr 360px;gap:16px;align-items:start">
      <section id="inventory" class="grid"></section>

      <aside class="sidebar">
        <h3>Finance Calculator</h3>
        <label for="selectedCar">Select car</label>
        <select id="selectedCar"></select>
        <div class="calc-row">
          <div style="flex:1">
            <label>Down payment (ZAR)</label>
            <input id="down" type="number" value="50000" />
          </div>
        </div>
        <div class="calc-row">
          <div style="flex:1">
            <label>Interest rate (annual %)</label>
            <input id="interest" type="number" step="0.01" value="10.5" />
          </div>
          <div style="width:120px">
            <label>Term (years)</label>
            <select id="term">
              <option>1</option>
              <option>2</option>
              <option selected>3</option>
              <option>4</option>
              <option>5</option>
            </select>
          </div>
        </div>
        <div style="display:flex;gap:8px;margin-top:8px">
          <button class="btn" id="calc">Calculate</button>
          <button class="link" id="resetCalc">Reset</button>
        </div>
        <div class="result" id="monthly">Monthly: —</div>
        <div style="font-size:13px;color:var(--muted);margin-top:6px">
          Tip: Click "Calculate" on any vehicle card to load that vehicle's price into the calculator.
        </div>

        <hr style="border:none;border-top:1px solid rgba(255,255,255,0.03);margin:12px 0" />
        <h4>Quick contact</h4>
        <p style="color:var(--muted);font-size:13px">Call or WhatsApp to enquire or book a test drive.</p>
        <div style="display:flex;gap:8px;margin-top:8px">
          <a class="btn" href="tel:+27123456789">Call +27 12 345 6789</a>
          <a class="btn" href="https://wa.me/27123456789" target="_blank">WhatsApp</a>
        </div>
        <div style="margin-top:10px;font-size:13px;color:var(--muted)">
          Or <button class="link" id="bookTest">Book a test drive</button>
        </div>
      </aside>
    </main>

    <div style="height:18px"></div>

    <!-- modal -->
    <div class="modal-backdrop" id="modalBackdrop">
      <div class="modal" role="dialog" aria-modal="true">
        <div style="display:flex;justify-content:space-between;align-items:center">
          <div>
            <h2 id="modalTitle">Car Details</h2>
            <div style="color:var(--muted);font-size:13px" id="modalSub">Make • Model • Year</div>
          </div>
          <div><button class="close" id="closeModal">Close ✕</button></div>
        </div>
        <div class="modal-grid" style="margin-top:12px">
          <div>
            <div class="gallery"><img id="modalImage" src="" alt="car" /></div>
            <div style="display:flex;gap:8px;margin-top:8px" id="thumbs"></div>
            <div style="margin-top:10px;color:var(--muted)" id="modalDesc"></div>
          </div>
          <aside class="sidebar">
            <div><strong id="modalPrice"></strong></div>
            <div style="margin-top:8px" id="modalSpecs"></div>
            <div style="display:flex;gap:8px;margin-top:12px">
              <button class="btn" id="modalCalc">Load in Calculator</button>
              <a class="btn" id="modalBook">Book Test Drive</a>
            </div>
            <div style="margin-top:10px;color:var(--muted);font-size:13px">
              Contact: <a href="tel:+27123456789">+27 12 345 6789</a> • <a href="mailto:sales@horizonauto.example">sales@horizonauto.example</a>
            </div>
          </aside>
        </div>
      </div>
    </div>

    <section id="contact" style="margin-top:18px">
      <h3>Contact & Location</h3>
      <div style="display:flex;gap:12px;flex-wrap:wrap;align-items:flex-start">
        <div style="flex:1;min-width:280px;background:var(--glass);padding:12px;border-radius:10px">
          <p style="margin:0 0 8px">Horizon Auto<br/>3 Summit Road, Cape Town<br/>Open: Mon–Sat 8:30–17:00</p>
          <p style="margin:0">Phone: <a href="tel:+27123456789">+27 12 345 6789</a><br/>Email: <a href="mailto:sales@horizonauto.example">sales@horizonauto.example</a></p>
        </div>
        <div style="min-width:260px">
          <form id="contactForm" style="display:grid;gap:8px">
            <input name="name" placeholder="Your name" required />
            <input name="email" type="email" placeholder="Email" required />
            <input name="phone" placeholder="Phone or WhatsApp" />
            <textarea name="message" rows="3" placeholder="How can we help?"></textarea>
            <div style="display:flex;gap:8px">
              <button class="btn">Send (mailto)</button>
              <button type="button" class="link" id="resetContact">Reset</button>
            </div>
          </form>
        </div>
      </div>
    </section>

    <footer>
      <div>© Horizon Auto — Quality cars & fair finance</div>
      <div style="font-size:13px;color:var(--muted)">Made for demo — change texts & images as needed</div>
    </footer>
  </div>

  <script>
    // --- Data: 30 vehicles ---
    const cars = [
     
	 { id:1, make:'Toyota', model:'Corolla Cross', year:2023, price:389900, mileage:23000, trans:'Auto', fuel:'Petrol', img:'Toyota Corolla Cross.jpg', desc:'Reliable compact SUV with modern features.' },
   
   { id:2, make:'Volkswagen', model:'Golf GTI', year:2019, price:289900, mileage:54000, trans:'Manual', fuel:'Petrol', img:'Toyota Yaris Cross.jpg', desc:'Sporty hatchback — fun to drive.' },
    
	{ id:3, make:'BMW', model:'3 Series', year:2020, price:559900, mileage:42000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Luxury sedan with performance pedigree.' },
  
  { id:4, make:'Mercedes-Benz', model:'C200', year:2018, price:499900, mileage:65000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Comfortable executive car.' },
  
  { id:5, make:'Ford', model:'Ranger', year:2021, price:459900, mileage:41000, trans:'Auto', fuel:'Diesel', img:"Car insurance.jpg", desc:'Durable bakkie for work and play.' },
   
   { id:6, make:'Nissan', model:'X-Trail', year:2022, price:379900, mileage:31000, trans:'Auto', fuel:'Petrol', img:'Nissan X-Trail.jpg', desc:'Family-friendly 7-seater option.' },
   
   { id:7, make:'Hyundai', model:'i30', year:2020, price:219900, mileage:48000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Value-packed hatchback.' },
    
	{ id:8, make:'Kia', model:'Sportage', year:2019, price:249900, mileage:56000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Compact SUV with good economy.' },
   
   { id:9, make:'Audi', model:'A4', year:2021, price:429900, mileage:30000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Refined sedan with premium interior.' },
    
	{ id:10, make:'Mazda', model:'CX-5', year:2018, price:239900, mileage:75000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Stylish SUV with driving flair.' },
     
	 { id:11, make:'Toyota', model:'Hilux', year:2020, price:469900, mileage:52000, trans:'Auto', fuel:'Diesel', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Legendary reliability for work.' },
    
	{ id:12, make:'Suzuki', model:'Swift', year:2019, price:129900, mileage:68000, trans:'Manual', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Affordable, zippy city car.' },
     
	 { id:13, make:'Renault', model:'Duster', year:2017, price:129900, mileage:88000, trans:'Manual', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Rugged value SUV.' },
     
	 { id:14, make:'Honda', model:'Civic', year:2022, price:299900, mileage:19000, trans:'Auto', fuel:'Petrol', img:'Honda Civic.jpg', desc:'Modern compact sedan.' },
     
	 { id:15, make:'Mercedes-Benz', model:'A200', year:2021, price:389900, mileage:26000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Premium compact with style.' },
    
	{ id:16, make:'Chevrolet', model:'Trailblazer', year:2019, price:219900, mileage:60000, trans:'Auto', fuel:'Diesel', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Practical midsize SUV.' },
     
	 { id:17, make:'GWM', model:'P-Series', year:2022, price:329900, mileage:22000, trans:'Auto', fuel:'Diesel', img:'GWM P Series.jpg', desc:'Affordable bakkie with features.' },
     
	 { id:18, make:'Volvo', model:'XC40', year:2020, price:399900, mileage:41000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Safe and modern crossover.' },
    
	{ id:19, make:'Isuzu', model:'D-Max', year:2018, price:269900, mileage:80000, trans:'Manual', fuel:'Diesel', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Workhorse bakkie with towing.' },
    
	{ id:20, make:'Toyota', model:'C-HR', year:2021, price:289900, mileage:30000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Stylish hybrid-inspired SUV.' },
     
	 { id:21, make:'Ford', model:'EcoSport', year:2018, price:159900, mileage:82000, trans:'Auto', fuel:'Petrol', img:'Ford EcoSport.jpg', desc:'Compact and affordable.' },
     
	 { id:22, make:'Hyundai', model:'Tucson', year:2022, price:349900, mileage:25000, trans:'Auto', fuel:'Petrol', img:'Hyundai Tucson.jpg', desc:'Family SUV with features.' },
     
	 { id:23, make:'Kia', model:'Cerato', year:2020, price:189900, mileage:47000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Reliable compact sedan.' },
    
	{ id:24, make:'Audi', model:'Q3', year:2019, price:339900, mileage:55000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Compact premium SUV.' },
    
	{ id:25, make:'BMW', model:'X1', year:2018, price:319900, mileage:72000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Entry-level luxury SUV.' },
     
	 { id:26, make:'Mercedes-Benz', model:'GLA', year:2020, price:349900, mileage:48000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Compact premium crossover.' },
     
	 { id:27, make:'Toyota', model:'Yaris Cross', year:2023, price:249900, mileage:8000, trans:'Auto', fuel:'Hybrid', img:'Toyota Yaris Cross.jpg', desc:'Efficient small SUV (hybrid).'},
   
   { id:28, make:'Mini', model:'Cooper', year:2017, price:169900, mileage:92000, trans:'Manual', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Cute and fun city car.'},
    
	{ id:29, make:'Porsche', model:'Macan', year:2019, price:999900, mileage:47000, trans:'Auto', fuel:'Petrol', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Performance crossover — aspirational.'},
   
   { id:30, make:'Tesla', model:'Model 3', year:2021, price:699900, mileage:22000, trans:'Auto', fuel:'Electric', img:'https://images.pexels.com/photos/210019/pexels-photo-210019.jpeg', desc:'Electric sedan with autopilot features.'}
   
   ];

    // --- Build UI ---
    const inventory = document.getElementById('inventory');
    const selectedCar = document.getElementById('selectedCar');
    const filterMake = document.getElementById('filterMake');
    const sortBy = document.getElementById('sortBy');
    const searchInput = document.getElementById('search');

    function populateMakes() {
      const makes = Array.from(new Set(cars.map(c => c.make))).sort();
      makes.forEach(m => {
        const o = document.createElement('option');
        o.value = m;
        o.textContent = m;
        filterMake.appendChild(o);
      });
    }

    function renderList(list) {
      inventory.innerHTML = '';
      list.forEach(car => {
        const c = document.createElement('article');
        c.className = 'card';
        c.innerHTML = `
          <img src="${car.img}" alt="${car.make} ${car.model}" />
          <div class="meta">
            <div>
              <div class="title">${car.make} ${car.model} <span style="color:var(--muted);font-weight:600">• ${car.year}</span></div>
              <div class="specs">${car.mileage.toLocaleString()} km • ${car.trans} • ${car.fuel}</div>
            </div>
            <div class="price">R ${car.price.toLocaleString()}</div>
          </div>
          <div class="specs">${car.desc}</div>
          <div class="actions">
            <button class="link" data-id="${car.id}" onclick="openModal(${car.id})">View</button>
            <button class="btn" onclick="loadToCalc(${car.id})">Calculate</button>
            <button class="link" onclick="saveFav(${car.id})">♡ Save</button>
          </div>
        `;
        inventory.appendChild(c);
      });
    }

    function applyFilters() {
      let list = cars.slice();
      const q = searchInput.value.trim().toLowerCase();
      if (q) {
        list = list.filter(c => `${c.make} ${c.model} ${c.year}`.toLowerCase().includes(q));
      }
      const make = filterMake.value;
      if (make) {
        list = list.filter(c => c.make === make);
      }
      const sort = sortBy.value;
      if (sort === 'priceLow') list.sort((a,b) => a.price - b.price);
      else if (sort === 'priceHigh') list.sort((a,b) => b.price - a.price);
      else list.sort((a,b) => b.year - a.year);
      renderList(list);
      populateCarSelect(list);
    }

    function populateCarSelect(list) {
      selectedCar.innerHTML = '';
      const blank = document.createElement('option');
      blank.value = '';
      blank.textContent = 'Choose a vehicle';
      selectedCar.appendChild(blank);
      list.forEach(c => {
        const o = document.createElement('option');
        o.value = c.id;
        o.textContent = `${c.make} ${c.model} — R ${c.price.toLocaleString()}`;
        selectedCar.appendChild(o);
      });
    }

    // Modal & interactions
    const backdrop = document.getElementById('modalBackdrop');
    const modalTitle = document.getElementById('modalTitle');
    const modalImage = document.getElementById('modalImage');
    const modalSub = document.getElementById('modalSub');
    const modalDesc = document.getElementById('modalDesc');
    const modalPrice = document.getElementById('modalPrice');
    const modalSpecs = document.getElementById('modalSpecs');
    const thumbs = document.getElementById('thumbs');
    const modalCalc = document.getElementById('modalCalc');
    const modalBook = document.getElementById('modalBook');

    function openModal(id) {
      const car = cars.find(c => c.id === id);
      if (!car) return;
      modalTitle.textContent = `${car.make} ${car.model}`;
      modalSub.textContent = `${car.make} • ${car.model} • ${car.year}`;
      modalImage.src = car.img;
      modalDesc.textContent = car.desc;
      modalPrice.textContent = `R ${car.price.toLocaleString()}`;
      modalSpecs.innerHTML = `<div class="specs">${car.mileage.toLocaleString()} km • ${car.trans} • ${car.fuel}</div>`;
      thumbs.innerHTML = '';
      for (let i=1; i<=3; i++) {
        const im = document.createElement('img');
        im.src = car.img;
        im.style.width='32%'; im.style.height='60px'; im.style.objectFit='cover'; im.style.borderRadius='6px';
        im.style.cursor='pointer';
        im.onclick = () => { modalImage.src = im.src; };
        thumbs.appendChild(im);
      }
      modalCalc.onclick = () => { loadToCalc(car.id); backdrop.style.display = 'none'; };
      modalBook.href = `mailto:sales@horizonauto.example?subject=Test%20drive%20request%20for%20${encodeURIComponent(car.make+' '+car.model)}&body=Hello,%0AI'd%20like%20to%20book%20a%20test%20drive%20for%20${encodeURIComponent(car.make+' '+car.model)}%20(${car.year}).%0A%0ARegards,`;
      modalBook.target='_blank';
      backdrop.style.display='flex';
    }

    document.getElementById('closeModal').onclick = () => backdrop.style.display='none';
    backdrop.onclick = (e) => { if (e.target === backdrop) backdrop.style.display='none'; };

    // Calculator
    function loadToCalc(id) {
      const car = cars.find(c => c.id == id);
      if (!car) return;
      selectedCar.value = car.id;
      document.getElementById('down').value = Math.min(50000, Math.round(car.price * 0.1));
      document.getElementById('interest').value = 10.5;
      document.getElementById('term').value = 3;
      calcPayment();
      window.scrollTo({ top:0, behavior:'smooth' });
    }

    function calcPayment() {
      const carId = selectedCar.value;
      if (!carId) {
        document.getElementById('monthly').textContent = 'Monthly: — (choose a car)';
        return;
      }
      const car = cars.find(c => c.id == carId);
      const price = car.price;
      const down = Number(document.getElementById('down').value) || 0;
      const principal = Math.max(0, price - down);
      const annual = Number(document.getElementById('interest').value) || 0;
      const r = annual/100/12;
      const years = Number(document.getElementById('term').value);
      const n = years * 12;
      let monthly = 0;
      if (r === 0) monthly = principal / n;
      else monthly = principal * r / (1 - Math.pow(1+r, -n));
      document.getElementById('monthly').textContent = `Monthly: R ${monthly.toFixed(2).toLocaleString()}`.replace(/\B(?=(\d{3})+(?!\d))/g, ",");
    }

    // Favorites
    function saveFav(id) {
      const favs = JSON.parse(localStorage.getItem('horizon_favs')||'[]');
      if (!favs.includes(id)) favs.push(id);
      localStorage.setItem('horizon_favs', JSON.stringify(favs));
      alert('Saved to favorites');
    }

    // Contact form
    document.getElementById('contactForm').onsubmit = (e) => {
      e.preventDefault();
      const f = new FormData(e.target);
      const body = `Name: ${f.get('name')}%0AEmail: ${f.get('email')}%0APhone: ${f.get('phone')}%0A%0A${encodeURIComponent(f.get('message'))}`;
      window.location.href = `mailto:sales@horizonauto.example?subject=Website%20enquiry&body=${body}`;
    };

    document.getElementById('bookTest').onclick = () => {
      const subject = encodeURIComponent('General test drive request');
      window.location.href = `mailto:sales@horizonauto.example?subject=${subject}`;
    };

    document.getElementById('calc').onclick = calcPayment;
    document.getElementById('resetCalc').onclick = () => {
      document.getElementById('down').value=50000;
      document.getElementById('interest').value=10.5;
      document.getElementById('term').value=3;
      document.getElementById('monthly').textContent='Monthly: —';
    };

    document.getElementById('clear-search').onclick = () => {
      searchInput.value='';
      applyFilters();
    };
    document.getElementById('resetFilters').onclick = () => {
      filterMake.value=''; sortBy.value='newest'; searchInput.value='';
      applyFilters();
    };

    searchInput.addEventListener('input', applyFilters);
    filterMake.addEventListener('change', applyFilters);
    sortBy.addEventListener('change', applyFilters);

    // initial
    populateMakes();
    applyFilters();

    document.getElementById('view-faves').addEventListener('click', () => {
      const favs = JSON.parse(localStorage.getItem('horizon_favs')||'[]');
      if (favs.length === 0) return alert('No saved vehicles');
      const list = cars.filter(c => favs.includes(c.id));
      renderList(list);
    });

    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') backdrop.style.display='none';
    });

  </script>
</body>
</html>
