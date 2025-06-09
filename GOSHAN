<!DOCTYPE html><html lang="en" >
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Flame Creative Studio - Advanced Video &amp; Image Creator</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Outfit:wght@600;700&display=swap');/* Base reset and styling */
html, body {
  margin: 0;
  padding: 0;
  min-height: 100vh;
  font-family: 'Outfit', sans-serif;
  background-color: #000000;
  color: #6b7280; /* neutral gray for general text */
  overflow-x: hidden;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  line-height: 1.6;
  position: relative;
}
body.modal-open {
  overflow: hidden;
}

/* Starfield background fixed behind everything */
#starfield {
  position: fixed;
  top: 0; left: 0; width: 100%; height: 100%;
  background: radial-gradient(ellipse at center, rgba(30, 10, 50, 0.35) 0%, #000000 98%);
  overflow: hidden;
  z-index: -1;
  pointer-events: none;
  user-select: none;
}
/* Small twinkling stars */
.star {
  position: absolute;
  border-radius: 50%;
  opacity: 0.7;
  filter: drop-shadow(0 0 2px rgba(127,127,255,0.9));
  animation: twinkle 4s infinite ease-in-out alternate;
  background: linear-gradient(45deg, #7f7fff, #b37aff);
  will-change: opacity, transform;
}
/* Shooting stars */
.shooting-star {
  position: absolute;
  width: 120px;
  height: 2px;
  background: linear-gradient(90deg, rgba(0,0,0,0), #7f7fff, #b37aff);
  border-radius: 50%;
  box-shadow: 0 0 10px 3px #b37aff;
  transform: rotate(-45deg);
  animation: shoot 6s linear infinite;
  opacity: 0;
  will-change: opacity, transform;
  pointer-events: none;
  user-select: none;
}
@keyframes twinkle {
  0%, 100% { opacity: 0.2; transform: scale(1); }
  50% { opacity: 1; transform: scale(1.3); }
}
@keyframes shoot {
  0% {
    transform: translateX(0) translateY(0) rotate(-45deg);
    opacity: 0;
  }
  10% {
    opacity: 1;
  }
  100% {
    transform: translateX(1100px) translateY(-1100px) rotate(-45deg);
    opacity: 0;
  }
}

/* Header styling */
header {
  position: sticky;
  top: 0;
  background: rgba(0,0,0,0.75);
  border-bottom: 1px solid #2a2a4a;
  z-index: 50;
  user-select: none;
}
.container {
  max-width: 1200px;
  margin-left: auto;
  margin-right: auto;
  padding-left: 1rem;
  padding-right: 1rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 4rem;
}
nav > ul {
  display: flex;
  gap: 2rem;
  list-style: none;
  padding: 0;
  margin: 0;
  align-items: center;
}
nav a, #login-btn {
  color: #b0b0ff;
  font-weight: 600;
  font-size: 1rem;
  transition: color 0.3s ease, background-color 0.3s ease;
  background: transparent;
  border: none;
  cursor: pointer;
  font-family: 'Outfit', sans-serif;
  padding: 0.25rem 0.5rem;
  border-radius: 0.5rem;
  user-select: none;
}
nav a:hover,
nav a:focus,
#login-btn:hover,
#login-btn:focus {
  color: #e0e0ff;
  outline: none;
  background-color: rgba(127, 122, 255, 0.2);
  transition: background-color 0.3s ease, color 0.3s ease;
}
.logo {
  font-weight: 700;
  font-size: 1.5rem;
  color: #7f7fff;
  letter-spacing: 0.05em;
  user-select: none;
  font-family: 'Outfit', sans-serif;
}

