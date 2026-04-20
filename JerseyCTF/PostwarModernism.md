# Challenge: Postwar Modernism
**Category:** OSINT
**Difficulty:** Hard
**CTF:** Jersey CTF 2026

## 📂 Files Provided
- Postwar_Modernism.png

## 🧠 Approach / Thought Process
- I first tried to reverse image search the png provided to identify the general location of the image. This did not work.
- Using Claude, I provided it with the image and it was able to deduce the image was likely taken near the JSC in Houston, Texas.
- Knowing the general area, I used Google Maps to identify any photospheres or street view available near the general area.
- I found a photosphere that was extremely close to where the image looked like it was taken.
- Cross referencing the photosphere, I used what3words and zoomed in as close as possible to brute force all surrounding 3x3 squares near the photosphere's location.

## 🛠️ Step-by-Step Solution
1. Use Claude or another LLM of choice to deduce the general location of the image.
2. Locate a photosphere/Google Street View image likely near the origin of the photo.
3. Brute force all 3x3 squares near the photosphere by slowly submitting answers until you get the right one. (It shouldn't take more than 10)

## 🎯 Final Flag
`jctf{rattling.depictions.served}`

