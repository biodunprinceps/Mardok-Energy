# Mart Dok Petroleum - Dynamic Pricing Guide

## 🎯 Quick Start - Update Prices in 3 Ways

### Method 1: Admin Panel (Easiest) ⭐ RECOMMENDED

1. Open `admin-prices.html` in your browser
2. Enter the new prices
3. Click "Generate Code"
4. Copy the code and paste it into `index.html` (line ~1040)
5. Save and done!

### Method 2: Direct Edit (Fast)

1. Open `index.html`
2. Find the "DYNAMIC PRICING SYSTEM" section (around line 1040)
3. Update the numbers:

```javascript
const dieselPrices = {
  small: 850, // Change this number
  commercial: 820, // Change this number
  industrial: 790, // Change this number
};
```

4. Save and refresh!

### Method 3: JSON File (For API Integration)

1. Edit `prices.json`
2. Change the `pricePerLitre` values
3. Use this file with your backend/API

---

## 📁 Files You Got

1. **index.html** - Main website (with dynamic pricing built-in)
2. **admin-prices.html** - Price management interface
3. **prices.json** - Price data file (for API integration)

---

## 🔧 How It Works

The pricing system uses JavaScript to automatically update all prices on the page:

```javascript
// Configuration (in index.html)
const dieselPrices = {
  small: 850,
  commercial: 820,
  industrial: 790,
};

// This function updates the display
function updatePrices() {
  document.getElementById("price-small").textContent = `₦${dieselPrices.small}`;
  document.getElementById(
    "price-commercial"
  ).textContent = `₦${dieselPrices.commercial}`;
  document.getElementById(
    "price-industrial"
  ).textContent = `₦${dieselPrices.industrial}`;
}
```

---

## 🚀 Future Enhancements

### Connect to Real-Time API

Replace the `fetchPricesFromAPI()` function in index.html:

```javascript
async function fetchPricesFromAPI() {
  try {
    const response = await fetch("https://your-api.com/diesel-prices");
    const data = await response.json();

    dieselPrices.small = data.small;
    dieselPrices.commercial = data.commercial;
    dieselPrices.industrial = data.industrial;

    updatePrices();
  } catch (error) {
    console.error("Error:", error);
    updatePrices(); // Fallback to default prices
  }
}
```

### Auto-Update Every Hour

Add this to automatically refresh prices:

```javascript
// Update prices every hour
setInterval(fetchPricesFromAPI, 3600000); // 3600000ms = 1 hour
```

---

## 💡 Tips

- **Keep prices realistic**: Industrial should be cheaper than commercial
- **Update regularly**: The "Last Updated" date updates automatically
- **Test before publishing**: Always check prices display correctly
- **Backup**: Keep old prices in comments for reference

---

## 🆘 Troubleshooting

**Prices not showing?**

- Check browser console for errors (F12)
- Make sure IDs match: `price-small`, `price-commercial`, `price-industrial`

**Date not updating?**

- Check that `<span id="current-date"></span>` exists in HTML

**Need help?**

- All code is commented for easy understanding
- Use the admin panel for foolproof updates

---

## 📞 Support

For questions or issues, check the code comments in `index.html` at the "DYNAMIC PRICING SYSTEM" section.

Happy pricing! 🎉