/* Hero Section */
.hero {
  padding-top: 6rem;
  padding-bottom: 5rem;
  text-align: center;
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
  color: #c5c9ff;
  user-select: none;
}
.hero h1 {
  font-size: 3.75rem;
  font-weight: 700;
  line-height: 1.1;
  text-shadow: 0 0 10px rgba(127,122,255,0.75);
  margin-bottom: 1rem;
}
.hero p {
  font-size: 1.5rem;
  margin-bottom: 3rem;
  color: #a3a7ffcc;
}
.btn-cta {
  background-color: #7f7fff;
  color: #eee;
  font-weight: 700;
  font-size: 1.25rem;
  padding: 1rem 3rem;
  border-radius: 1rem;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease, transform 0.3s ease;
  box-shadow: 0 6px 20px rgba(127, 122, 255, 0.4);
  user-select: none;
}
.btn-cta:hover,
.btn-cta:focus {
  background-color: #b37aff;
  outline: none;
  transform: translateY(-5px);
  box-shadow: 0 10px 30px rgba(179, 122, 255, 0.7);
}

/* Main content container - initially hidden, only visible after login */
main {
  max-width: 900px;
  margin: 3rem auto 6rem;
  background: rgba(255 255 255 / 0.95);
  border-radius: 1rem;
  box-shadow: 0 16px 40px rgb(127 122 255 / 0.25);
  padding: 2rem 2rem 3rem;
  color: #374151;
  font-size: 1.125rem;
  display: none;
  user-select: text;
}
main.active {
  display: block;
}
section {
  margin-bottom: 3.5rem;
}

.card {
  border-radius: 1rem;
  background: white;
  padding: 2rem 2.5rem;
  box-shadow: 0 5px 15px rgb(127 122 255 / 0.15);
  color: #374151;
}
.card h2 {
  font-weight: 700;
  font-size: 2.5rem;
  margin-bottom: 1.5rem;
  color: #4c51bf;
  text-align: center;
  user-select: text;
}
.card label {
  font-weight: 600;
  display: block;
  margin-bottom: 0.5rem;
  color: #4a4a7e;
}

/* Textarea improvements */
textarea {
  width: 100%;
  height: 150px;
  border-radius: 1rem;
  border: 1.75px solid #c5c6f0;
  padding: 1rem 1.25rem;
  color: #374151;
  font-size: 1.125rem;
  resize: vertical;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
  font-weight: 400;
  font-family: 'Outfit', sans-serif;
  line-height: 1.5;
  letter-spacing: 0.012em;
  box-shadow: 0 0 12px rgba(163, 167, 255, 0.3) inset;
}
textarea::placeholder {
  color: #9ca3af;
  font-style: italic;
}
textarea:focus {
  outline: none;
  border-color: #7f7fff;
  box-shadow: 0 0 20px rgba(127, 122, 255, 0.6);
}

/* Select improvements */
select {
  width: 100%;
  font-size: 1rem;
  border-radius: 0.75rem;
  border: 1.5px solid #c5c6f0;
  padding: 0.5rem 0.75rem;
  color: #4a4a7e;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
  font-family: 'Outfit', sans-serif;
}
select:focus {
  outline: none;
  border-color: #7f7fff;
  box-shadow: 0 0 20px rgba(127, 122, 255, 0.6);
}

/* Radio groups */
.radio-group {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  margin-bottom: 1rem;
  user-select: none;
}
input[type="radio"] {
  display: none;
}
input[type="radio"] + label {
  border: 2px solid #c5c6f0;
  border-radius: 1rem;
  padding: 0.6rem 1.5rem;
  cursor: pointer;
  font-weight: 600;
  font-size: 1rem;
  color: #4a4a7e;
  transition: all 0.3s ease;
  user-select: none;
  white-space: nowrap;
  font-family: 'Outfit', sans-serif;
}
input[type="radio"]:checked + label {
  background-color: #7f7fff;
  border-color: #7f7fff;
  color: white;
  box-shadow: 0 0 25px rgba(127, 122, 255, 0.6);
}
input[type="radio"]:focus-visible + label {
  outline: 3px solid #b37aff;
  outline-offset: 3px;
}

