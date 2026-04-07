# gyangravbodhgaya
this is hotel booking Website in Bodhgaya
<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <title>Gyan Grav Bodhgaya | Bihar's #1 Secure Hotel Booking Portal</title>
    <meta name="description" content="Book 120+ best hotels and guest houses in Bodhgaya. Secure booking via WhatsApp. An initiative by Mr. Mukesh & Mr. Sunny.">
    <meta name="keywords" content="Bodhgaya Hotel Booking, Guest House Bodhgaya, Gyan Grav, Mahabodhi Temple Stay">
    
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        :root { --primary: #ee2a24; --dark: #1a1a1b; --grey: #5e5e5e; --bg: #f7f8fa; --gold: #ffb400; --safe-green: #32ae5f; }
        * { box-sizing: border-box; transition: all 0.3s ease; margin: 0; padding: 0; }
        body { font-family: 'Inter', 'Segoe UI', sans-serif; background: var(--bg); color: #222; overflow-x: hidden; }

        /* --- Header --- */
        header { background: #fff; padding: 15px 6%; display: flex; justify-content: space-between; align-items: center; box-shadow: 0 2px 15px rgba(0,0,0,0.08); position: sticky; top: 0; z-index: 1000; }
        .brand { display: flex; align-items: center; gap: 12px; cursor: pointer; text-decoration: none; }
        .logo-sq { background: var(--primary); color: #fff; width: 45px; height: 45px; display: flex; align-items: center; justify-content: center; border-radius: 10px; font-weight: 900; font-size: 22px; box-shadow: 0 4px 10px rgba(238,42,36,0.3); }
        .brand-name { font-size: 22px; font-weight: 800; color: var(--dark); letter-spacing: -0.5px; }
        
        .nav-right { display: flex; align-items: center; gap: 20px; }
        .user-profile { display: none; align-items: center; gap: 10px; font-weight: 600; color: var(--primary); }
        .login-btn { background: var(--dark); color: #fff; padding: 10px 22px; border-radius: 8px; text-decoration: none; font-weight: 600; cursor: pointer; border: none; font-size: 14px; }
        .logout-link { display: none; font-size: 12px; color: var(--grey); cursor: pointer; text-decoration: underline; margin-left: 10px; }

        /* --- Hero Section --- */
        .hero { background: linear-gradient(rgba(0,0,0,0.6), rgba(0,0,0,0.6)), url('https://images.unsplash.com/photo-1544644181-1484b3fdfc62?auto=format&fit=crop&w=1500&q=80'); background-size: cover; background-position: center; padding: 100px 20px 80px; text-align: center; color: #fff; }
        .hero h1 { font-size: 48px; font-weight: 900; text-shadow: 0 4px 10px rgba(0,0,0,0.3); }
        .hero p { font-size: 18px; margin: 15px 0 25px; opacity: 0.9; }
        
        /* Security Badge */
        .secure-badge { background: rgba(50, 174, 95, 0.2); border: 1px solid var(--safe-green); color: var(--safe-green); padding: 5px 15px; border-radius: 20px; font-size: 12px; display: inline-flex; align-items: center; gap: 5px; margin-bottom: 20px; font-weight: bold; }

        /* --- Search & Filters --- */
        .search-container { max-width: 800px; margin: -40px auto 40px; background: #fff; padding: 10px; border-radius: 50px; display: flex; box-shadow: 0 10px 30px rgba(0,0,0,0.15); border: 1px solid #eee; }
        .search-container input { flex: 1; border: none; padding: 15px 25px; outline: none; font-size: 16px; border-radius: 50px; }
        .search-container button { background: var(--primary); color: #fff; border: none; padding: 0 35px; border-radius: 50px; font-weight: 700; cursor: pointer; }
        
        .filter-bar { display: flex; justify-content: center; gap: 15px; margin-bottom: 40px; padding: 0 20px; flex-wrap: wrap; }
        .filter-chip { padding: 10px 25px; background: #fff; border: 1.5px solid #ddd; border-radius: 30px; cursor: pointer; font-weight: 600; font-size: 14px; transition: 0.3s; }
        .filter-chip.active { background: var(--primary); border-color: var(--primary); color: #fff; box-shadow: 0 5px 15px rgba(238,42,36,0.3); }
        .filter-chip:hover:not(.active) { border-color: var(--primary); color: var(--primary); }

        /* --- Listings Grid --- */
        .main-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(290px, 1fr)); gap: 30px; padding: 0 6% 60px; max-width: 1400px; margin: auto; }
        .hotel-card { background: #fff; border-radius: 20px; overflow: hidden; box-shadow: 0 5px 20px rgba(0,0,0,0.04); position: relative; border: 1px solid #f0f0f0; transition: 0.4s; }
        .hotel-card:hover { transform: translateY(-10px); box-shadow: 0 15px 40px rgba(0,0,0,0.12); }
        
        .card-img-box { height: 200px; position: relative; overflow: hidden; }
        .card-img-box img { width: 100%; height: 100%; object-fit: cover; transition: 1s; }
        .hotel-card:hover .card-img-box img { scale: 1.1; }
        .tag { position: absolute; top: 15px; left: 15px; background: var(--primary); color: #fff; padding: 5px 12px; border-radius: 6px; font-size: 11px; font-weight: 800; text-transform: uppercase; z-index: 10; }
        .tag.guest { background: var(--dark); }

        .card-content { padding: 20px; }
        .card-meta { display: flex; justify-content: space-between; align-items: center; margin-bottom: 10px; }
        .stars { color: var(--gold); font-size: 12px; }
        .card-title { font-size: 17px; font-weight: 700; color: var(--dark); margin: 0 0 12px; height: 42px; overflow: hidden; line-height: 1.3; }
        .price-row { display: flex; align-items: baseline; gap: 8px; }
        .current-price { font-size: 22px; font-weight: 800; color: var(--dark); }
        .old-price { text-decoration: line-through; color: var(--grey); font-size: 14px; }
        .book-btn-small { width: 100%; background: var(--primary); color: #fff; border: none; padding: 12px; border-radius: 12px; font-weight: 700; margin-top: 15px; cursor: pointer; font-size: 14px; transition: 0.3s; }
        .book-btn-small:hover { background: #d0201d; }

        /* --- Founders Section --- */
        #founders-area { background: #fff; padding: 80px 6%; text-align: center; border-top: 1px solid #eee; }
        .founder-wrap { display: flex; justify-content: center; gap: 40px; flex-wrap: wrap; margin-top: 40px; }
        .f-card { width: 280px; padding: 30px; background: var(--bg); border-radius: 25px; text-align: center; border: 1px solid #eee; transition: 0.3s; }
        .f-card:hover { border-color: var(--accent); transform: translateY(-5px); }
        .f-card img { width: 130px; height: 130px; border-radius: 50%; border: 6px solid #fff; box-shadow: 0 10px 20px rgba(0,0,0,0.1); margin-bottom: 15px; object-fit: cover; }
        .f-card h3 { margin: 10px 0 5px; color: var(--dark); font-size: 20px; }
        .f-card p { color: var(--primary); font-weight: 700; font-size: 13px; text-transform: uppercase; letter-spacing: 1px; }

        /* --- Modals --- */
        .overlay { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.85); backdrop-filter: blur(8px); z-index: 2000; align-items: center; justify-content: center; padding: 20px; }
        .modal { background: #fff; width: 100%; max-width: 400px; padding: 40px; border-radius: 25px; position: relative; animation: pop 0.4s ease; }
        @keyframes pop { from { opacity: 0; scale: 0.8; } to { opacity: 1; scale: 1; } }
        .modal h2 { margin-bottom: 10px; font-size: 24px; color: var(--dark); }
        .modal input { width: 100%; padding: 15px; margin: 10px 0; border: 1px solid #eee; border-radius: 12px; background: #f9f9f9; outline: none; font-size: 15px; }
        .modal input:focus { border-color: var(--primary); background: #fff; }
        .close-btn { position: absolute; top: 20px; right: 25px; font-size: 24px; cursor: pointer; color: #ccc; transition: 0.3s; }
        .close-btn:hover { color: var(--primary); }

        /* --- Footer --- */
        footer { background: var(--dark); color: #bbb; padding: 60px 6% 30px; text-align: center; font-size: 14px; }
        .contact-pill { display: inline-flex; gap: 20px; background: #2a2a2b; padding: 15px 30px; border-radius: 50px; color: #fff; margin-bottom: 30px; font-size: 14px; flex-wrap: wrap; justify-content: center; }
        .footer-logo { font-size: 20px; font-weight: 800; color: #fff; margin-bottom: 15px; display: block; }
        
        /* Mobile Adjustments */
        @media (max-width: 768px) {
            .hero h1 { font-size: 32px; }
            .hero p { font-size: 16px; }
            .brand-name { font-size: 18px; }
            .main-grid { grid-template-columns: repeat(auto-fill, minmax(250px, 1fr)); padding: 0 4% 40px; }
            .founder-wrap { gap: 20px; }
            header { padding: 10px 4%; }
        }
    </style>
</head>
<body>

<header>
    <a href="#" class="brand">
        <div class="logo-sq">GG</div>
        <div class="brand-name">GYAN GRAV <span style="color:var(--primary)">BODHGAYA</span></div>
    </a>
    <div class="nav-right">
        <div id="userGreeting" class="user-profile">
            <i class="fas fa-user-circle" style="font-size: 20px;"></i> <span id="uDisplayName"></span>
            <span class="logout-link" onclick="logout()">Logout</span>
        </div>
        <button id="mainLoginBtn" class="login-btn" onclick="openModal('loginModal')">Login / Signup</button>
    </div>
</header>

<section class="hero">
    <div class="secure-badge"><i class="fas fa-shield-alt"></i> SSL Secured Booking Partner</div>
    <h1>Discover Bodhgaya's Best</h1>
    <p>Handpicked Stays curated by Mr. Mukesh & Mr. Sunny</p>
</section>

<div class="search-container">
    <i class="fas fa-search" style="margin-left:20px; color:#aaa; font-size: 18px;"></i>
    <input type="text" id="mainSearch" onkeyup="liveSearch()" placeholder="Search from 120+ authentic stays...">
    <button onclick="liveSearch()">Search</button>
</div>

<div class="filter-bar">
    <div class="filter-chip active" onclick="applyFilter('all', this)">All Stays</div>
    <div class="filter-chip" onclick="applyFilter('hotel', this)">Luxury Hotels</div>
    <div class="filter-chip" onclick="applyFilter('guest', this)">Budget Guest Houses</div>
</div>

<div class="main-grid" id="listingGrid">
    </div>

<section id="founders-area">
    <h2 style="font-size: 32px; font-weight: 800; color: var(--dark);">Meet The Visionaries</h2>
    <p style="color:var(--grey); max-width: 600px; margin: 10px auto 40px; line-height: 1.6;">"Gyan Grav Bodhgaya is driven by a passion to redefine hospitality in Bihar. We ensure trust, security, and unparalleled service."</p>
    <div class="founder-wrap">
        <div class="f-card">
            <img src="https://api.dicebear.com/8.x/avataaars/svg?seed=Mukesh&backgroundColor=b6e3f4" alt="Mr. Mukesh">
            <h3>Mr. Mukesh</h3>
            <p>Founder & CEO</p>
        </div>
        <div class="f-card">
            <img src="https://api.dicebear.com/8.x/avataaars/svg?seed=Sunny&backgroundColor=ffdfbf" alt="Mr. Sunny">
            <h3>Mr. Sunny</h3>
            <p>Co-Founder & COO</p>
        </div>
    </div>
</section>

<div class="overlay" id="loginModal">
    <div class="modal">
        <span class="close-btn" onclick="closeModal('loginModal')">&times;</span>
        <h2>Welcome to Gyan Grav</h2>
        <p style="color:var(--grey); font-size:14px; margin-bottom:25px;">Login securely to access exclusive rates and quick WhatsApp booking.</p>
        <input type="text" id="uNameInput" placeholder="Aapka Poora Naam (Full Name)">
        <input type="tel" id="uPhoneInput" placeholder="WhatsApp Number (10 Digit)">
        <button class="book-btn-small" style="padding:15px; font-size:16px;" onclick="doLogin()">Login Securely</button>
    </div>
</div>

<div class="overlay" id="bookModal">
    <div class="modal">
        <span class="close-btn" onclick="closeModal('bookModal')">&times;</span>
        <h3 id="targetHotel" style="margin-top:0; color:var(--primary); font-size: 20px;"></h3>
        <p style="font-size:14px; color:var(--grey); margin: 15px 0 5px;">Kripya Check-in ki taarikh chunein:</p>
        <input type="date" id="bookDateInput">
        <button class="book-now book-btn-small" style="font-size:16px;" onclick="finalWhatsApp()">Confirm Booking via WhatsApp</button>
        <div style="margin-top:15px; font-size:12px; color:var(--safe-green); text-align:center; font-weight: bold;">
            <i class="fas fa-lock"></i> End-to-End Encrypted via WhatsApp
        </div>
    </div>
</div>

<footer>
    <span class="footer-logo">GYAN GRAV <span style="color:var(--primary)">BODHGAYA</span></span>
    <div class="contact-pill">
        <span><i class="fab fa-whatsapp" style="color:#25D366"></i> +91 6207860869</span>
        <span><i class="far fa-envelope"></i> nahkuchbhi@gmail.com</span>
    </div>
    <div style="margin-bottom:25px; display:flex; justify-content:center; gap:25px; font-size:20px; color: #fff;">
        <i class="fab fa-facebook-f" style="cursor:pointer"></i> <i class="fab fa-instagram" style="cursor:pointer"></i> <i class="fab fa-linkedin-in" style="cursor:pointer"></i>
    </div>
    <p>© 2026 GYAN GRAV BODHGAYA. All Rights Reserved.</p>
    <p style="font-size: 12px; margin-top: 5px;">An Initiative by Mr. Mukesh & Mr. Sunny.</p>
</footer>

<script>
    // --- WHATSAPP CONFIG ---
    const WHATSAPP_NUMBER = "916207860869";

    // --- PROPERTY MASTER DATABASE (Realistic Images & Details) ---
    const rawHotels = [
        "Hyatt Regency Bodhgaya", "Marasa Sarovar Premiere", "The Royal Residency", "Maha Bodhi Hotel & Resort", "Hotel Lotus Nikko", "Hotel Tokyo Vihar", "Hotel Taj Darbar", "Oaks Bodhgaya", "Dhamma Grand Hotel", "Hotel Sujata", "Sambodhi Retreat", "Maya Heritage", "Hotel Buddha International", "Hotel Galaxy Intercontinental", "Hotel Delta International", "Hotel Deep", "Bodhi Residency", "Hotel Inaka", "Hotel Niranjana", "Hotel Kirti", "Hotel Siddhartha", "Hotel Mahamaya", "Hotel Vaishali", "Hotel Ananda", "Hotel Sakura", "Om International", "Hotel Imperial", "Rajgir Heritage", "Hotel Gautam", "Shanti Buddha", "Hotel Bodh Vilas", "Crystal", "Bodh Enclave", "Bodhi Tree", "Zen", "Asian", "Metta Residency", "Bodh View", "Royal Guest House", "Sun City", "Hotel Moon", "Hotel Star", "Bodhi Palace", "Hotel Grace", "Diamond", "Holiday", "City", "Relax", "Grand Plaza", "Landmark", "Elite", "Blue Diamond", "Red Velvet", "White Lotus", "Green Park", "Platinum", "Roseman", "Prince", "Seven Inn", "Crystal Palace", "Sun", "Gold", "Silver", "Diamond Palace", "Mahaprajnaparamita", "Gautam Palace", "Nirvana Stay", "Peace Inn", "Bodhgaya Residency"
    ];

    const rawGuests = [
        "Shanti Guest House", "Kundan Bazar Guest House", "Rahul Guest House", "Beauty Guest House", "Bodhgaya Guest House", "Om Guest House", "Deepak Guest House", "Sujata Guest House", "Laxmi Guest House", "Krishna Guest House", "Buddha Guest House", "Mahavir Guest House", "Gautam Guest House", "Ashoka Guest House", "Maitri Guest House", "Vishwa Guest House", "Anjali Guest House", "Raja Guest House", "Rani Guest House", "Prince Guest House", "Peace Guest House", "Happy Guest House", "Welcome Guest House", "Friendship Guest House", "Home Stay Bodhgaya", "Village Guest House", "Nisha Guest House", "Aasha Guest House", "Pooja Guest House", "Maya Guest House", "Tara Guest House", "Sunil Guest House", "Vinay Guest House", "Raj Guest House", "Aryan Guest House", "Kabir Guest House", "Meera Guest House", "Sagar Guest House", "Aakash Guest House", "Suraj Guest House", "Chanda Guest House", "Sitara Guest House", "Ganga Guest House", "Yamuna Guest House", "Saraswati Guest House", "Narmada Guest House", "Kaveri Guest House", "Godavari Guest House", "Indus Guest House", "Brahmaputra Guest House", "Sangam House"
    ];

    // Image libraries (Bodhgaya compatible)
    const hotelImgs = [
        "https://images.unsplash.com/photo-1566073771259-6a8506099945?auto=format&fit=crop&w=500&q=60", // Luxury Room
        "https://images.unsplash.com/photo-1582719478250-c89cae4dc85b?auto=format&fit=crop&w=500&q=60", // Modern Hotel
        "https://images.unsplash.com/photo-1542314831-068cd1dbfeeb?auto=format&fit=crop&w=500&q=60", // Premium
        "https://images.unsplash.com/photo-1571896349842-33c89424de2d?auto=format&fit=crop&w=500&q=60"  // View
    ];
    const guestImgs = [
        "https://images.unsplash.com/photo-1618773928121-c32242e63f39?auto=format&fit=crop&w=500&q=60", // Homestay
        "https://images.unsplash.com/photo-1520250497591-112f2f40a3f4?auto=format&fit=crop&w=500&q=60", // Cozy
        "https://images.unsplash.com/photo-1598928506311-c55ded91a20c?auto=format&fit=crop&w=500&q=60"  // Standard
    ];

    let masterData = [];

    function buildDatabase() {
        rawHotels.forEach((n, i) => {
            masterData.push({
                name: n,
                type: 'hotel',
                price: 2500 + (Math.floor(Math.random() * 5500)), // Real prices 2500 - 8000
                stars: 4 + (Math.floor(Math.random() * 2)), // 4-5 stars
                img: hotelImgs[i % hotelImgs.length]
            });
        });
        rawGuests.forEach((n, i) => {
            masterData.push({
                name: n,
                type: 'guest',
                price: 600 + (Math.floor(Math.random() * 1200)), // Real prices 600 - 1800
                stars: 2 + (Math.floor(Math.random() * 2)), // 2-3 stars
                img: guestImgs[i % guestImgs.length]
            });
        });
    }

    // --- CORE RENDERING LOGIC ---
    const grid = document.getElementById('listingGrid');

    function renderListings(data) {
        grid.innerHTML = "";
        if(data.length === 0) {
            grid.innerHTML = `<div style="grid-column: 1/-1; text-align:center; padding: 50px; color:var(--grey); font-weight: bold;">No results found. Try another search.</div>`;
            return;
        }
        data.forEach(item => {
            const card = document.createElement('div');
            card.className = "hotel-card";
            card.innerHTML = `
                <div class="card-img-box">
                    <div class="tag ${item.type}">${item.type === 'hotel' ? 'Hotel' : 'Guest House'}</div>
                    <img src="${item.img}" alt="${item.name}" loading="lazy">
                </div>
                <div class="card-content">
                    <div class="card-meta">
                        <div class="stars">${'<i class="fas fa-star"></i>'.repeat(item.stars)}</div>
                        <div style="font-size:11px; color:var(--safe-green); font-weight:bold;"><i class="fas fa-check-circle"></i> Gyan Grav Verified</div>
                    </div>
                    <h3 class="card-title">${item.name}</h3>
                    <div class="price-row">
                        <span class="current-price">₹${item.price.toLocaleString('en-IN')}</span>
                        <span class="old-price">₹${(item.price + 700).toLocaleString('en-IN')}</span>
                    </div>
                    <button class="book-btn-small" onclick="handleBookingTrigger('${item.name}')">Book Now via WhatsApp</button>
                </div>
            `;
            grid.appendChild(card);
        });
    }

    // --- INTERACTION LOGIC ---
    function liveSearch() {
        const val = document.getElementById('mainSearch').value.toLowerCase().trim();
        const filtered = masterData.filter(h => h.name.toLowerCase().includes(val));
        renderListings(filtered);
    }

    function applyFilter(type, el) {
        document.querySelectorAll('.filter-chip').forEach(c => c.classList.remove('active'));
        el.classList.add('active');
        if(type === 'all') renderListings(masterData);
        else renderListings(masterData.filter(d => d.type === type));
    }

    // --- AUTH/LOGIN LOGIC (Odoo compatible local storage) ---
    function doLogin() {
        const n = document.getElementById('uNameInput').value.trim();
        const p = document.getElementById('uPhoneInput').value.trim();
        if(n && p.length === 10 && !isNaN(p)) {
            localStorage.setItem('gyanName', n);
            localStorage.setItem('gyanPhone', p);
            closeModal('loginModal');
            updateUserUI();
            alert("Swagat hai " + n + "! Aapki Gyan Grav secure session active hai.");
        } else {
            alert("Security Alert: Kripya sahi naam aur 10-digit ka number bharein.");
        }
    }

    function updateUserUI() {
        const n = localStorage.getItem('gyanName');
        if(n) {
            document.getElementById('mainLoginBtn').style.display = "none";
            document.getElementById('userGreeting').style.display = "flex";
            document.getElementById('uDisplayName').innerText = n;
            document.querySelector('.logout-link').style.display = "inline";
        }
    }

    function logout() {
        localStorage.clear();
        location.reload();
    }

    // --- BOOKING LOGIC ---
    let activeHotel = "";
    function handleBookingTrigger(name) {
        if(!localStorage.getItem('gyanName')) {
            alert("Security Check: Booking aage badhane ke liye kripya Login karein.");
            openModal('loginModal');
        } else {
            activeHotel = name;
            document.getElementById('targetHotel').innerText = "Booking: " + name;
            openModal('bookModal');
        }
    }

    function finalWhatsApp() {
        const date = document.getElementById('bookDateInput').value;
        if(!date) return alert("Security Alert: Kripya Check-in ki taarikh chunein.");
        
        const n = localStorage.getItem('gyanName');
        const p = localStorage.getItem('gyanPhone');
        
        // Message structure (Clean & Professional)
        const text = `*GYAN GRAV SECURE BOOKING REQUEST*%0A------------------------%0A*Hotel:* ${activeHotel}%0A*Client Name:* ${n}%0A*WhatsApp:* ${p}%0A*Check-in Date:* ${date}%0A------------------------%0A_Sent via GYAN GRAV BODHGAYA Portal_`;
        
        // Final secure WhatsApp trigger
        window.open(`https://wa.me/${WHATSAPP_NUMBER}?text=${text}`);
    }

    // --- UI HELPER FUNCTIONS ---
    function openModal(id) { 
        document.getElementById(id).style.display = 'flex'; 
        document.body.style.overflow = 'hidden'; // Prevents background scroll
    }
    function closeModal(id) { 
        document.getElementById(id).style.display = 'none'; 
        document.body.style.overflow = 'auto'; // Re-enables scroll
    }

    // --- STARTUP SEQUENCE ---
    buildDatabase();
    renderListings(masterData);
    updateUserUI();
</script>

</body>
</html>
