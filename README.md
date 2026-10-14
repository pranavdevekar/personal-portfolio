<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Your Name | Portfolio</title>
  <meta name="description" content="Personal portfolio website for a developer, designer, or creative professional." />
  <style>
    :root {
      --bg: #0f172a;
      --bg-soft: #111827;
      --panel: #1f2937;
      --panel-2: #0b1220;
      --text: #e5e7eb;
      --muted: #94a3b8;
      --primary: #7c3aed;
      --primary-2: #22c55e;
      --accent: #38bdf8;
      --border: rgba(148, 163, 184, 0.2);
      --shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
      --radius: 18px;
      --container: 1120px;
    }

    * { box-sizing: border-box; }

    html {
      scroll-behavior: smooth;
    }

    body {
      margin: 0;
      font-family: Arial, Helvetica, sans-serif;
      background: linear-gradient(135deg, var(--bg) 0%, var(--bg-soft) 100%);
      color: var(--text);
      line-height: 1.6;
    }

    img {
      max-width: 100%;
      display: block;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(var(--container), calc(100% - 2rem));
      margin: 0 auto;
    }

    header {
      position: sticky;
      top: 0;
      z-index: 50;
      backdrop-filter: blur(14px);
      background: rgba(15, 23, 42, 0.7);
      border-bottom: 1px solid var(--border);
    }

    .nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      min-height: 70px;
    }

    .brand {
      font-size: 1.2rem;
      font-weight: 800;
      letter-spacing: 0.05em;
    }

    .brand span {
      color: var(--primary-2);
    }

    .nav-links {
      display: flex;
      gap: 1.5rem;
      align-items: center;
      flex-wrap: wrap;
    }

    .nav-links a {
      color: var(--muted);
      transition: color 0.2s ease;
      font-weight: 600;
    }

    .nav-links a:hover {
      color: var(--text);
    }

    .nav-links .btn {
      margin-left: 0.5rem;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.9rem 1.5rem;
      border-radius: 999px;
      border: 1px solid transparent;
      background: linear-gradient(135deg, var(--primary), var(--accent));
      color: white;
      font-weight: 700;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      box-shadow: var(--shadow);
    }

    .btn:hover {
      transform: translateY(-2px);
    }

    .btn.secondary {
      background: transparent;
      border-color: var(--border);
      box-shadow: none;
    }

    section {
      padding: 5.5rem 0;
    }

    .hero {
      min-height: 90vh;
      display: flex;
      align-items: center;
      padding-top: 4rem;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.3fr 0.7fr;
      align-items: center;
      gap: 3rem;
    }

    .eyebrow {
      display: inline-block;
      padding: 0.45rem 0.9rem;
      background: rgba(124, 58, 237, 0.12);
      border: 1px solid rgba(124, 58, 237, 0.3);
      border-radius: 999px;
      color: #d8c3ff;
      font-size: 0.8rem;
      font-weight: 700;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      margin-bottom: 1.2rem;
    }

    h1 {
      font-size: clamp(2.8rem, 5vw, 5rem);
      line-height: 1.04;
      margin: 0 0 1rem;
      letter-spacing: -0.05em;
    }

    .gradient-text {
      background: linear-gradient(135deg, #c4b5fd 0%, #67e8f9 50%, #86efac 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .lead {
      max-width: 640px;
      color: var(--muted);
      font-size: 1.08rem;
      margin-bottom: 2rem;
    }

    .hero-actions {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
      margin-bottom: 2rem;
    }

    .socials {
      display: flex;
      gap: 1rem;
      flex-wrap: wrap;
    }

    .socials a {
      width: 42px;
      height: 42px;
      border-radius: 50%;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: rgba(255,255,255,0.03);
      border: 1px solid var(--border);
      color: var(--text);
      font-weight: 700;
      transition: transform 0.2s ease, border-color 0.2s ease;
    }

    .socials a:hover {
      transform: translateY(-2px);
      border-color: rgba(124, 58, 237, 0.4);
    }

    .profile-card {
      position: relative;
      background: linear-gradient(180deg, rgba(255,255,255,0.04), rgba(255,255,255,0.01));
      border: 1px solid var(--border);
      border-radius: var(--radius);
      padding: 1rem;
      box-shadow: var(--shadow);
    }

    .profile-photo {
      position: relative;
      border-radius: 22px;
      overflow: hidden;
      min-height: 520px;
      background:
        linear-gradient(135deg, rgba(124,58,237,0.3), rgba(56,189,248,0.2)),
        #172033;
      border: 1px solid rgba(255,255,255,0.08);
    }

    .profile-photo::before {
      content: "";
      position: absolute;
      inset: 20px;
      border-radius: 18px;
      background: radial-gradient(circle at 50% 20%, rgba(255,255,255,0.15), rgba(255,255,255,0.02) 35%, transparent 55%),
                  linear-gradient(180deg, rgba(15,23,42,0.2), rgba(15,23,42,0.8));
      border: 1px solid rgba(255,255,255,0.06);
    }

    .profile-badge {
      position: absolute;
      bottom: 20px;
      left: 20px;
      right: 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
      padding: 1rem 1.1rem;
      border-radius: 16px;
      background: rgba(15, 23, 42, 0.7);
      border: 1px solid rgba(148,163,184,0.12);
      backdrop-filter: blur(8px);
    }

    .badge-title {
      font-size: 0.72rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.08em*

