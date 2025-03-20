<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Twenty's Auto Body</title>
  <style>
    /* RESET MARGINS & PADDING */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    /* BODY BACKGROUND */
    body {
      font-family: Arial, sans-serif;
      background-color: #10182b; /* Dark blue background across the whole page */
    }

    /* HEADER */
    header {
      padding: 20px;
      text-align: center;
      background-color: #10182b;
    }
    header h1 {
      color: #fff;
      font-size: 24px;
    }

    /* MAIN CONTENT: 4 COLUMNS ON A WIDER BLUE BACKGROUND */
    .main-content {
      max-width: 1800px; /* Ensures columns fit comfortably */
      margin: 0 auto;
      padding: 40px;
      display: flex;
      flex-wrap: wrap;  /* Wrap columns on smaller screens */
      justify-content: center;
      background-color: #10182b; /* Keep the dark blue background behind columns */
      gap: 20px; /* space between columns */
    }

    /* BASE COLUMN STYLES */
    .column {
      background-color: #e3e9f2;
      border-radius: 5px;
      padding: 15px;
      margin: 10px;
      min-height: 400px;
    }

    /* CUSTOM WIDTHS PER COLUMN */
    .cosmetics-column {
      width: 540px; /* Wide enough for 5 columns of cosmetic buttons */
    }
    .performance-column {
      width: 300px;
    }
    .respray-column {
      width: 250px;
    }
    .lighting-column {
      width: 250px;
    }

    /* HEADINGS INSIDE COLUMNS */
    .column h2 {
      text-align: center;
      color: #000;
      margin-bottom: 10px;
      font-size: 1.2rem;
    }

    /* COSMETICS GRID (5 columns, 5 rows) */
    .cosmetics-grid {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      gap: 10px;
    }

    /* PERFORMANCE GRID WITH SUBHEADINGS FOR EACH CATEGORY */
    .performance-category {
      margin-bottom: 20px;
    }
    .performance-category h3 {
      margin-bottom: 8px;
      color: #000;
      font-size: 1rem;
      text-align: center;
    }
    .levels {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      gap: 10px;
    }
    /* For categories with fewer levels, we can adjust columns. We'll just define them individually. */

    /* SIMPLE GRID FOR RESPRAY & LIGHTING BUTTONS */
    .button-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 10px;
    }

    /* BUTTON STYLES */
    .upgrade-btn {
      background-color: #fff;
      color: #000;
      border: 1px solid #ccc;
      border-radius: 5px;
      padding: 8px;
      text-align: center;
      cursor: pointer;
      font-size: 0.85rem;
      line-height: 1.2;
    }
    .upgrade-btn:hover {
      background-color: #e2e2e2;
    }

    /* SELECTED UPGRADES & TOTAL SECTION */
    #total-section {
      text-align: center;
      background-color: #f0f3f9;
      padding: 20px;
    }
    #total-section h2 {
      color: #000;
      margin-bottom: 10px;
    }
    #selected-upgrades {
      list-style: none;
      margin: 10px auto;
      padding-left: 0;
      max-width: 600px;
      max-height: 150px;
      overflow-y: auto;
    }
    #selected-upgrades li {
      background: #e3e9f2;
      margin: 5px 0;
      padding: 5px;
      border-radius: 3px;
      cursor: pointer;
      color: #000;
    }
    #selected-upgrades li:hover {
      background: #d1d8e2;
    }
    #total-price {
      font-size: 1.2rem;
      color: #000;
      margin-left: 5px;
    }
    .reset-btn {
      margin-top: 10px;
      padding: 8px 16px;
      background: #ccc;
      border: none;
      border-radius: 3px;
      cursor: pointer;
    }
    .reset-btn:hover {
      background: #bbb;
    }

    /* FORM & SUMMARY SECTION */
    .form-section {
      background-color: #f0f3f9;
      padding: 20px;
      text-align: center;
    }
    .form-section h2 {
      color: #000;
      margin-bottom: 10px;
    }
    .form-row {
      margin-bottom: 10px;
    }
    .form-row label {
      display: inline-block;
      width: 150px;
      text-align: right;
      margin-right: 5px;
      color: #000;
    }
    .form-row input {
      width: 200px;
      padding: 5px;
      border: 1px solid #999;
      border-radius: 3px;
    }
    .generate-btn {
      margin-top: 10px;
      padding: 8px 16px;
      background: #007bff;
      border: none;
      border-radius: 3px;
      cursor: pointer;
      color: #fff;
      font-size: 1rem;
    }
    .generate-btn:hover {
      background: #0056c1;
    }
    #summaryOutput {
      margin-top: 15px;
      white-space: pre-wrap;
      background: #e3e9f2;
      padding: 10px;
      border-radius: 5px;
      border: 1px solid #ccc;
      max-width: 600px;
      margin: 15px auto 0;
      color: #000;
      text-align: left;
    }
  </style>
