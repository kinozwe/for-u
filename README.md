<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>For My Love</title>
  
  <!-- Load required CSS libraries -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/css/bootstrap.min.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.css">
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick-theme.css">
  <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Cormorant+Garamond:wght@300;400;600&display=swap">
  
  <style id="app-style">
    :root {
      --primary-color: #f8e8e8;
      --secondary-color: #e6c9c9;
      --accent-color: #d4a8a8;
      --text-color: #5a4444;
      --light-text: #8a7777;
      --white: #ffffff;
      --shadow: rgba(0, 0, 0, 0.05);
    }
    
    body {
      font-family: 'Cormorant Garamond', serif;
      background-color: var(--primary-color);
      color: var(--text-color);
      line-height: 1.6;
      padding: 0;
      margin: 0;
      min-height: 100vh;
    }
    
    .container {
      padding: 2rem 1rem;
      max-width: 1200px;
      margin: 0 auto;
    }
    
    h1 {
      font-family: 'Playfair Display', serif;
      text-align: center;
      font-size: 2.5rem;
      margin-bottom: 2rem;
      color: var(--text-color);
      font-weight: 700;
      letter-spacing: 1px;
    }
    
    /* Elegant divider */
    .divider {
      display: flex;
      align-items: center;
      text-align: center;
      margin: 1.5rem 0;
    }
    
    .divider::before,
    .divider::after {
      content: '';
      flex: 1;
      border-bottom: 1px solid var(--accent-color);
    }
    
    .divider::before {
      margin-right: 1rem;
    }
    
    .divider::after {
      margin-left: 1rem;
    }
    
    .divider-icon {
      color: var(--accent-color);
      font-size: 1.5rem;
      padding: 0 1rem;
    }
    
    /* Slideshow styles */
    .slideshow-container {
      margin-bottom: 2rem;
      position: relative;
      background-color: var(--white);
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 5px 15px var(--shadow);
    }
    
    .slideshow {
      width: 100%;
      position: relative;
    }
    
    .slide {
      height: 400px;
      display: flex !important;
      align-items: center;
      justify-content: center;
      position: relative;
    }
    
    .slide img {
      max-width: 100%;
      max-height: 100%;
      object-fit: contain;
    }
    
    .slide-loading {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: rgba(255,255,255,0.8);
      z-index: 10;
    }
    
    .slick-arrow {
      width: 40px;
      height: 40px;
      z-index: 10;
    }
    
    .slick-prev:before, 
    .slick-next:before {
      color: var(--accent-color);
      font-size: 24px;
    }
    
    .slick-dots li button:before {
      color: var(--accent-color);
    }
    
    /* Message boxes */
    .message-container {
      display: flex;
      flex-wrap: wrap;
      gap: 1.5rem;
      margin-bottom: 2rem;
    }
    
    .message-box {
      flex: 1 1 calc(33.333% - 1.5rem); /* Make 3 boxes per row on larger screens */
      min-width: 250px;
      position: relative;
      background-color: var(--white);
      padding: 1.5rem;
      border-radius: 8px;
      box-shadow: 0 5px 15px var(--shadow);
      transition: all 0.3s ease;
      min-height: 120px;
    }
    
    .message-box:hover {
      transform: translateY(-5px);
      box-shadow: 0 8px 20px var(--shadow);
    }
    
    .message-content {
      width: 100%;
      height: 100%;
      border: none;
      outline: none;
      background: transparent;
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
      color: var(--text-color);
      resize: none;
      padding: 0;
    }
    
    .message-label {
      position: absolute;
      top: -10px;
      left: 15px;
      background-color: var(--white);
      padding: 0 10px;
      font-size: 0.9rem;
      color: var(--light-text);
    }
    
    /* Audio player - Medium style */
    .audio-container {
      margin-bottom: 2rem;
      padding: 1.5rem 2rem;
      background-color: var(--white); /* Light background instead of Spotify dark */
      border-radius: 8px;
      box-shadow: 0 5px 15px var(--shadow);
      position: relative;
      color: var(--text-color); /* Use theme text color instead of white */
      display: flex;
      align-items: center;
    }
    
    .album-art {
      width: 40px; /* Smaller album art */
      height: 40px;
      border-radius: 4px;
      margin-right: 1rem;
      flex-shrink: 0;
      background-size: cover;
      background-position: center;
      box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* Lighter shadow */
    }
    
    .audio-controls {
      flex-grow: 1;
      display: flex;
      flex-direction: row; /* Changed to row for single-line layout */
      align-items: center;
      gap: 15px;
    }
    
    .audio-title {
      font-size: 1rem;
      color: var(--text-color);
      font-weight: 400;
      margin-bottom: 0;
      white-space: nowrap;
      overflow: hidden;
      text-overflow: ellipsis;
    }
    
    .player-wrapper {
      flex-grow: 1;
      position: relative;
    }
    
    .audio-player {
      width: 100%;
      height: 32px;
      -webkit-appearance: none;
      background: transparent;
    }
    
    /* Medium-style minimal audio player controls */
    .audio-player::-webkit-media-controls-panel {
      background-color: transparent;
    }
    
    .audio-player::-webkit-media-controls-play-button {
      background-color: var(--accent-color);
      border-radius: 50%;
      transform: scale(1);
    }
    
    .audio-player::-webkit-media-controls-play-button:hover {
      background-color: var(--accent-color);
    }
    
    .audio-player::-webkit-media-controls-timeline {
      background-color: var(--secondary-color);
      border-radius: 2px;
      height: 3px;
    }
    
    .audio-player::-webkit-media-controls-current-time-display,
    .audio-player::-webkit-media-controls-time-remaining-display {
      color: var(--light-text);
      font-size: 0.9rem;
    }
    
    .audio-player::-webkit-media-controls-volume-slider {
      background-color: var(--secondary-color);
      border-radius: 2px;
      padding: 0;
    }
    
    /* Video player */
    .video-container {
      margin-bottom: 2rem;
      position: relative;
      width: 100%;
      max-width: 500px;
      margin-left: auto;
      margin-right: auto;
      background-color: var(--white);
      border-radius: 8px;
      box-shadow: 0 5px 15px var(--shadow);
      overflow: hidden;
    }
    
    .video-wrapper {
      position: relative;
      padding-bottom: 177.77%; /* 16:9 aspect ratio */
      height: 0;
    }
    
    .video-wrapper video {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      object-fit: contain;
      background-color: #000;
    }
    
    .video-play-button {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      width: 80px;
      height: 80px;
      background-color: rgba(255, 255, 255, 0.7);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      cursor: pointer;
      z-index: 10;
      transition: all 0.3s ease;
    }
    
    .video-play-button:hover {
      background-color: rgba(255, 255, 255, 0.9);
    }
    
    .video-play-icon {
      color: var(--accent-color);
      font-size: 2rem;
    }
    
    .video-loading {
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      display: flex;
      align-items: center;
      justify-content: center;
      background-color: rgba(0,0,0,0.5);
      z-index: 9;
    }
    
    /* Heartfelt message area */
    .heartfelt-container {
      padding: 1.5rem;
      background-color: var(--white);
      border-radius: 8px;
      box-shadow: 0 5px 15px var(--shadow);
      position: relative;
    }
    
    .heartfelt-message {
      width: 100%;
      min-height: 200px;
      border: none;
      outline: none;
      background: transparent;
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
      color: var(--text-color);
      resize: none;
      padding: 0;
      line-height: 1.7;
    }
    
    /* Responsive adjustments */
    @media (max-width: 992px) {
      .message-box {
        flex: 1 1 calc(50% - 1.5rem); /* 2 boxes per row on medium screens */
      }
    }
    
    @media (max-width: 768px) {
      h1 {
        font-size: 2rem;
      }
      
      .slide {
        height: 300px;
      }
      
      .message-box {
        flex: 100%;
      }
    }
    
    @media (max-width: 480px) {
      h1 {
        font-size: 1.8rem;
      }
      
      .slide {
        height: 250px;
      }
      
      .video-play-button {
        width: 60px;
        height: 60px;
      }
      
      .video-play-icon {
        font-size: 1.5rem;
      }
      
      .audio-container {
        flex-direction: row; /* Keep as row even on mobile */
        padding: 1rem 1.2rem;
        gap: 10px;
      }
      
      .album-art {
        margin-right: 0.8rem;
        width: 32px;
        height: 32px;
      }
      
      .audio-title {
        font-size: 0.9rem;
        max-width: 120px;
      }
    }
    
    /* Focus and hover styles */
    .message-content:focus,
    .heartfelt-message:focus {
      border: none;
      outline: 2px solid var(--accent-color);
      border-radius: 4px;
    }
    
    /* Animation classes */
    .fade-in {
      animation: fadeIn 1s ease-in-out;
    }
    
    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }
    
    /* Vintage accents */
    .vintage-accent {
      position: absolute;
      color: var(--accent-color);
      opacity: 0.1;
      font-size: 2rem;
    }
    
    .accent-top-left {
      top: 10px;
      left: 10px;
    }
    
    .accent-bottom-right {
      bottom: 10px;
      right: 10px;
    }
  </style>
