# Crypto Ticker for Streamlabs

This project is a customizable cryptocurrency ticker designed for Streamlabs, which fetches real-time data from the CoinGecko API and displays it in a scrolling animation.

---

## Features
- Real-time cryptocurrency prices and 24-hour price changes.
- Smooth scrolling ticker animation.
- Color-coded price changes (green for up, red for down).
- Fully customizable HTML, CSS, and JavaScript.

---

## File Details
- **File Name**: `crypto-ticker-streamlabs.html`
- **Dependencies**: No additional dependencies required. Optionally uses Axios for more robust HTTP requests.

---

## Hosting Options
To use the crypto ticker in Streamlabs, host the `crypto-ticker-streamlabs.html` file online. Here are some free hosting options:

1. **GitHub Pages**:
   - Upload your file to a GitHub repository and enable GitHub Pages.
   - Get the public URL (e.g., `https://<username>.github.io/crypto-ticker.html`).

2. **Netlify**:
   - Drag and drop the HTML file into Netlify for instant hosting.
   - Get the public URL (e.g., `https://<site-name>.netlify.app`).

3. **Vercel**:
   - Upload the HTML file via Vercel for hosting.
   - Get the public URL (e.g., `https://crypto-ticker.vercel.app`).

4. **Glitch**:
   - Upload the file to Glitch for real-time hosting and editing.
   - Get the public URL (e.g., `https://crypto-ticker.glitch.me`).

---

## Adding to Streamlabs
1. **Open Streamlabs**:
   - Go to the scene where you want to add the crypto ticker.

2. **Add a Browser Source**:
   - Click the `+` icon to add a new source.
   - Choose **Browser Source**.

3. **Configure Browser Source**:
   - Enter the hosted URL (e.g., from GitHub Pages, Netlify, etc.).
   - Set the resolution (e.g., width: `1920px`, height: `40px`).

4. **Save and Test**:
   - Save the settings and ensure the ticker is visible in the scene preview.

---

## File Structure
```plaintext
crypto-ticker-streamlabs.html
  - HTML: Handles the structure of the ticker.
  - CSS: Defines the styling, including scrolling animation and colors.
  - JavaScript: Fetches data from CoinGecko API and updates the ticker.
```

---

## Code Overview
### HTML
Defines the structure, including the container and debug panel:
```html
<div id="debug">Initializing...</div>
<div class="ticker-container">
    <div class="ticker-scroll" id="ticker">
        <div class="ticker-item">Loading cryptocurrency data...</div>
    </div>
</div>
```

### CSS
Handles the scrolling animation and visual styles:
```css
@keyframes scroll {
    0% {
        transform: translateX(100%);
    }
    100% {
        transform: translateX(-100%);
    }
}
```

### JavaScript
Fetches real-time cryptocurrency data from the CoinGecko API:
```javascript
async function fetchCryptoData() {
    try {
        const response = await fetch('https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=20&page=1&sparkline=false');
        const data = await response.json();
        // Process and display the data...
    } catch (error) {
        console.error('Error fetching crypto data:', error);
    }
}
```

---

## How to Customize
### Update Coin Limit
Modify the `per_page` parameter in the API URL to change the number of coins displayed:
```javascript
const response = await fetch('https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=10&page=1&sparkline=false');
```

### Adjust Animation Speed
Update the `animation-duration` in the CSS for faster or slower scrolling:
```css
.ticker-scroll {
    animation: scroll 120s linear infinite; /* Change 120s to your desired duration */
}
```

### Change Colors
Customize colors for price changes in the CSS:
```css
.price-up {
    color: #00ff00;
}
.price-down {
    color: #ff0000;
}
```

---

## Troubleshooting
### Ticker Doesn’t Load
- Check if the hosted URL is correct.
- Verify API access (test the API URL in your browser).
- Ensure the Streamlabs Browser Source has an active internet connection.

### Debugging
- Use the `#debug` div to display error messages.
- Open the browser console (F12) to check for errors.

---

## Support
For questions or issues, feel free to reach out or consult the documentation for the chosen hosting service.

---

## License
This project is open-source and available for modification and redistribution.