</head>
<body>

  <header>
    <h1>Twenty's Auto Body</h1>
  </header>

  <!-- MAIN 4-COLUMN LAYOUT -->
  <div class="main-content">

    <!-- COSMETICS COLUMN -->
    <div class="column cosmetics-column">
      <h2>Cosmetics</h2>
      <!-- All cosmetics = $400 + $100 fee = $500 each (from last image) -->
      <div class="cosmetics-grid">
        <div class="upgrade-btn" onclick="addUpgrade('Aerial', 500)">Aerial<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Air Filter', 500)">Air Filter<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Door Speaker', 500)">Door Speaker<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Custom Trim', 500)">Custom Trim<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Dashboard', 500)">Dashboard<br>$500</div>

        <div class="upgrade-btn" onclick="addUpgrade('Engine Block', 500)">Engine Block<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Exhaust', 500)">Exhaust<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Grille', 500)">Grille<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Hood', 500)">Hood<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Horn', 500)">Horn<br>$500</div>

        <div class="upgrade-btn" onclick="addUpgrade('Lights', 500)">Lights<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Mirrors', 500)">Mirrors<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Ornaments', 500)">Ornaments<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Plate', 500)">Plate<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Rear Bumper', 500)">Rear Bumper<br>$500</div>

        <div class="upgrade-btn" onclick="addUpgrade('Roof', 500)">Roof<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Seat', 500)">Seat<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Shift Knob', 500)">Shift Knob<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Speaker', 500)">Speaker<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Spoiler', 500)">Spoiler<br>$500</div>

        <div class="upgrade-btn" onclick="addUpgrade('Sun Strip', 500)">Sun Strip<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Vanity Plate', 500)">Vanity Plate<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Window Tints', 500)">Window Tints<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Side Skirts', 500)">Side Skirts<br>$500</div>
        <div class="upgrade-btn" onclick="addUpgrade('Sill', 500)">Sill<br>$500</div>
      </div>
    </div><!-- end COSMETICS column -->

    <!-- PERFORMANCE COLUMN -->
    <div class="column performance-column">
      <h2>Performance</h2>

      <!-- ENGINE (5 levels: L1-L4 from first screenshot, L5 from last image if higher) -->
      <div class="performance-category">
        <h3>Engine Upgrades</h3>
        <div class="levels" style="grid-template-columns: repeat(5, 1fr);">
          <!-- From the first screenshot: L1=$2000, L2=$3250, L3=$6500, L4=$9450; last image is higher => L5=$14250 -->
          <div class="upgrade-btn" onclick="addUpgrade('Engine Level 1', 2000)">Lvl 1<br>$2,000</div>
          <div class="upgrade-btn" onclick="addUpgrade('Engine Level 2', 3250)">Lvl 2<br>$3,250</div>
          <div class="upgrade-btn" onclick="addUpgrade('Engine Level 3', 6500)">Lvl 3<br>$6,500</div>
          <div class="upgrade-btn" onclick="addUpgrade('Engine Level 4', 9450)">Lvl 4<br>$9,450</div>
          <div class="upgrade-btn" onclick="addUpgrade('Engine Level 5', 14250)">Lvl 5<br>$14,250</div>
        </div>
      </div>

      <!-- ARMOR (5 levels: L1-L4 from screenshot, L5 from last image if higher) -->
      <div class="performance-category">
        <h3>Armor Upgrades</h3>
        <div class="levels" style="grid-template-columns: repeat(5, 1fr);">
          <div class="upgrade-btn" onclick="addUpgrade('Armor Level 1', 2000)">Lvl 1<br>$2,000</div>
          <div class="upgrade-btn" onclick="addUpgrade('Armor Level 2', 3250)">Lvl 2<br>$3,250</div>
          <div class="upgrade-btn" onclick="addUpgrade('Armor Level 3', 6500)">Lvl 3<br>$6,500</div>
          <div class="upgrade-btn" onclick="addUpgrade('Armor Level 4', 9450)">Lvl 4<br>$9,450</div>
          <!-- Last image highest: $19,500 overrides $13,250 from screenshot -->
          <div class="upgrade-btn" onclick="addUpgrade('Armor Level 5', 19500)">Lvl 5<br>$19,500</div>
        </div>
      </div>

      <!-- BRAKES (3 levels: L1=$2000, L2=$3250, final from screenshot is $5500 which is higher than last image's $3500) -->
      <div class="performance-category">
        <h3>Brakes Upgrades</h3>
        <div class="levels" style="grid-template-columns: repeat(3, 1fr);">
          <div class="upgrade-btn" onclick="addUpgrade('Brakes Level 1', 2000)">Lvl 1<br>$2,000</div>
          <div class="upgrade-btn" onclick="addUpgrade('Brakes Level 2', 3250)">Lvl 2<br>$3,250</div>
          <div class="upgrade-btn" onclick="addUpgrade('Brakes Level 3', 5500)">Lvl 3<br>$5,500</div>
        </div>
      </div>

      <!-- GEARBOX (3 levels: L1=$2000, L2=$3250, final from screenshot is $5500 which is higher than last image's $2500) -->
      <div class="performance-category">
        <h3>Gearbox Upgrades</h3>
        <div class="levels" style="grid-template-columns: repeat(3, 1fr);">
          <div class="upgrade-btn" onclick="addUpgrade('Gearbox Level 1', 2000)">Lvl 1<br>$2,000</div>
          <div class="upgrade-btn" onclick="addUpgrade('Gearbox Level 2', 3250)">Lvl 2<br>$3,250</div>
          <div class="upgrade-btn" onclick="addUpgrade('Gearbox Level 3', 5500)">Lvl 3<br>$5,500</div>
        </div>
      </div>

      <!-- If the last image also has single-button "Suspension" or "Turbo" references: -->
      <div class="performance-category">
        <h3>Suspension</h3>
        <div class="button-grid">
          <!-- Last image shows $1,500 for suspension's highest? -->
          <div class="upgrade-btn" onclick="addUpgrade('Suspension (Max)', 1500)">Suspension<br>$1,500</div>
        </div>
      </div>

      <div class="performance-category">
        <h3>Turbo</h3>
        <div class="button-grid">
          <!-- Last image might show $2,000 for Turbo -->
          <div class="upgrade-btn" onclick="addUpgrade('Turbo', 2000)">Turbo<br>$2,000</div>
        </div>
      </div>
    </div><!-- end PERFORMANCE column -->

    <!-- RESPRAY COLUMN -->
    <div class="column respray-column">
      <h2>Respray</h2>
      <div class="button-grid">
        <!-- From the last image: $1000 + $100 fee => $1100 for primary/secondary, $600 for pearlescent, $200 interior, $100 dash/plate color -->
        <div class="upgrade-btn" onclick="addUpgrade('Primary Respray', 1100)">Primary Respray<br>$1,100</div>
        <div class="upgrade-btn" onclick="addUpgrade('Secondary Respray', 1100)">Secondary Respray<br>$1,100</div>
        <div class="upgrade-btn" onclick="addUpgrade('Pearlescent Respray', 600)">Pearlescent Respray<br>$600</div>
        <div class="upgrade-btn" onclick="addUpgrade('Interior Respray', 200)">Interior Respray<br>$200</div>
        <div class="upgrade-btn" onclick="addUpgrade('Dashboard Color', 100)">Dashboard Color<br>$100</div>
        <div class="upgrade-btn" onclick="addUpgrade('Plate Color', 100)">Plate Color<br>$100</div>
      </div>
    </div><!-- end RESPRAY column -->

    <!-- LIGHTING COLUMN -->
    <div class="column lighting-column">
      <h2>Lighting</h2>
      <div class="button-grid">
        <!-- From last image: +$100 fee => Xenon kit $200, color $200, Neon kit $300, color $200 -->
        <div class="upgrade-btn" onclick="addUpgrade('Xenon Kit', 200)">Xenon Kit<br>$200</div>
        <div class="upgrade-btn" onclick="addUpgrade('Xenon Color', 200)">Xenon Color<br>$200</div>
        <div class="upgrade-btn" onclick="addUpgrade('Neon Kit', 300)">Neon Kit<br>$300</div>
        <div class="upgrade-btn" onclick="addUpgrade('Neon Color', 200)">Neon Color<br>$200</div>
      </div>
    </div><!-- end LIGHTING column -->

  </div><!-- end .main-content -->

  <!-- SELECTED UPGRADES & TOTALS -->
  <div id="total-section">
    <h2>Selected Upgrades</h2>
    <ul id="selected-upgrades"></ul>
    <h3>Total Price: $<span id="total-price">0</span></h3>
    <button class="reset-btn" onclick="resetUpgrades()">Reset All</button>
  </div>

  <!-- CUSTOMER FORM & SUMMARY -->
  <div class="form-section">
    <h2>Customer Details</h2>
    <div class="form-row">
      <label for="customerName">Customer Name:</label>
      <input type="text" id="customerName" placeholder="Enter Customer Name" />
    </div>
    <div class="form-row">
      <label for="vehicle">Vehicle [Make/Model]:</label>
      <input type="text" id="vehicle" placeholder="Enter Make/Model" />
    </div>
    <div class="form-row">
      <label for="plate">Plate:</label>
      <input type="text" id="plate" placeholder="Enter Plate" />
    </div>

    <button class="generate-btn" onclick="generateSummary()">Generate Summary</button>

    <div id="summaryOutput"></div>
  </div>

  <!-- JS FOR PRICE CALCULATIONS & SUMMARY -->
  <script>
    let total = 0;
    let upgrades = [];

    // Add an upgrade to the list
    function addUpgrade(name, price) {
      upgrades.push({ name, price });
      total += price;
      renderUpgrades();
    }

    // Render the selected upgrades + total
    function renderUpgrades() {
      const upgradesList = document.getElementById('selected-upgrades');
      upgradesList.innerHTML = '';

      upgrades.forEach((upgrade, index) => {
        const li = document.createElement('li');
        li.textContent = `${upgrade.name} - $${upgrade.price}`;
        // Clicking an upgrade in the list removes it (optional "undo")
        li.addEventListener('click', () => removeUpgrade(index));
        upgradesList.appendChild(li);
      });

      document.getElementById('total-price').textContent = total;
    }

    // Remove a specific upgrade
    function removeUpgrade(index) {
      total -= upgrades[index].price;
      upgrades.splice(index, 1);
      renderUpgrades();
    }

    // Reset everything
    function resetUpgrades() {
      total = 0;
      upgrades = [];
      renderUpgrades();
    }

    // Generate final summary
    function generateSummary() {
      const name = document.getElementById('customerName').value || "N/A";
      const vehicle = document.getElementById('vehicle').value || "N/A";
      const plate = document.getElementById('plate').value || "N/A";
      const upgradesPurchased = upgrades.map(u => u.name).join(', ') || "None";

      const summary =
`Customer Name: ${name}
Vehicle | [Make/Model]: ${vehicle}
Plate: ${plate}
Upgrades Purchased: ${upgradesPurchased}
Price Charged: $${total}
SHOP: Twenty's`;

      document.getElementById('summaryOutput').textContent = summary;
    }
  </script>
</body>
</html>