</head>
<body>
  <div class="container fade-in">
    <h1 class="animate__animated animate__fadeIn">Welcome to my website for you</h1>
    
    <div class="divider">
      <span class="divider-icon"><i class="fas fa-heart"></i></span>
    </div>
    
    <!-- Slideshow Section -->
    <div class="slideshow-container">
      <div class="slideshow">
        <div class="slide">
          <img src="494812888_1045256953773136_4894748904934657062_n.jpg" alt="Romantic Rose">
          <div class="slide-loading d-none">
            <div class="spinner-border text-danger" role="status">
              <span class="visually-hidden">Loading...</span>
            </div>
          </div>
        </div>
        <div class="slide">
          <img src="13d7e96f-be9e-4aea-850e-1c43f58845d2.jpg" alt="Heart in Sunset">
          <div class="slide-loading d-none">
            <div class="spinner-border text-danger" role="status">
              <span class="visually-hidden">Loading...</span>
            </div>
          </div>
        </div>
        <div class="slide">
          <img src="494820234_1232715904896880_5278549943553628743_n.jpg" alt="Woman in Field">
          <div class="slide-loading d-none">
            <div class="spinner-border text-danger" role="status">
              <span class="visually-hidden">Loading...</span>
            </div>
          </div>
        </div>
        <div class="slide">
          <img src="494820631_1801867853696871_2930474522118545996_n.jpg" alt="Couple at Train Station">
          <div class="slide-loading d-none">
            <div class="spinner-border text-danger" role="status">
              <span class="visually-hidden">Loading...</span>
            </div>
          </div>
        </div>
        <div class="slide">
          <img src="494821917_1726056538111428_5105563148100902075_n.jpg" alt="Couple Holding Hands">
          <div class="slide-loading d-none">
            <div class="spinner-border text-danger" role="status">
              <span class="visually-hidden">Loading...</span>
            </div>
          </div>
        </div>
        <div class="slide">
            <img src="484030490_8687439814689614_4621310961642498727_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="494859827_1238232771346764_3938694209127380116_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="500408998_1397364688249772_1238878991960246945_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="494823175_1197211158392336_731855079901905144_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="494363320_1392032341923575_660939968614982830_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="494816014_687538957436722_5125277335889016147_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="494819475_1241618980923464_5783791144515546358_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="494829512_993304966283399_2736871728453572163_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
          <div class="slide">
            <img src="494820396_1167673745043030_8883945723910405449_n.jpg" alt="Couple Holding Hands">
            <div class="slide-loading d-none">
              <div class="spinner-border text-danger" role="status">
                <span class="visually-hidden">Loading...</span>
              </div>
            </div>
          </div>
        <!-- Added new slide here -->
        <div class="slide">
          <img src="495267461_667502426271713_1989818902738541413_n.jpg" alt="Love Symbol">
          <div class="slide-loading d-none">
            <div class="spinner-border text-danger" role="status">
              <span class="visually-hidden">Loading...</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    
   <!-- Short Message Boxes -->
