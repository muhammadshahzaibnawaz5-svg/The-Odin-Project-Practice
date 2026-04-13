<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>The Odin Project – Sign Up</title>
  <link rel="stylesheet" href="style.css" />
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@700&family=Lato:wght@300;400;700&display=swap" rel="stylesheet" />
</head>
<body>

  <!-- ===================== LEFT SIDEBAR ===================== -->
  <aside class="sidebar">
    <div class="sidebar-bg"></div>

    <div class="logo-block">
      <img
        src="https://www.theodinproject.com/assets/icons/top-logo-900-940f1ad72e696e3b42e57680fd16f1c2f6d7b40a2985a63b1c4b6c4e3d4d41f.svg"
        alt="The Odin Project Logo"
        class="odin-logo"
        onerror="this.style.display='none';"
      />
      <span class="logo-text">The Odin Project</span>
    </div>

    <p class="photo-credit">
      Photo by <a href="https://unsplash.com/@anandu" target="_blank" rel="noopener noreferrer">Anandu Vinod</a>
      on <a href="https://unsplash.com" target="_blank" rel="noopener noreferrer">Unsplash</a>
    </p>
  </aside>

  <!-- ===================== RIGHT FORM PANEL ===================== -->
  <main class="form-panel">

    <section class="form-intro">
      <p>Trusted by thousands of aspiring developers.</p>
      <h1>Start your coding journey today!</h1>
    </section>

    <form class="signup-form" novalidate>

      <div class="form-row">
        <div class="field-group">
          <label for="first-name">First Name</label>
          <input type="text" id="first-name" name="first-name" placeholder="John" required minlength="2" />
        </div>
        <div class="field-group">
          <label for="last-name">Last Name</label>
          <input type="text" id="last-name" name="last-name" placeholder="Doe" required minlength="2" />
        </div>
      </div>

      <div class="form-row">
        <div class="field-group">
          <label for="email">Email</label>
          <input type="email" id="email" name="email" placeholder="john@example.com" required />
        </div>
        <div class="field-group">
          <label for="phone">Phone Number</label>
          <input type="tel" id="phone" name="phone" placeholder="+1 (555) 000-0000" />
        </div>
      </div>

      <div class="form-row">
        <div class="field-group">
          <label for="password">Password</label>
          <input type="password" id="password" name="password" placeholder="At least 8 characters" required minlength="8" />
        </div>
        <div class="field-group">
          <label for="confirm-password">Confirm Password</label>
          <input type="password" id="confirm-password" name="confirm-password" placeholder="Repeat password" required minlength="8" />
        </div>
      </div>

      <button type="submit" class="btn-create">Create Account</button>

    </form>

    <p class="login-prompt">
      Already have an account? <a href="#">Log in</a>
    </p>

  </main>

</body>
</html>                                                                                                                                                                                                                                                                                                                                        /* =========================================================
   THE ODIN PROJECT – SIGN-UP PAGE
   Author: Your Name
   GitHub: https://github.com/yourusername
   ========================================================= */

/* ── Reset & Base ── */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

:root {
  --accent-green:        #596D48;
  --accent-green-hover:  #4a5d3c;
  --input-border-default: #E5E7EB;
  --input-border-focus:   #3B82F6;
  --input-border-invalid: #EF4444;
  --input-shadow-focus:   0 0 0 3px rgba(59, 130, 246, 0.25);
  --input-shadow-invalid: 0 0 0 3px rgba(239, 68, 68, 0.18);
  --sidebar-width: 38%;
  --font-display: 'Cinzel', serif;
  --font-body:    'Lato', sans-serif;
  --text-dark:  #1f2937;
  --text-mid:   #4b5563;
  --text-light: #9ca3af;
}

html, body {
  height: 100%;
}

body {
  display: flex;
  font-family: var(--font-body);
  background: #f9fafb;
  color: var(--text-dark);
  min-height: 100vh;
}

/* =========================================================
   SIDEBAR
   ========================================================= */

.sidebar {
  position: relative;
  width: var(--sidebar-width);
  min-height: 100vh;
  flex-shrink: 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}

/* Background image layer */
.sidebar-bg {
  position: absolute;
  inset: 0;
  background-image: url('https://images.unsplash.com/photo-1501854140801-50d01698950b?auto=format&fit=crop&w=1200&q=80');
  background-size: cover;
  background-position: center;
  filter: brightness(0.6) saturate(0.85);
  z-index: 0;
}

/* Dark green gradient overlay */
.sidebar::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
    160deg,
    rgba(41, 55, 30, 0.55) 0%,
    rgba(20, 30, 14, 0.70) 100%
  );
  z-index: 1;
}

/* ── Logo Block ── */
.logo-block {
  position: relative;
  z-index: 2;
  display: flex;
  align-items: center;
  gap: 16px;
  background: rgba(0, 0, 0, 0.42);
  backdrop-filter: blur(6px);
  -webkit-backdrop-filter: blur(6px);
  border-radius: 14px;
  padding: 22px 32px;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.35);
  border: 1px solid rgba(255, 255, 255, 0.08);
}

.odin-logo {
  width: 52px;
  height: 52px;
  object-fit: contain;
  filter: brightness(0) invert(1);
}