/* Create button */
.btn-create {
  width: 100%;
  background-color: #7f7fff;
  color: white;
  font-weight: 700;
  font-size: 1.25rem;
  padding: 1rem;
  border-radius: 1.25rem;
  cursor: pointer;
  border: none;
  margin-top: 2rem;
  box-shadow: 0 10px 35px rgba(127, 122, 255, 0.45);
  transition: background-color 0.3s ease, transform 0.3s ease;
  user-select: none;
  font-family: 'Outfit', sans-serif;
}
.btn-create:hover,
.btn-create:focus {
  background-color: #b37aff;
  outline: none;
  transform: translateY(-4px);
  box-shadow: 0 12px 40px rgba(179, 122, 255, 0.75);
}

/* Result preview container */
#result-container {
  margin-top: 2rem;
  text-align: center;
  color: #5243a3;
  user-select: none;
}
#result-preview {
  margin: 1rem auto;
  width: 320px;
  height: 320px;
  border-radius: 1.25rem;
  border: 2px dashed #b5a6ff;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.25rem;
  color: #b5a6ff;
  background: #f6f3ff;
  position: relative;
  overflow: hidden;
  user-select: none;
  box-shadow: 0 4px 15px rgb(179 122 255 / 0.4) inset;
}
#result-preview canvas {
  border-radius: 1.25rem;
  max-width: 100%;
  max-height: 100%;
  object-fit: contain;
}
#download-button {
  display: none;
  margin-top: 1.25rem;
  padding: 0.75rem 1.5rem;
  font-weight: 700;
  font-size: 1.125rem;
  border-radius: 0.75rem;
  border: none;
  color: #7f7fff;
  background-color: #e6e0ff;
  cursor: pointer;
  transition: background-color 0.3s ease;
  user-select: none;
  font-family: 'Outfit', sans-serif;
}
#download-button:hover,
#download-button:focus {
  background-color: #d1c4ff;
  outline: none;
}

/* Login Modal */
#login-modal {
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.85);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
  padding: 1rem;
  user-select: none;
}
#login-modal.hidden {
  display: none;
}
#login-modal .modal-content {
  background: #1a1a2e;
  padding: 2rem 2.5rem;
  border-radius: 1.5rem;
  max-width: 420px;
  width: 100%;
  color: #c5c9ff;
  box-shadow: 0 10px 40px rgb(127 122 255 / 0.6);
  font-family: 'Outfit', sans-serif;
  user-select: text;
  position: relative;
}
#login-modal h2 {
  font-size: 1.75rem;
  font-weight: 700;
  margin-bottom: 1rem;
  color: #b3b8ff;
  text-align: center;
  user-select: text;
}
#login-modal label {
  color: #aeadff;
  font-weight: 600;
  margin-top: 1rem;
  display: block;
  user-select: text;
}
#login-modal input[type="text"],
#login-modal input[type="password"] {
  margin-top: 0.5rem;
  width: 100%;
  border-radius: 0.75rem;
  border: 1.5px solid #7f7fff;
  font-size: 1rem;
  color: #c5c9ff;
  background: #2a2a4a;
  padding: 0.5rem 1rem;
  font-family: 'Outfit', sans-serif;
  transition: border-color 0.3s ease, box-shadow 0.3s ease;
  user-select: text;
}
#login-modal input[type="text"]:focus,
#login-modal input[type="password"]:focus {
  outline: none;
  border-color: #b37aff;
  box-shadow: 0 0 20px rgba(179, 122, 255, 0.9);
}
#login-modal button {
  margin-top: 1.75rem;
  width: 100%;
  background-color: #7f7fff;
  color: white;
  border-radius: 1rem;
  padding: 0.75rem;
  font-weight: 700;
  font-size: 1.125rem;
  border: none;
  cursor: pointer;
  transition: background-color 0.3s ease;
  user-select: none;
  box-shadow: 0 6px 20px rgba(127 122 255 / 0.5);
}
#login-modal button:hover,
#login-modal button:focus {
  background-color: #b37aff;
  outline: none;
  box-shadow: 0 8px 25px rgba(179, 122, 255, 0.85);
}
#login-modal .close-btn {
  position: absolute;
  top: 1rem;
  right: 1.5rem;
  font-weight: 900;
  font-size: 1.6rem;
  line-height: 1;
  cursor: pointer;
  color: #aeadff;
  user-select: none;
  background: transparent;
  border: none;
  transition: color 0.3s ease;
}
#login-modal .close-btn:hover,
#login-modal .close-btn:focus {
  color: #e8e8ff;
  outline: none;
}