<div class="message-container">
    <div class="message-box" style="position: relative; padding: 20px; border: 1px solid #ccc; background: #f9f9f9;">
      <span class="vintage-accent accent-top-left"><i class="fas fa-quote-left"></i></span>
      <span class="message-label" style="display: block; font-weight: bold; margin-bottom: 10px;"></span>
      
      <div class="message-content" style="
        white-space: pre-wrap;
        line-height: 1.6;
        font-size: 16px;
        background: none;
        border: none;
        padding: 0;
      ">
        i love your eyes, but i like mine better, because without mine i wouldn't be able to see yours..... SHHHEESSSSHHHHH
      </div>
  
      <span class="vintage-accent accent-bottom-right"><i class="fas fa-quote-right"></i></span>
    </div>
  </div>
  
      
     <!-- Short Message Boxes -->
<div class="message-container">
    <div class="message-box" style="position: relative; padding: 20px; border: 1px solid #ccc; background: #f9f9f9;">
      <span class="vintage-accent accent-top-left"><i class="fas fa-quote-left"></i></span>
      <span class="message-label" style="display: block; font-weight: bold; margin-bottom: 10px;"></span>
      
      <div class="message-content" style="
        white-space: pre-wrap;
        line-height: 1.6;
        font-size: 16px;
        background: none;
        border: none;
        padding: 0;
      ">
        meeting you as the best thing in my life and choosing to love you was the best decision I've ever made.
      </div>
  
      <span class="vintage-accent accent-bottom-right"><i class="fas fa-quote-right"></i></span>
    </div>
  </div>
  
      
     <!-- Short Message Boxes -->
