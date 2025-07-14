# galaxy-simulation
A digital runway of stars —'cos even the universe deserves a touch of style.💅🏽🌌
---

## 🔭 What Is This?

This is a *simple animated starfield simulation* built using pure *HTML + CSS*, designed to give your website a calm, silent, and aesthetic galaxy vibe — like floating in space.

---

## 🔧 Code Sample

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title> Neymaa's galaxy</title>
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background: black;
    }

    .stars {
      position: fixed;
      width: 100%;
      height: 100%;
      top: 0;
      left: 0;
      z-index: 0;
      pointer-events: none;
    }

    .stars::before {
      content: '';
      position: absolute;
      width: 1px;
      height: 1px;
      background: transparent;
      animation: twinkle 2s infinite alternate, floatStars 10s ease-in-out infinite;
      box-shadow:
        30px 40px #ffffff, 100px 120px #ccccee, 200px 180px #b0e0e6,
        300px 240px #ffe4e1, 400px 60px #ffccff, 500px 300px #f0ffff,
        600px 350px #ffffff, 700px 100px #ffffcc, 800px 220px #e0ffff,
        900px 180px #d8bfd8, 1000px 90px #f8f8ff, 1100px 260px #ffffff,
        1200px 310px #fffacd, 1300px 70px #ffe4b5, 1400px 200px #add8e6,
        1500px 400px #e6e6fa, 1600px 360px #fff, 1700px 130px #f5f5f5,
        1800px 420px #fafad2, 1900px 270px #e0ffff, 2000px 50px #ffebcd,
        2100px 100px #dcdcdc, 2200px 300px #fff5ee, 2300px 200px #fdf5e6;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 1; }
      50% { opacity: 0.4; }
    }

    @keyframes floatStars {
      0% { transform: translateY(0px); }
      50% { transform: translateY(10px); }
      100% { transform: translateY(0px); }
    }

    .shooting-stars {
      position: absolute;
      width: 100%;
      height: 100%;
      overflow: hidden;
      z-index: 1;
      pointer-events: none;
    }

    .shooting-star {
      position: absolute;
      top: 0;
      width: 2px;
      height: 80px;
      background: linear-gradient(-45deg, white, transparent);
      opacity: 0.8;
      transform: rotate(45deg);
      animation: shooting 6s linear infinite;
    }

    .shooting-star:nth-child(1) { left: 50%; animation-delay: 0s; }
    .shooting-star:nth-child(2) { left: 80%; animation-delay: 3s; }
    .shooting-star:nth-child(3) { left: 30%; animation-delay: 1.5s; }
    .shooting-star:nth-child(4) { left: 70%; animation-delay: 4s; }
    .shooting-star:nth-child(5) { left: 90%; animation-delay: 5.5s; }

    @keyframes shooting {
      0% {
        transform: translateX(0) translateY(0) rotate(45deg);
        opacity: 1;
      }
      100% {
        transform: translateX(-800px) translateY(800px) rotate(45deg);
        opacity: 0;
      }
    }

    .space {
      width: 100vw;
      height: 100vh;
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 2;
    }

    .sun {
      width: 120px;
      height: 120px;
      background: radial-gradient(circle, yellow, orange, red);
      border-radius: 50%;
      position: absolute;
      z-index: 10;
      box-shadow: 0 0 60px yellow;
    }

    .orbit {
      position: absolute;
      border: 1px solid rgba(255, 255, 255, 0.1);
      border-radius: 50%;
      animation: rotate linear infinite;
    }

    .orbit.mercury { width: 140px; height: 140px; animation-duration: 4s; }
    .orbit.venus   { width: 180px; height: 180px; animation-duration: 6s; }
    .orbit.earth   { width: 230px; height: 230px; animation-duration: 8s; }
    .orbit.mars    { width: 280px; height: 280px; animation-duration: 10s; }
    .orbit.jupiter { width: 340px; height: 340px; animation-duration: 14s; }
    .orbit.saturn  { width: 400px; height: 400px; animation-duration: 18s; }
    .orbit.uranus  { width: 460px; height: 460px; animation-duration: 22s; }
    .orbit.neptune { width: 520px; height: 520px; animation-duration: 26s; }

    .planet {
      position: absolute;
      top: 50%;
      left: 100%;
      transform: translate(-50%, -50%);
      border-radius: 50%;
    }

    .planet.mercury { width: 8px;  height: 8px;  background: radial-gradient(circle, #9e9e9e, #555); }
    .planet.venus   { width: 14px; height: 14px; background: radial-gradient(circle, #e6d8ad, #b49c6e); }
    .planet.earth   { width: 16px; height: 16px; background: radial-gradient(circle, #3399ff, #003366); }
    .planet.mars    { width: 12px; height: 12px; background: radial-gradient(circle, #e2725b, #5c1e15); }
    .planet.jupiter { width: 24px; height: 24px; background: radial-gradient(circle, #d9b38c, #8b5e3c); }
    .planet.saturn  { width: 20px; height: 20px; background: radial-gradient(circle, #f5d76e, #a78b2b); }
    .planet.uranus  { width: 16px; height: 16px; background: radial-gradient(circle, #a2f0f0, #2daaaa); }
    .planet.neptune { width: 16px; height: 16px; background: radial-gradient(circle, #5c5cff, #000080); }

    @keyframes rotate {
      from { transform: rotate(0deg); }
      to   { transform: rotate(360deg); }
    }
  </style>
</head>
<body>
  <div class="stars"></div>

  <div class="shooting-stars">
    <div class="shooting-star"></div>
    <div class="shooting-star"></div>
    <div class="shooting-star"></div>
    <div class="shooting-star"></div>
    <div class="shooting-star"></div>
  </div>

  <div class="space">
    <div class="sun"></div>
    <div class="orbit mercury"><div class="planet mercury"></div></div>
    <div class="orbit venus"><div class="planet venus"></div></div>
    <div class="orbit earth"><div class="planet earth"></div></div>
    <div class="orbit mars"><div class="planet mars"></div></div>
    <div class="orbit jupiter"><div class="planet jupiter"></div></div>
    <div class="orbit saturn"><div class="planet saturn"></div></div>
    <div class="orbit uranus"><div class="planet uranus"></div></div>
    <div class="orbit neptune"><div class="planet neptune"></div></div>
  </div>
</body>
</html>
