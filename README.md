<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <title>Nonchopper Official Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    :root {
      --bg: #000;
      --fg: #fff;
      --accent: #fff;
      --font-main: -apple-system, BlinkMacSystemFont, "Helvetica Neue", Arial, sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    body {
      background: var(--bg);
      color: var(--fg);
      font-family: var(--font-main);
      line-height: 1.6;
    }

    a {
      color: var(--fg);
      text-decoration: none;
    }

    .page {
      max-width: 1200px;
      margin: 0 auto;
      padding: 40px 24px 80px;
    }

    /* header */

    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid #333;
      padding-bottom: 16px;
      margin-bottom: 40px;
    }

    .logo {
      letter-spacing: 0.2em;
      font-size: 14px;
      text-transform: uppercase;
    }

    nav ul {
      display: flex;
      gap: 24px;
      list-style: none;
      font-size: 13px;
      text-transform: uppercase;
      letter-spacing: 0.12em;
    }

    nav a {
      position: relative;
    }

    nav a::after {
      content: "";
      position: absolute;
      left: 0;
      bottom: -4px;
      width: 0;
      height: 1px;
      background: var(--accent);
      transition: width 0.25s ease;
    }

    nav a:hover::after {
      width: 100%;
    }

    /* hero */

    .hero {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 0.9fr);
      gap: 40px;
      align-items: center;
      margin-bottom: 60px;
    }

    .hero-title {
      font-size: 32px;
      letter-spacing: 0.12em;
      text-transform: uppercase;
    }

    .hero-sub {
      margin-top: 16px;
      font-size: 14px;
      color: #aaa;
      max-width: 420px;
    }

    .hero-meta {
      margin-top: 32px;
      font-size: 12px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: #888;
    }

    .hero-image {
      position: relative;
      border: 1px solid #333;
      padding: 16px;
      aspect-ratio: 4 / 5;
      display: flex;
      align-items: center;
      justify-content: center;
      overflow: hidden;
    }

    .hero-image-inner {
      width: 100%;
      height: 100%;
      background: #111;
      background-size: cover;
      background-position: center;
      /* ここにトップビジュアルを設定 */
      /* background-image: url("images/top.jpg"); */
    }

    .hero-caption {
      position: absolute;
      bottom: 12px;
      left: 16px;
      font-size: 11px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: #ccc;
    }

    /* section */

    section {
      margin-bottom: 60px;
    }

    .section-header {
      display: flex;
      justify-content: space-between;
      align-items: baseline;
      margin-bottom: 24px;
      border-top: 1px solid #333;
      padding-top: 16px;
    }

    .section-title {
      font-size: 14px;
      text-transform: uppercase;
      letter-spacing: 0.18em;
    }

    .section-sub {
      font-size: 12px;
      color: #777;
    }

    /* gallery */

    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 16px;
    }

    .gallery-item {
      position: relative;
      background: #111;
      aspect-ratio: 4 / 5;
      overflow: hidden;
      border: 1px solid #222;
    }

    .gallery-thumb {
      width: 100%;
      height: 100%;
      background-size: cover;
      background-position: center;
      transition: transform 0.4s ease, opacity 0.4s ease;
      opacity: 0.9;
    }

    .gallery-item:hover .gallery-thumb {
      transform: scale(1.04);
      opacity: 1;
    }

    .gallery-label {
      position: absolute;
      bottom: 10px;
      left: 12px;
      font-size: 10px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
      color: #ccc;
      background: rgba(0, 0, 0, 0.6);
      padding: 4px 8px;
    }

    /* about */

    .about-layout {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 0.9fr);
      gap: 32px;
    }

    .about-text {
      font-size: 13px;
      color: #ccc;
    }

    .about-meta {
      font-size: 12px;
      color: #888;
      margin-top: 16px;
    }

    .about-sign {
      margin-top: 32px;
      font-size: 12px;
      letter-spacing: 0.16em;
      text-transform: uppercase;
    }

    .about-sign span {
      display: block;
      margin-top: 8px;
      font-family: "Times New Roman", serif;
      font-size: 18px;
      letter-spacing: 0.04em;
    }

    /* contact */

    .contact-layout {
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 0.9fr);
      gap: 32px;
      font-size: 13px;
      color: #ccc;
    }

    .contact-list {
      list-style: none;
    }

    .contact-list li {
      margin-bottom: 8px;
    }

    .contact-label {
      font-size: 11px;
      text-transform: uppercase;
      letter-spacing: 0.16em;
      color: #777;
    }

    .contact-value {
      margin-top