<div class="message-container">
    <div class="message-box" style="position: relative; padding: 20px; border: 1px solid #ccc; background: #f9f9f9;">
      <span class="vintage-accent accent-top-left"><i class="fas fa-quote-left"></i></span>
      <span class="message-label" style="display: block; font-weight: bold; margin-bottom: 10px;"></span>
      
      <div class="message-content" style="
        white-space: pre-wrap;
        line-height: 1.6;
        font-size: 16px;
        background: none;
        border: none;
        padding: 0;
      ">
       for the past two months, I've had feelings for you that have continued to grow stronger with each passing day. 
      </div>
  
      <span class="vintage-accent accent-bottom-right"><i class="fas fa-quote-right"></i></span>
    </div>
  </div>
  
      
      <!-- Short Message Boxes -->
<div class="message-container">
    <div class="message-box" style="position: relative; padding: 20px; border: 1px solid #ccc; background: #f9f9f9;">
      <span class="vintage-accent accent-top-left"><i class="fas fa-quote-left"></i></span>
      <span class="message-label" style="display: block; font-weight: bold; margin-bottom: 10px;"></span>
      
      <div class="message-content" style="
        white-space: pre-wrap;
        line-height: 1.6;
        font-size: 16px;
        background: none;
        border: none;
        padding: 0;
      ">
        as long as I'm here, you will have someone who likes you more than anything. 
        You will always have a number one supporter who always supports you and I'm always proud of you. 
      </div>
  
      <span class="vintage-accent accent-bottom-right"><i class="fas fa-quote-right"></i></span>
    </div>
  </div>
  
      
      <!-- Short Message Boxes -->