/* About Section */
#about {
  max-width: 700px;
  margin-left: auto;
  margin-right: auto;
  padding: 2rem 2.25rem 3rem 2.25rem;
  color: #bbbefd;
  line-height: 1.6;
  font-size: 1.125rem;
  border-radius: 1rem;
  background: rgba(127 122 255 / 0.12);
  box-shadow: 0 0 40px rgb(127 122 255 / 0.25);
  user-select: text;
}
#about h2 {
  font-weight: 700;
  font-size: 2.5rem;
  margin-bottom: 1.25rem;
  color: #cbcfff;
  text-align: center;
  user-select: text;
}
#about p {
  margin-bottom: 0.8rem;
  text-align: center;
  user-select: text;
}
#about a {
  color: #b0b0ff;
  font-weight: 600;
  text-decoration: underline;
  cursor: pointer;
  transition: color 0.3s ease;
  user-select: text;
}
#about a:hover,
#about a:focus {
  color: #e0e0ff;
  outline: none;
}

/* Responsive */
@media (max-width: 640px) {
  .hero h1 {
    font-size: 2.75rem;
    padding: 0 1rem;
  }
  main {
    padding: 2rem 1rem 4rem;
    margin-bottom: 4rem;
  }
  .card {
    padding: 2rem 1rem;
  }
}

  </style>
