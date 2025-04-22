# ipl
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IPL History Hub | Complete Indian Premier League Chronicle</title>
    <style>
        :root {
            --primary: #2c3e50;
            --secondary: #e74c3c;
            --accent: #f39c12;
            --text: #333;
            --bg: #f9f9f9;
            --card-bg: #fff;
            --border: #e0e0e0;
        }

        .dark-mode {
            --primary: #3498db;
            --secondary: #e74c3c;
            --accent: #f1c40f;
            --text: #ecf0f1;
            --bg: #121212;
            --card-bg: #1e1e1e;
            --border: #333;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            transition: background-color 0.3s, color 0.3s;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: var(--text);
            background-color: var(--bg);
        }

        header {
            background-color: var(--primary);
            color: white;
            padding: 1.5rem 0;
            text-align: center;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            font-weight: 700;
        }

        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
        }

        nav {
            background-color: var(--primary);
            padding: 1rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        nav ul {
            display: flex;
            justify-content: center;
            list-style: none;
            flex-wrap: wrap;
        }

        nav li {
            margin: 0 15px;
        }

        nav a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            padding: 5px 10px;
            border-radius: 4px;
            transition: background-color 0.2s;
        }

        nav a:hover {
            background-color: rgba(255, 255, 255, 0.2);
        }

        .hero {
            height: 500px;
            background: linear-gradient(rgba(0, 0, 0, 0.6), rgba(0, 0, 0, 0.6)), url('https://resources.pulse.icc-cricket.com/ICC/photo/2023/03/31/4c1c9b7e-3e6a-4a9b-8a3b-8c5c5a5e5f5f/GettyImages-1248996753.jpg');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-align: center;
            margin-bottom: 2rem;
        }

        .hero-content {
            max-width: 800px;
            padding: 0 20px;
        }

        .hero h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 1.5rem;
        }

        .btn {
            display: inline-block;
            background-color: var(--secondary);
            color: white;
            padding: 10px 20px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: 600;
            transition: background-color 0.2s;
        }

        .btn:hover {
            background-color: #c0392b;
        }

        .section-title {
            text-align: center;
            margin: 3rem 0 2rem;
            font-size: 2rem;
            color: var(--secondary);
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background-color: var(--accent);
            margin: 10px auto;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .card {
            background-color: var(--card-bg);
            border-radius: 8px;
            overflow: hidden;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border: 1px solid var(--border);
        }

        .card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
        }

        .card-content {
            padding: 1.5rem;
        }

        .card h3 {
            margin-bottom: 0.5rem;
            color: var(--secondary);
        }

        .card p {
            margin-bottom: 1rem;
            color: var(--text);
        }

        .video-container {
            position: relative;
            padding-bottom: 56.25%;
            height: 0;
            overflow: hidden;
            margin-bottom: 2rem;
        }

        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            border: none;
        }

        .trophy-table {
            width: 100%;
            border-collapse: collapse;
            margin: 2rem 0;
        }

        .trophy-table th, .trophy-table td {
            padding: 12px 15px;
            text-align: left;
            border-bottom: 1px solid var(--border);
        }

        .trophy-table th {
            background-color: var(--primary);
            color: white;
        }

        .trophy-table tr:nth-child(even) {
            background-color: rgba(0, 0, 0, 0.05);
        }

        .dark-mode .trophy-table tr:nth-child(even) {
            background-color: rgba(255, 255, 255, 0.05);
        }

        .mode-toggle {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 10px 15px;
            border-radius: 50%;
            cursor: pointer;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
            z-index: 100;
        }

        footer {
            background-color: var(--primary);
            color: white;
            text-align: center;
            padding: 2rem 0;
            margin-top: 3rem;
        }

        @media (max-width: 768px) {
            h1 {
                font-size: 2rem;
            }
            
            .hero h2 {
                font-size: 1.8rem;
            }
            
            .grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <h1>IPL History Hub</h1>
            <p class="subtitle">The Complete Chronicle of Indian Premier League (2008 - 2025)</p>
        </div>
    </header>

    <nav>
        <ul>
            <li><a href="#overview">Overview</a></li>
            <li><a href="#champions">Champions</a></li>
            <li><a href="#highlights">Highlights</a></li>
            <li><a href="#records">Records</a></li>
            <li><a href="#teams">Teams</a></li>
        </ul>
    </nav>

    <section class="hero">
        <div class="hero-content">
            <h2>Relive the Glory of IPL</h2>
            <p>From the inaugural season in 2008 to the latest triumphs in 2025, explore the complete history of the world's most exciting cricket league.</p>
            <a href="#overview" class="btn">Explore IPL History</a>
        </div>
    </section>

    <div class="container">
        <section id="overview">
            <h2 class="section-title">IPL Overview</h2>
            <p>The Indian Premier League (IPL) is a professional Twenty20 cricket league established in 2008 by the Board of Control for Cricket in India (BCCI). It has grown to become the most-attended cricket league in the world and ranks sixth among all sports leagues.</p>
            
            <div class="video-container">
                <iframe width="560" height="315" src="https://www.youtube.com/embed/7E9G1bpQPb8" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
            </div>

            <h3>Basic Rules</h3>
            <div class="grid">
                <div class="card">
                    <div class="card-content">
                        <h3>Format</h3>
                        <p>IPL follows the Twenty20 format where each team faces a maximum of 20 overs. The team scoring the most runs wins.</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-content">
                        <h3>Player Auction</h3>
                        <p>Teams are built through an annual auction where franchises bid for players from around the world.</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-content">
                        <h3>Playoffs</h3>
                        <p>Top 4 teams qualify for playoffs consisting of Qualifiers and Eliminator leading to the Final.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="champions">
            <h2 class="section-title">IPL Champions</h2>
            <table class="trophy-table">
                <thead>
                    <tr>
                        <th>Year</th>
                        <th>Winner</th>
                        <th>Runner-up</th>
                        <th>Venue</th>
                        <th>Player of the Match</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>2008</td>
                        <td>Rajasthan Royals</td>
                        <td>Chennai Super Kings</td>
                        <td>DY Patil Stadium, Navi Mumbai</td>
                        <td>Yusuf Pathan (RR)</td>
                    </tr>
                    <tr>
                        <td>2009</td>
                        <td>Deccan Chargers</td>
                        <td>Royal Challengers Bangalore</td>
                        <td>Wanderers, Johannesburg</td>
                        <td>Anil Kumble (RCB)</td>
                    </tr>
                    <tr>
                        <td>2010</td>
                        <td>Chennai Super Kings</td>
                        <td>Mumbai Indians</td>
                        <td>DY Patil Stadium, Navi Mumbai</td>
                        <td>Suresh Raina (CSK)</td>
                    </tr>
                    <tr>
                        <td>2011</td>
                        <td>Chennai Super Kings</td>
                        <td>Royal Challengers Bangalore</td>
                        <td>M.A. Chidambaram Stadium, Chennai</td>
                        <td>Murali Vijay (CSK)</td>
                    </tr>
                    <tr>
                        <td>2012</td>
                        <td>Kolkata Knight Riders</td>
                        <td>Chennai Super Kings</td>
                        <td>M.A. Chidambaram Stadium, Chennai</td>
                        <td>Manvinder Bisla (KKR)</td>
                    </tr>
                    <tr>
                        <td>2013</td>
                        <td>Mumbai Indians</td>
                        <td>Chennai Super Kings</td>
                        <td>Eden Gardens, Kolkata</td>
                        <td>Kieron Pollard (MI)</td>
                    </tr>
                    <tr>
                        <td>2014</td>
                        <td>Kolkata Knight Riders</td>
                        <td>Kings XI Punjab</td>
                        <td>M. Chinnaswamy Stadium, Bangalore</td>
                        <td>Manish Pandey (KKR)</td>
                    </tr>
                    <tr>
                        <td>2015</td>
                        <td>Mumbai Indians</td>
                        <td>Chennai Super Kings</td>
                        <td>Eden Gardens, Kolkata</td>
                        <td>Rohit Sharma (MI)</td>
                    </tr>
                    <tr>
                        <td>2016</td>
                        <td>Sunrisers Hyderabad</td>
                        <td>Royal Challengers Bangalore</td>
                        <td>M. Chinnaswamy Stadium, Bangalore</td>
                        <td>Ben Cutting (SRH)</td>
                    </tr>
                    <tr>
                        <td>2017</td>
                        <td>Mumbai Indians</td>
                        <td>Rising Pune Supergiant</td>
                        <td>Rajiv Gandhi Stadium, Hyderabad</td>
                        <td>Krunal Pandya (MI)</td>
                    </tr>
                    <tr>
                        <td>2018</td>
                        <td>Chennai Super Kings</td>
                        <td>Sunrisers Hyderabad</td>
                        <td>Wankhede Stadium, Mumbai</td>
                        <td>Shane Watson (CSK)</td>
                    </tr>
                    <tr>
                        <td>2019</td>
                        <td>Mumbai Indians</td>
                        <td>Chennai Super Kings</td>
                        <td>Rajiv Gandhi Stadium, Hyderabad</td>
                        <td>Jasprit Bumrah (MI)</td>
                    </tr>
                    <tr>
                        <td>2020</td>
                        <td>Mumbai Indians</td>
                        <td>Delhi Capitals</td>
                        <td>Dubai International Stadium</td>
                        <td>Trent Boult (MI)</td>
                    </tr>
                    <tr>
                        <td>2021</td>
                        <td>Chennai Super Kings</td>
                        <td>Kolkata Knight Riders</td>
                        <td>Dubai International Stadium</td>
                        <td>Faf du Plessis (CSK)</td>
                    </tr>
                    <tr>
                        <td>2022</td>
                        <td>Gujarat Titans</td>
                        <td>Rajasthan Royals</td>
                        <td>Narendra Modi Stadium, Ahmedabad</td>
                        <td>Hardik Pandya (GT)</td>
                    </tr>
                    <tr>
                        <td>2023</td>
                        <td>Chennai Super Kings</td>
                        <td>Gujarat Titans</td>
                        <td>Narendra Modi Stadium, Ahmedabad</td>
                        <td>Devon Conway (CSK)</td>
                    </tr>
                    <tr>
                        <td>2024</td>
                        <td>Kolkata Knight Riders</td>
                        <td>Sunrisers Hyderabad</td>
                        <td>M.A. Chidambaram Stadium, Chennai</td>
                        <td>Mitchell Starc (KKR)</td>
                    </tr>
                    <tr>
                        <td>2025</td>
                        <td>TBD</td>
                        <td>TBD</td>
                        <td>TBD</td>
                        <td>TBD</td>
                    </tr>
                </tbody>
            </table>
        </section>

        <section id="highlights">
            <h2 class="section-title">Iconic Moments</h2>
            <div class="grid">
                <div class="card">
                    <img src="https://m.cricbuzz.com/a/img/v1/1920x1080/i1/c244891/ms-dhoni-led-csk-to-their.jpg" alt="CSK 2018 Victory">
                    <div class="card-content">
                        <h3>CSK's Fairytale Return (2018)</h3>
                        <p>After a 2-year suspension, Chennai Super Kings made a triumphant return by winning their 3rd IPL title.</p>
                    </div>
                </div>
                <div class="card">
                    <img src="https://img1.hscicdn.com/image/upload/f_auto/lsci/db/PICTURES/CMS/316300/316307.6.jpg" alt="MI 2019 Final">
                    <div class="card-content">
                        <h3>MI's 1-run Victory (2019)</h3>
                        <p>Mumbai Indians won by 1 run in the closest final ever against CSK, claiming their 4th title.</p>
                    </div>
                </div>
                <div class="card">
                    <img src="https://images.indianexpress.com/2022/05/GT-1.jpg" alt="GT 2022 Debut">
                    <div class="card-content">
                        <h3>GT's Dream Debut (2022)</h3>
                        <p>Gujarat Titans won the title in their inaugural season under Hardik Pandya's captaincy.</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="records">
            <h2 class="section-title">IPL Records</h2>
            <div class="grid">
                <div class="card">
                    <div class="card-content">
                        <h3>Most Runs</h3>
                        <p>Virat Kohli (RCB) - 7,263 runs</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-content">
                        <h3>Most Wickets</h3>
                        <p>Yuzvendra Chahal (RR) - 187 wickets</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-content">
                        <h3>Highest Individual Score</h3>
                        <p>Chris Gayle (RCB) - 175* (66 balls) vs PWI, 2013</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-content">
                        <h3>Most Titles</h3>
                        <p>Mumbai Indians - 5 titles (2013, 2015, 2017, 2019, 2020)</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-content">
                        <h3>Fastest Century</h3>
                        <p>Chris Gayle (RCB) - 30 balls vs PWI, 2013</p>
                    </div>
                </div>
                <div class="card">
                    <div class="card-content">
                        <h3>Best Bowling Figures</h3>
                        <p>Alzarri Joseph (MI) - 6/12 vs SRH, 2019</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="teams">
            <h2 class="section-title">IPL Teams</h2>
            <div class="grid">
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/2/2b/Chennai_Super_Kings_Logo.svg/1200px-Chennai_Super_Kings_Logo.svg.png" alt="CSK Logo">
                    <div class="card-content">
                        <h3>Chennai Super Kings</h3>
                        <p>5-time champions (2010, 2011, 2018, 2021, 2023)</p>
                        <a href="csk.html" class="btn">View Team History</a>
                    </div>
                </div>
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/c/cd/Mumbai_Indians_Logo.svg/1200px-Mumbai_Indians_Logo.svg.png" alt="MI Logo">
                    <div class="card-content">
                        <h3>Mumbai Indians</h3>
                        <p>5-time champions (2013, 2015, 2017, 2019, 2020)</p>
                        <a href="mi.html" class="btn">View Team History</a>
                    </div>
                </div>
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/4/4c/Kolkata_Knight_Riders_Logo.svg/1200px-Kolkata_Knight_Riders_Logo.svg.png" alt="KKR Logo">
                    <div class="card-content">
                        <h3>Kolkata Knight Riders</h3>
                        <p>3-time champions (2012, 2014, 2024)</p>
                        <a href="kkr.html" class="btn">View Team History</a>
                    </div>
                </div>
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/8/81/Sunrisers_Hyderabad.svg/1200px-Sunrisers_Hyderabad.svg.png" alt="SRH Logo">
                    <div class="card-content">
                        <h3>Sunrisers Hyderabad</h3>
                        <p>1-time champions (2016)</p>
                        <a href="srh.html" class="btn">View Team History</a>
                    </div>
                </div>
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/9/9a/Rajasthan_Royals_Logo.svg/1200px-Rajasthan_Royals_Logo.svg.png" alt="RR Logo">
                    <div class="card-content">
                        <h3>Rajasthan Royals</h3>
                        <p>1-time champions (2008)</p>
                        <a href="rr.html" class="btn">View Team History</a>
                    </div>
                </div>
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/4/42/Royal_Challengers_Bangalore_2020.svg/1200px-Royal_Challengers_Bangalore_2020.svg.png" alt="RCB Logo">
                    <div class="card-content">
                        <h3>Royal Challengers Bangalore</h3>
                        <p>3-time runners-up (2009, 2011, 2016)</p>
                        <a href="rcb.html" class="btn">View Team History</a>
                    </div>
                </div>
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/6/6b/Delhi_Capitals_Logo.svg/1200px-Delhi_Capitals_Logo.svg.png" alt="DC Logo">
                    <div class="card-content">
                        <h3>Delhi Capitals</h3>
                        <p>1-time runners-up (2020)</p>
                        <a href="dc.html" class="btn">View Team History</a>
                    </div>
                </div>
                <div class="card">
                    <img src="https://upload.wikimedia.org/wikipedia/en/thumb/0/09/Gujarat_Titans_Logo.svg/1200px-Gujarat_Titans_Logo.svg.png" alt="GT Logo">
                    <div class="card-content">
                        <h3>Gujarat Titans</h3>
                        <p>1-time champions (2022), 1-time runners-up (2023)</p>
                        <a href="gt.html" class="btn">View Team History</a>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <footer>
        <div class="container">
            <p>&copy; 2025 IPL History Hub. All rights reserved.</p>
            <p>This is an unofficial website and is not affiliated with the BCCI or IPL.</p>
        </div>
    </footer>

    <button class="mode-toggle" id="modeToggle">🌓</button>

    <script>
        const modeToggle = document.getElementById('modeToggle');
        
        modeToggle.addEventListener('click', () => {
            document.body.classList.toggle('dark-mode');
            
            if (document.body.classList.contains('dark-mode')) {
                localStorage.setItem('darkMode', 'enabled');
                modeToggle.textContent = '☀️';
            } else {
                localStorage.setItem('darkMode', 'disabled');
                modeToggle.textContent = '🌓';
            }
        });

        // Check for saved mode preference
        if (localStorage.getItem('darkMode') === 'enabled') {
            document.body.classList.add('dark-mode');
            modeToggle.textContent = '☀️';
        }
    </script>
</body>
</html>