<div class="message-container">
    <div class="message-box" style="position: relative; padding: 20px; border: 1px solid #ccc; background: #f9f9f9;">
      <span class="vintage-accent accent-top-left"><i class="fas fa-quote-left"></i></span>
      <span class="message-label" style="display: block; font-weight: bold; margin-bottom: 10px;"></span>
      
      <div class="message-content" style="
        white-space: pre-wrap;
        line-height: 1.6;
        font-size: 16px;
        background: none;
        border: none;
        padding: 0;
      ">
       for you I would, I'm willing to fo everything for you without any doubts and hesitations. I want to show you that not everyone leaves. 
       I'll be the person that will stay through your ups and downs


      </div>
  
      <span class="vintage-accent accent-bottom-right"><i class="fas fa-quote-right"></i></span>
    </div>
  </div>
  
    
        <!-- Spotify Embed iframe -->
        <iframe style="border-radius:12px" 
                src="https://open.spotify.com/embed/track/2dMQ4FbQcrEWVFK6NIFjrl?utm_source=generator" 
                width="100%" 
                height="80" 
                frameborder="0" 
                allowtransparency="true" 
                allow="encrypted-media">
        </iframe>
      </div>
    </div>
  </div>
  
    
    <div class="divider">
      <span class="divider-icon"><i class="fas fa-heart"></i></span>
    </div>
    
    <!-- Heartfelt Message -->
    <div class="heartfelt-container">
      <span class="vintage-accent accent-top-left"><i class="fas fa-feather-alt"></i></span>
      <textarea id="heartfeltMessage" class="heartfelt-message" placeholder="I'm willing to risk everything and chase after you no matter how uncertain the path. you are worth every fear i must face and every challenge i must overcome. my heart longs for with a love so deep it defies reason, and ill pursue you with unwavering devotion. For you I'd cross the storms and embrace the unknown because a life without a risk I'm not willing to take. every step, ill prove that my love for you is fearless and true and I will also prove to you that not everyone leaves, that not every love faded or falters. I'll stay though the storms thorough the high and lows, and though the moment when the world feels like it's falling apart you deserve a love that's constant unwavering and true and I'll be the one to show u that kind of love I'm here to stay to be your safe heaven and to remind you every single day that some hearts are ment to stay forever. You are the most precious person in my life, you are the source of my happiness and joy. I'll still like you and I'll stay, even after seeing how unstable you are, how quickly your mood changes, how sensitive you are, when you have ghosting phase and how you tend to overthink even the smallest things. No matter what you think of yourself, I will never ever think that you are hard to handle because for you, I will do anything and is ready to risk everything. I'll be the greatest fan of your life.

      "></textarea>
      <span class="vintage-accent accent-bottom-right"><i class="fas fa-feather-alt"></i></span>
    </div>
  </div>

  <!-- Load required JS libraries -->
  <script src="https://code.jquery.com/jquery-3.7.1.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.2/dist/js/bootstrap.bundle.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/slick-carousel@1.8.1/slick/slick.min.js"></script>
  
  <script id="app-script">
    $(document).ready(function() {
      // Initialize slideshow
      $('.slideshow').slick({
        autoplay: true,
        autoplaySpeed: 3000,
        dots: true,
        arrows: true,
        infinite: true,
        speed: 500,
        fade: true,
        cssEase: 'linear'
      });
      
      // Simulate image loading
      $('.slide').each(function() {
        const img = $(this).find('img')[0];
        const loadingDiv = $(this).find('.slide-loading');
        
        if (img.complete) {
          loadingDiv.addClass('d-none');
        } else {
          loadingDiv.removeClass('d-none');
          $(img).on('load', function() {
            loadingDiv.addClass('d-none');
          });
        }
      });
      
      // Load saved messages from localStorage
      if (localStorage.getItem('message1')) {
        $('#message1').val(localStorage.getItem('message1'));
      }
      
      if (localStorage.getItem('message2')) {
        $('#message2').val(localStorage.getItem('message2'));
      }
      
      // Add localStorage handling for new message boxes
      if (localStorage.getItem('message3')) {
        $('#message3').val(localStorage.getItem('message3'));
      }
      
      if (localStorage.getItem('message4')) {
        $('#message4').val(localStorage.getItem('message4'));
      }
      
      if (localStorage.getItem('message5')) {
        $('#message5').val(localStorage.getItem('message5'));
      }
      
      if (localStorage.getItem('heartfeltMessage')) {
        $('#heartfeltMessage').val(localStorage.getItem('heartfeltMessage'));
      }
      
      // Save messages to localStorage when changed
      $('#message1').on('input', function() {
        localStorage.setItem('message1', $(this).val());
      });
      
      $('#message2').on('input', function() {
        localStorage.setItem('message2', $(this).val());
      });
      
      // Add event handlers for new message boxes
      $('#message3').on('input', function() {
        localStorage.setItem('message3', $(this).val());
      });
      
      $('#message4').on('input', function() {
        localStorage.setItem('message4', $(this).val());
      });
      
      $('#message5').on('input', function() {
        localStorage.setItem('message5', $(this).val());
      });
      
      $('#heartfeltMessage').on('input', function() {
        localStorage.setItem('heartfeltMessage', $(this).val());
      });
      
      // Video player functionality
      const videoPlayer = document.getElementById('videoPlayer');
      const playButton = document.getElementById('videoPlayButton');
      const videoLoading = document.getElementById('videoLoading');
      
      playButton.addEventListener('click', function() {
        videoLoading.classList.remove('d-none');
        
        // Simulate loading time
        setTimeout(function() {
          videoLoading.classList.add('d-none');
          videoPlayer.play();
          playButton.style.display = 'none';
        }, 1000);
      });
      
      videoPlayer.addEventListener('pause', function() {
        playButton.style.display = 'flex';
      });
      
      videoPlayer.addEventListener('ended', function() {
        playButton.style.display = 'flex';
      });
      
      // Adjust textarea heights automatically
      function autoResizeTextarea(textarea) {
        textarea.style.height = 'auto';
        textarea.style.height = textarea.scrollHeight + 'px';
      }
      
      const textareas = document.querySelectorAll('textarea');
      textareas.forEach(textarea => {
        autoResizeTextarea(textarea);
        textarea.addEventListener('input', function() {
          autoResizeTextarea(this);
        });
      });
      
      // Ensure audio starts playing
      const audioPlayer = document.getElementById('audioPlayer');
      audioPlayer.volume = 0.5; // Set to half volume by default
    });
  </script>
</body>
</html>