</head>
<body>  <!-- Starfield Background -->  <div id="starfield" aria-hidden="true"></div>  <!-- Header -->  <header>
    <div class="container" role="banner">
      <div class="logo" tabindex="0" aria-label="Flame Creative Studio Logo">flame²⁺²=1</div>
      <nav aria-label="Primary Navigation">
        <ul>
          <li><a href="#create" tabindex="0" id="nav-create-link" class="hidden-on-login">Create</a></li>
          <li><a href="#about" tabindex="0" id="nav-about-link" class="hidden-on-login">About Me</a></li>
          <li><button id="login-btn" aria-haspopup="dialog" aria-controls="login-modal" class="text-blue-300 hover:text-indigo-400 focus:outline-none focus:ring-2 focus:ring-indigo-400 rounded px-2 py-1 transition hidden-on-login">Log In</button>
          <button id="logout-btn" class="text-blue-300 hover:text-indigo-400 focus:outline-none focus:ring-2 focus:ring-indigo-400 rounded px-2 py-1 transition hidden-on-logout" style="display:none;">Log Out</button></li>
        </ul>
      </nav>
    </div>
  </header>  <!-- Hero Section -->  <section class="hero" role="region" aria-label="Welcome hero">
    <h1>Extraordinary Video &amp; Image Creator</h1>
    <p>Create stunning videos and images with ease. Choose style, voices, and length — then download your masterpiece.</p>
    <button class="btn-cta hidden-on-login" id="hero-login-btn" type="button" aria-label="Log in to start creating">Log In to Start Creating</button>
  </section>  <main tabindex="-1" aria-live="polite" aria-atomic="true" >
    <!-- Create Content Section -->
    <section id="create" class="card" role="region" aria-label="Content creation form">
      <h2>Create Your Video or Picture</h2>
      <form id="create-form" aria-describedby="form-description" autocomplete="off">
        <p id="form-description" class="sr-only">Use the form fields below to customize your video or picture creation.</p><!-- Description Input (Square) -->
    <label for="description">Description (Write here)</label>
    <textarea id="description" name="description" placeholder="Enter your writing description…" required aria-required="true" rows="6" aria-describedby="desc-help"></textarea>
    <div id="desc-help" class="sr-only">Write a description for your video or picture, multiline supported.</div>

    <!-- Style Options -->
    <fieldset class="mt-6" aria-labelledby="style-label">
      <legend id="style-label" class="font-semibold text-gray-700 mb-2">Choose Style</legend>
      <div class="radio-group" role="radiogroup" aria-describedby="style-label">
        <input type="radio" id="style-animated" name="style" value="animated" required />
        <label for="style-animated" tabindex="0">Animated</label>

        <input type="radio" id="style-realistic" name="style" value="realistic" />
        <label for="style-realistic" tabindex="0">Realistic</label>

        <input type="radio" id="style-dreamy" name="style" value="dreamy" />
        <label for="style-dreamy" tabindex="0">Dreamy</label>

        <input type="radio" id="style-bw" name="style" value="black_and_white" />
        <label for="style-bw" tabindex="0">Black &amp; White</label>
      </div>
    </fieldset>

    <!-- Video Length Option -->
    <label for="video-length" class="mt-6 block font-semibold text-gray-700">Select Video Length (seconds)</label>
    <select name="video-length" id="video-length" aria-label="Select video length in seconds" required>
      <option value="5">5</option>
      <option value="10" selected>10</option>
      <option value="15">15</option>
      <option value="30">30</option>
      <option value="60">60</option>
    </select>

    <!-- Character Voice Options -->
    <label for="voice" class="mt-6 block font-semibold text-gray-700">Choose Character Voice</label>
    <select name="voice" id="voice" aria-label="Choose character voice" required>
      <optgroup label="Female Voices">
        <option value="female_1">Female 1</option>
        <option value="female_2">Female 2</option>
        <option value="female_3">Female 3</option>
        <option value="female_4">Female 4</option>
      </optgroup>
      <optgroup label="Male Voices">
        <option value="male_1">Male 1</option>
        <option value="male_2">Male 2</option>
        <option value="male_3">Male 3</option>
        <option value="male_4">Male 4</option>
      </optgroup>
    </select>

    <!-- Dialogue or Monologue -->
    <fieldset class="mt-6" aria-labelledby="speech-type-label">
      <legend id="speech-type-label" class="font-semibold text-gray-700 mb-2">Select Speech Type</legend>
      <div class="radio-group" role="radiogroup" aria-describedby="speech-type-label">
        <input type="radio" id="dialogue" name="speech" value="dialogue" required />
        <label for="dialogue" tabindex="0">Dialogue</label>

        <input type="radio" id="monologue" name="speech" value="monologue" />
        <label for="monologue" tabindex="0">Monologue</label>
      </div>
    </fieldset>

    <button type="submit" class="btn-create" aria-live="polite" aria-label="Create your video or picture with chosen options">Create Video/Picture</button>
  </form>

  <!-- Result preview -->
  <div id="result-container" aria-live="polite" aria-atomic="true" aria-relevant="additions removals">
    <div id="result-preview" aria-label="Preview of the generated content">
      <span>No content created yet.</span>
    </div>
    <button id="download-button" aria-label="Download the generated video or picture">Download</button>
  </div>
</section>

<!-- About Me Section -->
<section id="about" role="contentinfo" tabindex="0" aria-label="About me section" class="mt-6 p-6 rounded-lg" >
  <h2>About Me</h2>
  <p>My name is <strong>Goshan</strong>. I am studying at the University of Halabja, majoring in English.</p>
  <p>My Facebook: <a href="https://www.facebook.com/goshan.mzafar" target="_blank" rel="noopener noreferrer">goshan.mzafar</a></p>
  <p>For your feedback and suggestions, feel free to message me.</p>
</section>

  </main>  <!-- Login Modal -->  <div id="login-modal" r# 2-2-1
