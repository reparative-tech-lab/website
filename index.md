---
layout: page
home: true
title: Reparative Technology Lab
---

<div class="bg-[#FBFCF4]">

  <div class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem] bg-[#FBFCF4]">
    <div id="hero-wrap" class="relative w-full">

      <!-- Image Background -->
      <!-- <img src="{{ '/assets/imgs/bg.jpg' | relative_url }}" class="absolute inset-0 w-full h-full object-cover opacity-[0.8] z-0"> /> -->

      <style>
        @font-face {
          font-family: 'Tilt Prism';
          src: url('{{ "/assets/css/TiltPrism-Regular-VariableFont.ttf" | relative_url }}') format('truetype');
        }
        #rt-logo-text {
          font-family: 'Tilt Prism', sans-serif;
          font-size: 340px;
          color: #664545;
          font-variation-settings: 'XROT' 0, 'YROT' 0;
          line-height: 1;
          display: block;
        }
        @media (max-width: 768px) {
          #rt-logo-text { font-size: 120px; }
        }
      </style>

      <!-- Header over Image -->
      <header id="site-header" class="sticky top-0 left-0 w-full z-20 bg-transparent text-[#2A2020] py-6">
          <div id="site-header-inner" class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem]">   

            <div id="site-header-inner-fixed" class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem]">   

                <div class="grid grid-cols-1 lg:grid-cols-12 gap-5 md:pb-0 lg:pb-0">
                  <div class="lg:col-span-6 flex items-center justify-between">
                    <a href="{{ '/' | relative_url }}" aria-label="Reparative Technology Lab">
                      <span id="rt-logo-text">RT</span>
                    </a>
                    <button id="menu-toggle" class="lg:hidden ml-4 p-2 rounded" aria-expanded="false" aria-controls="primary-nav" aria-label="Toggle navigation">
                      <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-[#2A2020]" fill="none" viewBox="0 0 24 24" stroke="currentColor" stroke-width="2">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M4 6h16M4 12h16M4 18h16" />
                      </svg>
                    </button>
                  </div>
                  <ul id="primary-nav" class="lg:col-span-6 hidden lg:flex flex-col lg:flex-row lg:justify-end  space-y-1 lg:space-y-0 lg:space-x-8 lg:mt-0">

                    <li>
                      <a href="{{ '/#our-approach' | relative_url }}" class="text-[#2A2020] text-lg font-bold hover:text-gray-500">Our Approach</a>
                    </li>
                    <li>
                      <a href="{{ '/#our-work' | relative_url }}" class="text-[#2A2020] text-lg font-bold  hover:text-gray-500">Our Work</a>
                    </li>
                    <li>
                      <a href="{{ '/#team' | relative_url }}" class="text-[#2A2020] text-lg font-bold hover:text-gray-500">Team</a>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
      </header>
      <!-- Hero Section -->
      <div id="hero" class="relative z-10 w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem] py-5 md:py-10">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-5">
          <div class="lg:col-span-7">
            <p class="text-[#2A2020] text-3xl md:text-4xl">
              <span class="text-[#664545] italic">The Reparative Technology Lab</span> studies urban technologies, collects data, and builds tools and visualizations to expose the inequities behind urban technologies and contribute to repairing the relationships by actively acknowledging and addressing past harms.
            </p>
          </div>
        </div>
      </div>

      <!-- Research Theme Section -->
      <section class="relative z-10 w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem] py-6 md:pt-8 md:pb-10">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-5 mb-2">
          <div class="lg:col-span-12">
            <h1 class="text-[#664545] text-xl font-bold">Research Themes</h1>
          </div>
        </div>
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-5">

          {% for theme_hash in site.data.research_theme %}

            {% assign theme = theme_hash[1] %}
            <div class="lg:col-span-4 mb-4 lg:mb-0">
              <h2 class="text-[#2A2020] text-xl md:text-xl font-bold mb-2">{{ theme.title }}</h2>
              <p class="text-[#2A2020] text-xl">{{ theme.description }}</p>
            </div>
          {% endfor %}
        </div>
      </section>

      <script>
      /* ============================================================
         Hero interactive background — "Stitching the City"
         Urban data nodes connected by repair threads.
         Mouse hover: kintsugi-gold shimmer heals nearby connections.
         Click / tap: repair wave ripples outward from touch point.
         ============================================================ */
      (function() {
        var heroWrap = document.getElementById('hero-wrap');
        if (!heroWrap) return;

        var canvas = document.createElement('canvas');
        canvas.setAttribute('aria-hidden', 'true');
        canvas.style.cssText = 'position:absolute;top:0;left:0;width:100%;height:100%;z-index:1;pointer-events:none;display:block;';
        heroWrap.insertBefore(canvas, heroWrap.firstChild);

        var ctx = canvas.getContext('2d');
        var W = 0, H = 0;
        var nodes = [], edges = [];
        var mouse = { x: -9999, y: -9999 };
        var waves = [];
        var running = true;
        var resizeTimer;

        var CELL, MAX_DIST, MOUSE_RADIUS;

        function cfg() {
          var mobile = window.innerWidth < 768;
          CELL = mobile ? 110 : 80;
          MAX_DIST = CELL * 1.65;
          MOUSE_RADIUS = mobile ? 120 : 195;
        }

        function buildGrid() {
          cfg();
          nodes = [];
          edges = [];
          var cols = Math.ceil(W / CELL) + 2;
          var rows = Math.ceil(H / CELL) + 2;

          for (var r = -1; r < rows; r++) {
            for (var c = -1; c < cols; c++) {
              nodes.push({
                x: (c + 0.5) * CELL + (Math.random() * 2 - 1) * CELL * 0.44,
                y: (r + 0.5) * CELL + (Math.random() * 2 - 1) * CELL * 0.44,
                phase: Math.random() * Math.PI * 2
              });
            }
          }

          for (var i = 0; i < nodes.length; i++) {
            for (var j = i + 1; j < nodes.length; j++) {
              var dx = nodes[i].x - nodes[j].x;
              var dy = nodes[i].y - nodes[j].y;
              var d = Math.sqrt(dx * dx + dy * dy);
              if (d < MAX_DIST) {
                edges.push({
                  a: i, b: j, d: d,
                  repair: 0.12 + Math.random() * 0.58,
                  rest:   0.22 + Math.random() * 0.46,
                  phase:  Math.random() * Math.PI * 2,
                  lit: 0
                });
              }
            }
          }
        }

        function resize() {
          W = canvas.width  = heroWrap.offsetWidth;
          H = canvas.height = heroWrap.offsetHeight;
          buildGrid();
        }

        if (window.IntersectionObserver) {
          new IntersectionObserver(function(entries) {
            running = entries[0].isIntersecting;
          }, { threshold: 0 }).observe(heroWrap);
        }

        function draw(ts) {
          ctx.clearRect(0, 0, W, H);

          /* ---- process repair waves (from clicks/taps) ---- */
          for (var wi = waves.length - 1; wi >= 0; wi--) {
            var wv = waves[wi];
            wv.r  += 5.5;
            wv.a  *= 0.963;
            if (wv.a < 0.007) { waves.splice(wi, 1); continue; }

            for (var i = 0; i < edges.length; i++) {
              var e = edges[i];
              var na = nodes[e.a], nb = nodes[e.b];
              var ecx = (na.x + nb.x) * 0.5, ecy = (na.y + nb.y) * 0.5;
              var dd = Math.sqrt((ecx - wv.x) * (ecx - wv.x) + (ecy - wv.y) * (ecy - wv.y));
              var ring = Math.abs(dd - wv.r);
              if (ring < 38) {
                var fi = (1 - ring / 38) * wv.a;
                e.repair = Math.min(1, e.repair + fi * 0.20);
                e.lit    = Math.min(1, e.lit    + fi * 0.55);
              }
            }
          }

          /* ---- draw edges (repair threads) ---- */
          for (var i = 0; i < edges.length; i++) {
            var e = edges[i];
            var na = nodes[e.a], nb = nodes[e.b];

            var inA = na.x > -4 && na.x < W + 4 && na.y > -4 && na.y < H + 4;
            var inB = nb.x > -4 && nb.x < W + 4 && nb.y > -4 && nb.y < H + 4;
            if (!inA && !inB) continue;

            var ecx = (na.x + nb.x) * 0.5, ecy = (na.y + nb.y) * 0.5;
            var mdx = ecx - mouse.x, mdy = ecy - mouse.y;
            var md  = Math.sqrt(mdx * mdx + mdy * mdy);
            var mi  = Math.max(0, 1 - md / MOUSE_RADIUS);
            mi = mi * mi;

            if (mi > 0) {
              e.lit    = Math.min(1, e.lit + mi * 0.075);
              e.repair = Math.min(1, e.repair + mi * 0.010);
            } else {
              e.lit    = Math.max(0, e.lit - 0.024);
              e.repair += (e.rest - e.repair) * 0.00042;
            }

            var shimmer = Math.sin(ts / 580 + e.phase) * 0.018;
            var alpha   = 0.038 + e.repair * 0.072 + e.lit * 0.105 + shimmer;
            alpha = Math.max(0, Math.min(0.23, alpha));

            /* thread grows outward from center as repair increases */
            var t  = 0.32 + e.repair * 0.68;
            var hx = (nb.x - na.x) * (1 - t) * 0.5;
            var hy = (nb.y - na.y) * (1 - t) * 0.5;
            var x1 = na.x + hx, y1 = na.y + hy;
            var x2 = nb.x - hx, y2 = nb.y - hy;

            /* primary thread */
            ctx.beginPath();
            ctx.moveTo(x1, y1);
            ctx.lineTo(x2, y2);
            ctx.strokeStyle = 'rgba(102,69,69,' + alpha.toFixed(3) + ')';
            ctx.lineWidth   = 0.5 + e.lit * 0.95;
            ctx.stroke();

            /* kintsugi gold shimmer for lit threads */
            if (e.lit > 0.07) {
              ctx.beginPath();
              ctx.moveTo(x1, y1);
              ctx.lineTo(x2, y2);
              ctx.strokeStyle = 'rgba(193,149,88,' + ((e.lit - 0.07) * 0.16).toFixed(3) + ')';
              ctx.lineWidth   = 0.55;
              ctx.stroke();
            }
          }

          /* ---- draw nodes ---- */
          for (var i = 0; i < nodes.length; i++) {
            var n = nodes[i];
            if (n.x < -4 || n.x > W + 4 || n.y < -4 || n.y > H + 4) continue;

            var mdx = n.x - mouse.x, mdy = n.y - mouse.y;
            var md  = Math.sqrt(mdx * mdx + mdy * mdy);
            var mi  = Math.max(0, 1 - md / MOUSE_RADIUS);
            mi = mi * mi;

            var pulse = Math.sin(ts / 1500 + n.phase) * 0.026;
            var alpha = 0.068 + mi * 0.235 + pulse;
            var r     = 1.2 + mi * 2.4;

            ctx.beginPath();
            ctx.arc(n.x, n.y, r, 0, Math.PI * 2);
            ctx.fillStyle = 'rgba(102,69,69,' + Math.min(0.38, Math.max(0, alpha)).toFixed(3) + ')';
            ctx.fill();

            if (mi > 0.18) {
              ctx.beginPath();
              ctx.arc(n.x, n.y, r * 3.0, 0, Math.PI * 2);
              ctx.strokeStyle = 'rgba(193,149,88,' + ((mi - 0.18) * 0.13).toFixed(3) + ')';
              ctx.lineWidth   = 0.65;
              ctx.stroke();
            }
          }

          /* ---- draw expanding wave rings ---- */
          for (var wi = 0; wi < waves.length; wi++) {
            var wv = waves[wi];
            ctx.beginPath();
            ctx.arc(wv.x, wv.y, wv.r, 0, Math.PI * 2);
            ctx.strokeStyle = 'rgba(193,149,88,' + (wv.a * 0.17).toFixed(3) + ')';
            ctx.lineWidth   = 1.1;
            ctx.stroke();
          }
        }

        function loop(ts) {
          if (running) draw(ts);
          requestAnimationFrame(loop);
        }

        /* ---- input: mouse ---- */
        heroWrap.addEventListener('mousemove', function(e) {
          var rect = heroWrap.getBoundingClientRect();
          mouse.x = e.clientX - rect.left;
          mouse.y = e.clientY - rect.top;
        }, { passive: true });

        heroWrap.addEventListener('mouseleave', function() {
          mouse.x = -9999; mouse.y = -9999;
        }, { passive: true });

        heroWrap.addEventListener('click', function(e) {
          var rect = heroWrap.getBoundingClientRect();
          waves.push({ x: e.clientX - rect.left, y: e.clientY - rect.top, r: 0, a: 1 });
        }, { passive: true });

        /* ---- input: touch ---- */
        heroWrap.addEventListener('touchstart', function(e) {
          var rect = heroWrap.getBoundingClientRect();
          var t = e.touches[0];
          mouse.x = t.clientX - rect.left;
          mouse.y = t.clientY - rect.top;
          waves.push({ x: mouse.x, y: mouse.y, r: 0, a: 1 });
        }, { passive: true });

        heroWrap.addEventListener('touchmove', function(e) {
          var rect = heroWrap.getBoundingClientRect();
          var t = e.touches[0];
          mouse.x = t.clientX - rect.left;
          mouse.y = t.clientY - rect.top;
        }, { passive: true });

        heroWrap.addEventListener('touchend', function() {
          mouse.x = -9999; mouse.y = -9999;
        }, { passive: true });

        window.addEventListener('resize', function() {
          clearTimeout(resizeTimer);
          resizeTimer = setTimeout(resize, 120);
        });

        resize();
        requestAnimationFrame(loop);
      })();
      </script>

    </div>

  </div>
</div>





    
<div class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem]">
    <!-- Our Approach Section -->
    <section id="our-approach" class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem] py-8 md:py-16">
      <h1 class="text-[#664545] text-xl font-bold">Our Approach</h1>
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-5 mb-4">
        <div class="lg:col-span-8">
          <p class="text-[#2A2020] text-3xl leading-tight">
            Our approach is to uncover how urban technologies formalize present-day outputs in ways that disconnect them from past wrongs — and, by doing so, to shift the work of creating urban technologies toward redress.
          </p>
        </div>
      </div>
    </section>

    <!-- Our Work Section -->
    <section id="our-work" class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem] py-6 md:py-8">
    <!-- Title and Filter Row -->
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-5 mb-4">
        <!-- OUR WORK Title (3 columns) -->
        <div class="lg:col-span-3">
          <h1 class="text-[#664545] text-xl font-bold  mb-3">Our Work</h1>
        
        
            <div class="relative">
              <svg class="pointer-events-none absolute left-0 top-1/2 -translate-y-1/2 text-[#664545]" width="18" height="18" viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
                <path d="M21 21l-4.35-4.35" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <circle cx="11" cy="11" r="7" stroke="currentColor" stroke-width="2"/>
              </svg>
              <input type="text" id="search-input" placeholder="Search..." class="w-full bg-transparent border-b border-[#AAA] text-[#2A2020] placeholder-gray-500 focus:outline-none focus:border-[#664545] pb-1 pt-1 pl-6" />
            </div>
            
        </div>
        
        <!-- Research Theme Filter (3 columns) -->
        <div class="lg:col-span-3">
          <h3 class="text-[#664545] text-xl font-bold mb-3">By Research Theme</h3>
          <div>
            {% for theme_hash in site.data.research_theme %}
              {% assign theme = theme_hash[1] %}
              {% assign theme_key = theme_hash[0] %}
              {% assign theme_count = 0 %}
              {% for work in site.works %}
                {% if work.research_themes and work.research_themes contains theme_key %}
                  {% assign theme_count = theme_count | plus: 1 %}
                {% endif %}
              {% endfor %}
              <button class="research-theme-btn text-left inline-block px-2 py-1 rounded-lg border border-[#BBBBBB] bg-[#FBFCF4] text-[#2A2020] text-sm font-medium mr-2 mb-1" data-theme="{{ theme_key }}"><span class="theme-title">{{ theme.title }}</span><span class="ml-1 text-[12px] opacity-70">({{ theme_count }})</span></button>
            {% endfor %}
          </div>
        </div>
        
        <!-- Tags Filter (3 columns) -->
        <div class="lg:col-span-6">
          <h3 class="text-[#664545] text-xl font-bold mb-3">By Tags</h3>
          <div>
            {% for tag_group in site.data.tags %}
              {% for tag in tag_group %}
                {% if tag != "# contribution type" and tag != "# methods" and tag != "# domain" %}
                  {% assign tag_count = 0 %}
                  {% for work in site.works %}
                    {% if work.tags and work.tags contains tag %}
                      {% assign tag_count = tag_count | plus: 1 %}
                    {% endif %}
                  {% endfor %}
                  <button class="tag-btn inline-block px-2 py-1 rounded-lg border border-[#BBBBBB] bg-[#FBFCF4] text-[#2A2020] text-sm font-medium mr-2 mb-1" data-tag="{{ tag }}">{{ tag }}<span class="ml-1 text-[12px] opacity-70">({{ tag_count }})</span></button>
                {% endif %}
              {% endfor %}
            {% endfor %}
          </div>
        </div>
      </div>
      
      
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-12 gap-5 py-5">
        {% assign sorted_works = site.works | sort: "year" | reverse %}
        {% for work in sorted_works %}
          {% assign url = work.external_url | default: work.url | relative_url | replace: 'index.html', '' %}
          <div class="sm:col-span-1 lg:col-span-3 mb-6 lg:mb-0 work">
            {% if work.images and work.images.size > 0 %}
              <div class="mb-4">
                <a href="{{ url }}" class="block">
                  {% capture work_thumb %}/imgs/works/{{ work.slug }}/{{ work.images.first }}{% endcapture %}
                  <img src="{{ work_thumb | relative_url }}" alt="{{ work.title }}" class="w-full object-cover rounded">
                </a>
              </div>
            {% endif %}
            
            <!-- Research Theme Buttons -->
            {% if work.research_themes %}
              <div class="flex flex-wrap gap-0 mb-1">
                {% for theme_key in work.research_themes %}
                  {% assign theme = site.data.research_theme[theme_key] %}
                  {% if theme %}
                    <span class="research-theme-btn inline-block px-2 py-1 rounded-lg border border-[#BBBBBB] bg-[#FBFCF4] text-[#2A2020] text-sm font-medium mr-2 mb-1">{{ theme.title }}</span>
                  {% endif %}
                {% endfor %}
              </div>
            {% endif %}
            
            <h3 class="text-[#2A2020] text-base md:text-xl font-bold mb-2 capitalize" style="line-height: 1.25;">
              <a href="{{ url }}" class="hover:text-gray-500">{{ work.title }}</a>
            </h3>
            
            <!-- Visit Website Link -->
            {% if work.website %}
              <div class="mb-2">
                <a href="{{ work.website }}" class="text-grat-400 hover:text-gray-500 text-sm transition-colors" target="_blank">
                  Visit Website →
                </a>
              </div>
            {% endif %}
            
            <!-- Publisher and DOI for articles -->
            {% if work.bibtex and work.bibtex.type == 'article' %}
              <div class="mb-2">
                {% if work.publisher %}
                  <p class="text-[#2A2020] text-sm">{{ work.publisher }}</p>
                {% endif %}
                {% if work.doi %}
                  <p class="text-[#2A2020] text-sm">
                    <a href="https://doi.org/{{ work.doi }}" class="hover:text-[#2A2020] transition-colors" target="_blank">
                      DOI: {{ work.doi }}
                    </a>
                  </p>
                {% endif %}
              </div>
            {% endif %}
            
            {% if work.authors %}
              <div class="flex items-center gap-2 mb-2">
                {% for author in work.authors %}
                  {% assign person = site.data.people[author] %}
                  {% if person.photo %}
                    <div class="flex items-center">
                      <img src="{{ '/imgs/people/' | append: person.photo | relative_url }}" alt="Profile of {{ person.first_name }}" class="w-6 h-6 rounded-full object-cover">
                    </div>
                  {% endif %}
                {% endfor %}
              </div>
            {% endif %}
          
          </div>
        {% endfor %}
      </div>
    </section>


    
    <!-- Team Section -->
    <section id="team" class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem] py-8 md:py-16">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-5 mb-4">
        <div class="lg:col-span-12">
          <h1 class="text-[#664545] text-xl font-bold">Team</h1>
        </div>
      </div>
      {% for person_hash in site.data.people %}
        {% assign person = person_hash[1] %}
        {% if person.type == 'current' %}
          <div class="grid grid-cols-1 lg:grid-cols-12 gap-5 mb-4">
            <!-- Profile Image (3 columns on desktop, full width on mobile) -->
            <div class="lg:col-span-3 flex justify-center lg:justify-start">
              <div class="w-full overflow-hidden">

                {% if person.photo %}
                <img src="{{ '/imgs/people/' | append: person.photo | relative_url }}" alt="Headshot of {{person.first_name}} {{person.last_name}}" class="w-full rounded-full ">
                {% endif %}
              </div>
            </div>
            
            <!-- Name and Affiliation (4 columns on desktop, full width on mobile) -->
            <div class="lg:col-span-4">
              {% if person.url %}
                <h3 class="text-[#2A2020] text-xl md:text-xl font-bold mb-2">
                  <a href="{{person.url}}" class="hover:text-gray-500">{{person.first_name}} {{person.last_name}}</a>
                </h3>
              {% else %}
                <h3 class="text-[#2A2020] text-xl md:text-xl font-bold mb-2">{{person.first_name}} {{person.last_name}}</h3>
              {% endif %}
              <p class="text-[#2A2020] text-lg md:text-base">{{person.title}}</p>
              <p class="text-gray-500 text-lg md:text-sm">{{person.affiliation}}</p>
            </div>
            
            <!-- Description (5 columns on desktop, full width on mobile) -->
            <div class="lg:col-span-5">
              {% if person.description %}
                <div class="text-[#2A2020] text-lg leading-[1.25]" id="person-desc">
                  {{ person.description | markdownify }}
                </div>
              {% endif %}
            </div>
          </div>
        {% endif %}
      {% endfor %}
    </section>

    <!-- SVG duotone filter + CSS for work thumbnails -->
    <svg xmlns="http://www.w3.org/2000/svg" style="position: absolute; width: 0; height: 0; overflow: hidden;" aria-hidden="true" focusable="false">
      <defs>
        <!-- Duotone mapping: shadows -> #614646 (primary), highlights -> #FBFCF4 (off-white) -->
        <filter id="duotone-7655ea-fafcf3" color-interpolation-filters="sRGB">
          <!-- Convert to grayscale (luminance) -->
          <feColorMatrix type="matrix" values="0.2126 0.7152 0.0722 0 0  0.2126 0.7152 0.0722 0 0  0.2126 0.7152 0.0722 0 0  0 0 0 1 0" result="gray" />
          <!-- Map grayscale to duotone colors by channel tables (black->#614646, white->#FBFCF4) -->
          <feComponentTransfer color-interpolation-filters="sRGB">
            <!-- R channel: 0 -> 97/255 (0.380392), 1 -> 250/255 (0.980392) -->
            <feFuncR type="table" tableValues="0.380392 0.980392" />
            <!-- G channel: 0 -> 70/255 (0.274510), 1 -> 252/255 (0.988235) -->
            <feFuncG type="table" tableValues="0.274510 0.988235" />
            <!-- B channel: 0 -> 70/255 (0.274510), 1 -> 243/255 (0.952941) -->
            <feFuncB type="table" tableValues="0.274510 0.952941" />
          </feComponentTransfer>
        </filter>
      </defs>
    </svg>

    <style>
      /* Apply duotone filter only to main work thumbnails */
      .work img.w-full {
        filter: url(#duotone-7655ea-fafcf3);
        -webkit-filter: url(#duotone-7655ea-fafcf3);
        /* Smoothly transition filter removal, radius changes, and transforms */
        transition: filter 220ms ease, -webkit-filter 220ms ease, border-radius 420ms ease, transform 220ms ease;
        /* Hint to browser about upcoming transforms for better performance */
        will-change: transform, filter;
        /* Keep image rendering crisp while allowing border-radius animation */
        backface-visibility: hidden;
      }

      /* Disable duotone when the image or the work card is hovered/focused */
      .work:hover img.w-full,
      .work:focus-within img.w-full,
      .work img.w-full:hover,
      .work img.w-full:focus,
      .work img.w-full:focus-visible {
        filter: none;
        -webkit-filter: none;
      }

      /* Add a subtle zoom when the work card or the image is hovered/focused */
      .work:hover img.w-full,
      .work:focus-within img.w-full,
      .work img.w-full:hover,
      .work img.w-full:focus,
      .work img.w-full:focus-visible {
        transform: scale(1.04);
        /* Elevate slightly visually — optional shadow */
        box-shadow: 0 6px 18px rgba(19, 51, 73, 0.08);
      }

      /* --------------------------- */
      /* Team / person photos (no zoom on hover) */
      /* Target the team section images rendered as `w-full rounded-full` */
      #team img.w-full {
        filter: url(#duotone-7655ea-fafcf3);
        -webkit-filter: url(#duotone-7655ea-fafcf3);
        transition: filter 220ms ease;
        will-change: filter;
        backface-visibility: hidden;
      }

      /* On hover/focus for team avatars (image only), remove the duotone but do not scale */
      #team img.w-full:hover,
      #team img.w-full:focus,
      #team img.w-full:focus-visible {
        filter: none;
        -webkit-filter: none;
        /* explicitly prevent transform/zoom for these avatars */
        transform: none !important;
        box-shadow: none !important;
      }
    </style>

    <script>
      (function() {
        var header = document.getElementById('site-header');
        var siteHeaderInner = document.getElementById("site-header-inner-fixed");
        var logoText = document.getElementById('rt-logo-text');
        if (!header) return;
        var threshold = 20;
        function getStartFontSize() { return window.innerWidth < 768 ? 120 : 340; }
        var startFontSize = getStartFontSize();
        var endFontSize = 40;
        var scrollRange = 300;
        window.addEventListener('resize', function() { startFontSize = getStartFontSize(); });
        function onScroll() {
          var heroWrap = document.getElementById('hero-wrap');
          var heroWrapBottom = heroWrap ? (heroWrap.offsetTop + heroWrap.offsetHeight) : 0;
          var scrollY = window.scrollY || window.pageYOffset;

          // shrink state for background toggle
          if (scrollY > threshold) {
            header.classList.add('is-shrunk');
          } else {
            header.classList.remove('is-shrunk');
          }

          // shrink logo font size as user scrolls
          if (logoText) {
            var progress = Math.min(scrollY / scrollRange, 1);
            var fontSize = startFontSize + (endFontSize - startFontSize) * progress;
            logoText.style.fontSize = fontSize + 'px';
          }

          // when below hero-wrap bottom, switch to fixed (sticky within hero might release at its boundary)
          var containerClasses = ['w-full','px-3','sm:px-6','md:px-8','lg:px-10','xl:px-12','2xl:px-16','3xl:px-24','4xl:px-32','mx-auto','max-w-[92rem]','2xl:max-w-[110rem]','3xl:max-w-[128rem]','4xl:max-w-[144rem]'];
          if (scrollY + 1 >= heroWrapBottom) {
            header.classList.add('fixed');
            header.classList.remove('sticky');
            header.classList.remove('bg-transparent');
            header.classList.add('bg-[#FBFCF4]');
            if (siteHeaderInner) { containerClasses.forEach(function(cls){ siteHeaderInner.classList.add(cls); }); }
          } else {
            header.classList.remove('fixed');
            header.classList.add('sticky');
            header.classList.remove('bg-[#FBFCF4]');
            header.classList.add('bg-transparent');
            if (siteHeaderInner) { containerClasses.forEach(function(cls){ siteHeaderInner.classList.remove(cls); }); }
          }
        }
        window.addEventListener('scroll', onScroll, { passive: true });
        onScroll();

        var menuToggle = document.getElementById('menu-toggle');
        var primaryNav = document.getElementById('primary-nav');
        if (menuToggle && primaryNav) {
          menuToggle.addEventListener('click', function() {
            var isHidden = primaryNav.classList.contains('hidden');
            if (isHidden) {
              primaryNav.classList.remove('hidden');
              menuToggle.setAttribute('aria-expanded', 'true');
            } else {
              primaryNav.classList.add('hidden');
              menuToggle.setAttribute('aria-expanded', 'false');
            }
          });
        }

        if (logoText) {
          var isHovering = false;
          var mouseTargetXrot = 0, mouseTargetYrot = 0;
          var currentXrot = 0, currentYrot = 0;

          function onLogoMouseMove(e) {
            var rect = logoText.getBoundingClientRect();
            mouseTargetYrot = ((e.clientX - rect.left) / rect.width * 2 - 1) * 45;
            mouseTargetXrot = ((e.clientY - rect.top) / rect.height * 2 - 1) * 45;
          }
          logoText.addEventListener('mouseenter', function() {
            isHovering = true;
            logoText.addEventListener('mousemove', onLogoMouseMove);
          });
          logoText.addEventListener('mouseleave', function() {
            isHovering = false;
            logoText.removeEventListener('mousemove', onLogoMouseMove);
          });
          logoText.addEventListener('touchstart', function(e) {
            isHovering = true;
            var touch = e.touches[0];
            var rect = logoText.getBoundingClientRect();
            mouseTargetYrot = ((touch.clientX - rect.left) / rect.width * 2 - 1) * 45;
            mouseTargetXrot = ((touch.clientY - rect.top) / rect.height * 2 - 1) * 45;
          }, { passive: true });
          logoText.addEventListener('touchmove', function(e) {
            var touch = e.touches[0];
            var rect = logoText.getBoundingClientRect();
            mouseTargetYrot = ((touch.clientX - rect.left) / rect.width * 2 - 1) * 45;
            mouseTargetXrot = ((touch.clientY - rect.top) / rect.height * 2 - 1) * 45;
          }, { passive: true });
          logoText.addEventListener('touchend', function() {
            isHovering = false;
          });

          requestAnimationFrame(function loop(timestamp) {
            var animXrot = Math.sin(timestamp / 1000) * 45;
            var animYrot = Math.cos(timestamp / 1300) * 45;
            var targetXrot = isHovering ? mouseTargetXrot : animXrot;
            var targetYrot = isHovering ? mouseTargetYrot : animYrot;
            var speed = isHovering ? 0.12 : 0.04;
            currentXrot += (targetXrot - currentXrot) * speed;
            currentYrot += (targetYrot - currentYrot) * speed;
            logoText.style.fontVariationSettings = "'XROT' " + currentXrot.toFixed(2) + ", 'YROT' " + currentYrot.toFixed(2);
            requestAnimationFrame(loop);
          });
        }

      })();
    </script>

    <!-- Interested in Joining Section -->
    <section class="w-full px-3 sm:px-6 md:px-8 lg:px-10 xl:px-12 2xl:px-16 3xl:px-24 4xl:px-32 mx-auto max-w-[92rem] 2xl:max-w-[110rem] 3xl:max-w-[128rem] 4xl:max-w-[144rem] py-8 md:py-16">
      <div class="grid grid-cols-1 lg:grid-cols-12 gap-5">
        <div class="lg:col-span-3 mb-4 lg:mb-0">
          <h2 class="text-[#664545] text-xl md:text-2xl font-bold">Interested in joining?</h2>
        </div>
        <div class="lg:col-span-6">
          <p class="text-[#2A2020] text-lg leading-[1.25]">We're always looking for passionate researchers and collaborators who share our vision for urban justice and technology. <a href="mailto:wyso@umich.edu" class="underline">Get in touch</a> to learn more about opportunities.</p>
        </div>
      </div>
    </section>
</div>