.logo-text {
  font-family: var(--font-display);
  font-size: clamp(1.6rem, 2.8vw, 2.4rem);
  font-weight: 700;
  color: #ffffff;
  letter-spacing: 0.04em;
  text-shadow: 0 2px 8px rgba(0, 0, 0, 0.5);
  white-space: nowrap;
}

/* ── Photo Credit ── */
.photo-credit {
  position: absolute;
  bottom: 18px;
  left: 0;
  right: 0;
  text-align: center;
  z-index: 2;
  font-size: 0.72rem;
  color: rgba(255, 255, 255, 0.55);
  letter-spacing: 0.02em;
}

.photo-credit a {
  color: rgba(255, 255, 255, 0.75);
  text-decoration: underline;
  text-underline-offset: 2px;
}

.photo-credit a:hover {
  color: #ffffff;
}

/* =========================================================
   FORM PANEL
   ========================================================= */

.form-panel {
  flex: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 60px clamp(32px, 6vw, 90px);
  background: #ffffff;
  box-shadow: -6px 0 40px rgba(0, 0, 0, 0.08);
}

/* ── Intro ── */
.form-intro {
  margin-bottom: 36px;
}

.form-intro p {
  font-size: 1rem;
  color: var(--text-mid);
  margin-bottom: 8px;
  font-weight: 300;
  letter-spacing: 0.02em;
}

.form-intro h1 {
  font-family: var(--font-display);
  font-size: clamp(1.5rem, 2.6vw, 2rem);
  font-weight: 700;
  color: var(--text-dark);
  line-height: 1.2;
  letter-spacing: 0.01em;
}

/* ── Form Card ── */
.signup-form {
  background: #f3f4f6;
  border-radius: 16px;
  padding: 36px 40px;
  box-shadow: 0 2px 16px rgba(0, 0, 0, 0.06);
  max-width: 560px;
  width: 100%;
}

.form-row {
  display: flex;
  gap: 24px;
  margin-bottom: 20px;
}

.form-row:last-of-type {
  margin-bottom: 28px;
}

.field-group {
  display: flex;
  flex-direction: column;
  flex: 1;
  gap: 6px;
}

/* ── Labels ── */
label {
  font-size: 0.78rem;
  font-weight: 700;
  color: var(--text-dark);
  text-transform: uppercase;
  letter-spacing: 0.07em;
}

/* ── Inputs ── */
input {
  padding: 10px 14px;
  border: 2px solid var(--input-border-default);
  border-radius: 8px;
  font-family: var(--font-body);
  font-size: 0.95rem;
  color: var(--text-dark);
  background: #ffffff;
  transition: border-color 0.18s ease, box-shadow 0.18s ease;
  outline: none;
}

input::placeholder {
  color: var(--text-light);
  font-weight: 300;
}

/* Focus state — blue border + glow */
input:focus {
  border-color: var(--input-border-focus);
  box-shadow: var(--input-shadow-focus);
}

/* Invalid state — only after user types (not on empty placeholder) */
input:not(:placeholder-shown):invalid {
  border-color: var(--input-border-invalid);
  box-shadow: var(--input-shadow-invalid);
}

/* Password fields: red border when invalid */
input[type="password"]:invalid {
  border-color: var(--input-border-invalid);
  box-shadow: var(--input-shadow-invalid);
}

/* But NOT when still showing placeholder (untouched) */
input[type="password"]:placeholder-shown {
  border-color: var(--input-border-default);
  box-shadow: none;
}

/* ── Submit Button ── */
.btn-create {
  display: block;
  width: 100%;
  padding: 14px;
  background-color: var(--accent-green);
  color: #ffffff;
  font-family: var(--font-body);
  font-size: 1rem;
  font-weight: 700;
  letter-spacing: 0.06em;
  text-transform: uppercase;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  transition: background-color 0.2s ease, transform 0.12s ease, box-shadow 0.2s ease;
  box-shadow: 0 4px 14px rgba(89, 109, 72, 0.35);
}

.btn-create:hover {
  background-color: var(--accent-green-hover);
  box-shadow: 0 6px 20px rgba(89, 109, 72, 0.45);
  transform: translateY(-1px);
}

.btn-create:active {
  transform: translateY(0);
  box-shadow: 0 2px 8px rgba(89, 109, 72, 0.3);
}

/* ── Login Prompt ── */
.login-prompt {
  margin-top: 28px;
  font-size: 0.9rem;
  color: var(--text-mid);
  max-width: 560px;
}

.login-prompt a {
  color: var(--accent-green);
  font-weight: 700;
  text-decoration: none;
  border-bottom: 1.5px solid transparent;
  transition: border-color 0.18s ease;
}

.login-prompt a:hover {
  border-bottom-color: var(--accent-green);
}

/* =========================================================
   ENTRANCE ANIMATIONS
   ========================================================= */

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(18px); }
  to   { opacity: 1; transform: translateY(0); }
}

.logo-block   { animation: fadeUp 0.6s ease both; animation-delay: 0.05s; }
.form-intro   { animation: fadeUp 0.55s ease both; animation-delay: 0.10s; }
.signup-form  { animation: fadeUp 0.55s ease both; animation-delay: 0.22s; }
.login-prompt { animation: fadeUp 0.55s ease both; animation-delay: 0.32s; }