<svelte:head>
  <title>Особенная мама — главная</title>
  <meta
    name="description"
    content="Главная страница платформы поддержки семей: проверенные фонды, инструкции, истории и маршруты помощи."
  />
  <script src="https://cdn.tailwindcss.com"></script>
  <script>
    tailwind.config = {
      theme: {
        extend: {
          screens: {
            xs: '390px'
          },
          colors: {
            ink: '#080808',
            text: '#111111',
            muted: '#5C5F63',
            surface: '#F5F4F0',
            line: '#DDDCD6',
            violet: '#7B2CFF',
            olive: '#9DBB60',
            orange: '#EB5B23',
            card: '#EEF2FB'
          },
          boxShadow: {
            soft: '0 24px 60px -18px rgba(0, 0, 0, 0.22)',
            glow: '0 18px 42px -16px rgba(123, 44, 255, 0.34)',
            orange: '0 18px 40px -18px rgba(235, 91, 35, 0.45)'
          },
          borderRadius: {
            '4xl': '32px',
            '5xl': '40px'
          },
          fontFamily: {
            sans: ['Inter', 'ui-sans-serif', 'system-ui', 'sans-serif'],
            display: ['Inter', 'ui-sans-serif', 'system-ui', 'sans-serif'],
            serif: ['"Times New Roman"', 'Georgia', 'serif']
          },
          maxWidth: {
            '8xl': '1440px'
          },
          letterSpacing: {
            tighter2: '-0.04em'
          }
        }
      }
    };
  </script>
  <style>
    html { scroll-behavior: smooth; }
    body {
      font-family: Inter, ui-sans-serif, system-ui, sans-serif;
      color: #111111;
      background:
        radial-gradient(980px 560px at 92% 6%, rgba(157,187,96,.18), transparent 55%),
        radial-gradient(620px 340px at 12% 14%, rgba(123,44,255,.07), transparent 54%),
        radial-gradient(760px 320px at 70% 76%, rgba(235,91,35,.05), transparent 60%),
        linear-gradient(180deg, #f7f6f2 0%, #f3f1eb 48%, #f6f4ef 100%);
    }
    .bg-grid::before {
      content: '';
      position: fixed;
      inset: 0;
      z-index: -1;
      opacity: .18;
      background-image:
        linear-gradient(rgba(221,220,214,.9) 1px, transparent 1px),
        linear-gradient(90deg, rgba(221,220,214,.9) 1px, transparent 1px);
      background-size: 48px 48px;
      mask-image: radial-gradient(circle at center, #000 42%, transparent 100%);
      -webkit-mask-image: radial-gradient(circle at center, #000 42%, transparent 100%);
      pointer-events: none;
    }
    .section-dark {
      background:
        radial-gradient(560px 220px at 88% 0%, rgba(157,187,96,.18), transparent 56%),
        radial-gradient(420px 180px at 12% 8%, rgba(123,44,255,.08), transparent 58%),
        #050505;
    }
    .section-orange {
      background:
        linear-gradient(135deg, rgba(255,255,255,.10) 0%, transparent 36%),
        radial-gradient(420px 180px at 95% 8%, rgba(255,255,255,.08), transparent 56%),
        linear-gradient(180deg, #EE6A33 0%, #E95B25 100%);
    }
    .hero-shell {
      background:
        radial-gradient(circle at 10% 18%, rgba(157, 187, 96, 0.12), transparent 24%),
        radial-gradient(circle at 82% 24%, rgba(123, 44, 255, 0.08), transparent 28%),
        linear-gradient(180deg, rgba(255,255,255,.72), rgba(255,255,255,.5));
      backdrop-filter: blur(12px);
    }
    .hero-image-mask {
      position: relative;
      overflow: hidden;
    }
    .hero-image-mask::after {
      content: '';
      position: absolute;
      inset: 0;
      background:
        linear-gradient(180deg, rgba(0,0,0,0) 0%, rgba(0,0,0,0.08) 100%);
      pointer-events: none;
    }
    .article-overlay {
      background: linear-gradient(
        180deg,
        rgba(0,0,0,.06) 0%,
        rgba(0,0,0,.26) 48%,
        rgba(0,0,0,.72) 100%
      );
    }
  </style>
</svelte:head>

<div class="min-h-screen bg-grid text-text antialiased">
  <header class="sticky top-0 z-50 border-b border-line/80 bg-surface/80 backdrop-blur-xl">
    <div class="mx-auto flex max-w-8xl items-center justify-between px-4 py-3 xs:px-5 md:px-6 lg:px-8">
      <a href="#hero" class="flex items-center gap-3">
        <span class="flex h-9 w-9 items-center justify-center rounded-full bg-violet/10 text-violet">
          <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true">
            <path d="M12 21s-6.7-4.35-8.93-9.01C1.4 8.46 3.2 4.5 7.1 4.5c2.02 0 3.45.98 4.4 2.37.95-1.39 2.38-2.37 4.4-2.37 3.9 0 5.7 3.96 4.03 7.49C18.7 16.65 12 21 12 21Z" />
          </svg>
        </span>
        <span class="text-base font-extrabold tracking-tighter2 xs:text-lg md:text-xl">Особенная мама</span>
      </a>

      <nav class="hidden items-center gap-7 text-sm font-medium text-muted lg:flex">
        <a href="#help" class="transition hover:text-text">Получить помощь</a>
        <a href="#navigator" class="transition hover:text-text">Навигатор фондов</a>
        <a href="#materials" class="transition hover:text-text">Материалы</a>
        <a href="#stories" class="transition hover:text-text">Истории</a>
        <a href="#about" class="transition hover:text-text">О проекте</a>
      </nav>

      <div class="flex items-center gap-2 xs:gap-3 md:gap-4">
        <a
          href="#donate"
          class="hidden text-sm font-semibold text-orange transition hover:opacity-80 lg:inline-block"
        >Поддержать</a>
        <a
          href="#help"
          class="inline-flex items-center justify-center rounded-full bg-ink px-4 py-2.5 text-xs font-bold text-white shadow-soft transition hover:-translate-y-0.5 xs:text-sm md:px-5"
        >Найти помощь</a>
      </div>
    </div>
  </header>

  <main>
    <section id="hero" class="px-4 pb-10 pt-6 xs:px-5 md:px-6 md:pb-14 md:pt-8 lg:px-8 lg:pb-20 lg:pt-10">
      <div class="mx-auto max-w-8xl">
        <div class="hero-shell overflow-hidden rounded-4xl border border-white/70 shadow-soft">
          <div class="grid gap-8 px-4 py-5 xs:px-5 xs:py-6 md:px-8 md:py-8 lg:grid-cols-[minmax(0,540px)_minmax(0,1fr)] lg:gap-10 lg:px-10 lg:py-10 xl:grid-cols-[minmax(0,600px)_minmax(0,1fr)] xl:px-12 xl:py-12">
            <div class="flex flex-col justify-center">
              <div class="mb-4 inline-flex w-fit items-center gap-2 rounded-full border border-line bg-white px-3 py-1.5">
                <span class="h-2 w-2 rounded-full bg-olive"></span>
                <span class="text-[11px] font-semibold text-muted xs:text-xs">Платформа поддержки семей</span>
              </div>

              <h1 class="max-w-[16ch] font-display text-[34px] font-black leading-[0.98] tracking-tighter2 text-text xs:text-[38px] sm:text-[44px] md:text-[56px] lg:text-[62px] xl:text-[74px]">
                Вы не одни.
                <span class="block text-orange">Маршрут помощи</span>
                для особенных мам.
              </h1>

              <p class="mt-5 max-w-[56ch] text-sm leading-6 text-muted xs:text-[15px] md:text-base md:leading-7 xl:text-[18px] xl:leading-8">
                Единая база проверенных фондов, понятные инструкции к действию и опыт тех, кто уже прошел этот путь.
              </p>

              <div class="mt-6 flex flex-wrap gap-3 md:mt-7 lg:mt-8">
                <a
                  href="#help"
                  class="inline-flex items-center gap-2 rounded-full bg-violet px-5 py-3 text-sm font-bold text-white shadow-glow transition hover:-translate-y-0.5 md:px-6 md:py-3.5"
                >
                  <span>Получить помощь</span>
                  <span aria-hidden="true">›</span>
                </a>
                <a
                  href="#navigator"
                  class="inline-flex items-center rounded-full border border-line bg-white px-5 py-3 text-sm font-bold text-text transition hover:border-violet/35 hover:bg-white md:px-6 md:py-3.5"
                >Найти фонд</a>
                <a
                  href="#donate"
                  class="inline-flex items-center rounded-full border border-transparent px-3 py-3 text-sm font-semibold text-muted underline underline-offset-4 transition hover:text-text"
                >Поддержать проект</a>
              </div>

              <div class="mt-7 grid gap-2 border-t border-line pt-4 text-xs font-medium text-muted xs:grid-cols-2 md:grid-cols-3 md:gap-3 md:text-sm">
                <div class="flex items-center gap-2">
                  <span class="text-olive">•</span>
                  <span>Проверенные фонды</span>
                </div>
                <div class="flex items-center gap-2">
                  <span class="text-orange">•</span>
                  <span>Понятные шаги</span>
                </div>
                <div class="flex items-center gap-2">
                  <span class="text-violet">•</span>
                  <span>Поддержка равных</span>
                </div>
              </div>
            </div>

            <div class="relative flex items-center justify-center lg:justify-end">
              <div class="hero-image-mask w-full overflow-hidden rounded-[28px] bg-white shadow-soft md:rounded-[32px] lg:max-w-[760px] xl:max-w-[820px]">
                <img
                  src="https://www.figma.com/api/mcp/asset/8bbb9320-bc8b-4dba-a97e-06d11e149688"
                  alt="Мама с ребёнком"
                  class="h-[280px] w-full object-cover object-[34%_center] xs:h-[320px] md:h-[420px] lg:h-[560px] xl:h-[640px]"
                />
              </div>

              <div class="absolute bottom-3 left-3 w-[160px] rounded-3xl border border-line/80 bg-white/92 p-3 backdrop-blur-md shadow-soft xs:w-[180px] xs:p-4 md:bottom-5 md:left-5 md:w-[220px] lg:bottom-6 lg:left-[-12px] lg:w-[240px] xl:bottom-8 xl:left-[-24px]">
                <div class="flex items-center gap-3">
                  <div class="flex -space-x-2">
                    <img src="https://www.figma.com/api/mcp/asset/9ea092e4-6b0d-4d68-9e03-1e03912568f9" alt="" class="h-8 w-8 rounded-full border border-white object-cover" />
                    <img src="https://www.figma.com/api/mcp/asset/2cc002a6-4604-4edd-b806-a95e3ac8ac7c" alt="" class="h-8 w-8 rounded-full border border-white object-cover" />
                    <img src="https://www.figma.com/api/mcp/asset/c3998db3-5a73-4b32-b4ff-3c1bd4667901" alt="" class="h-8 w-8 rounded-full border border-white object-cover" />
                  </div>
                  <div class="text-[11px] font-bold text-text xs:text-xs">+2.5k историй</div>
                </div>
                <p class="mt-2 text-[11px] leading-4 text-muted xs:text-xs xs:leading-5">
                  Сообщество мам, которые понимают, через что вы проходите.
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="help" class="px-4 py-8 xs:px-5 md:px-6 md:py-10 lg:px-8 lg:py-14">
      <div class="mx-auto max-w-8xl">
        <div class="rounded-4xl border border-white/70 bg-white/72 px-4 py-5 shadow-soft backdrop-blur-sm xs:px-5 md:px-8 md:py-8">
          <div class="mb-6 md:mb-8 lg:mb-10">
            <h2 class="font-display text-[28px] font-black leading-[1.02] tracking-tighter2 md:text-[36px] lg:text-[42px]">
              Выберите ваш путь
            </h2>
            <p class="mt-3 max-w-[60ch] text-sm leading-6 text-muted md:text-base">
              Мы структурировали информацию, чтобы вы могли быстро найти именно то, что нужно сейчас.
            </p>
          </div>

          <div class="grid gap-3 md:grid-cols-2 lg:grid-cols-4 lg:gap-4">
            <article class="rounded-4xl bg-surface p-5 md:p-6 lg:p-7">
              <div class="mb-6 flex h-11 w-11 items-center justify-center rounded-full bg-white text-violet shadow-sm">
                <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true"><path d="M12 2a10 10 0 1 0 10 10A10.011 10.011 0 0 0 12 2Zm6.71 9h-2.09a14.14 14.14 0 0 0-1.3-4.13A8.038 8.038 0 0 1 18.71 11ZM12 4.06A12.33 12.33 0 0 1 14.56 11H9.44A12.33 12.33 0 0 1 12 4.06ZM4.29 13h2.09a14.14 14.14 0 0 0 1.3 4.13A8.038 8.038 0 0 1 4.29 13Zm2.09-2H4.29a8.038 8.038 0 0 1 3.39-4.13A14.14 14.14 0 0 0 6.38 11Zm.92 2h5.7a12.33 12.33 0 0 1-1.99 5.39A12.33 12.33 0 0 1 7.3 13Zm6.7 5.39A12.33 12.33 0 0 1 13 13h5.7A12.33 12.33 0 0 1 14 18.39ZM13 11a12.33 12.33 0 0 1 1.99-5.39A12.33 12.33 0 0 1 18.7 11Z"/></svg>
              </div>
              <h3 class="text-lg font-bold leading-6">Мне нужна помощь</h3>
              <p class="mt-8 text-sm leading-6 text-muted">С чего начать после диагноза, как получить квоту или найти психолога.</p>
            </article>

            <article class="rounded-4xl bg-surface p-5 md:p-6 lg:p-7">
              <div class="mb-6 flex h-11 w-11 items-center justify-center rounded-full bg-white text-violet shadow-sm">
                <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true"><path d="M10 2a8 8 0 1 0 4.9 14.32l4.39 4.39 1.41-1.41-4.39-4.39A8 8 0 0 0 10 2Zm0 2a6 6 0 1 1 0 12 6 6 0 0 1 0-12Z"/></svg>
              </div>
              <h3 class="text-lg font-bold leading-6">Хочу найти фонд</h3>
              <p class="mt-8 text-sm leading-6 text-muted">Единая база проверенных НКО по регионам и диагнозам.</p>
            </article>

            <article class="rounded-4xl bg-surface p-5 md:p-6 lg:p-7">
              <div class="mb-6 flex h-11 w-11 items-center justify-center rounded-full bg-white text-violet shadow-sm">
                <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true"><path d="M4 3h10a2 2 0 0 1 2 2v14l-7-3-7 3V5a2 2 0 0 1 2-2Zm0 2v10.76l5-2.14 5 2.14V5Z"/></svg>
              </div>
              <h3 class="text-lg font-bold leading-6">Хочу разобраться</h3>
              <p class="mt-8 text-sm leading-6 text-muted">Инструкции по реабилитации, юридическим правам и школе.</p>
            </article>

            <article class="rounded-4xl bg-surface p-5 md:p-6 lg:p-7">
              <div class="mb-6 flex h-11 w-11 items-center justify-center rounded-full bg-white text-violet shadow-sm">
                <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true"><path d="M12 21s-6.7-4.35-8.93-9.01C1.4 8.46 3.2 4.5 7.1 4.5c2.02 0 3.45.98 4.4 2.37.95-1.39 2.38-2.37 4.4-2.37 3.9 0 5.7 3.96 4.03 7.49C18.7 16.65 12 21 12 21Z"/></svg>
              </div>
              <h3 class="text-lg font-bold leading-6">Хочу помочь</h3>
              <p class="mt-8 text-sm leading-6 text-muted">Сделать пожертвование, стать волонтёром или партнёром проекта.</p>
            </article>
          </div>
        </div>
      </div>
    </section>

    <section id="about" class="px-4 py-10 xs:px-5 md:px-6 md:py-12 lg:px-8 lg:py-16">
      <div class="mx-auto max-w-8xl border-y border-line px-0 py-8 md:py-10 lg:px-8 lg:py-14">
        <div class="grid gap-8 md:grid-cols-2 md:gap-10 lg:gap-16 xl:gap-24">
          <div>
            <h2 class="font-display text-[30px] font-black leading-[1.02] tracking-tighter2 md:text-[40px] lg:text-[52px]">
              Мы объединяем помощь,
              <br />
              ради одной цели.
            </h2>

            <p class="mt-5 text-sm leading-7 text-muted md:text-base xl:text-[18px]">
              Проект «Особенная мама» создан для того, чтобы в момент растерянности семья не оставалась один на один с системой. Мы собираем актуальные данные фондов, переводим бюрократические алгоритмы на человеческий язык и публикуем реальные истории пути.
            </p>

            <a href="/" class="mt-6 inline-flex items-center gap-2 border-b border-text pb-1 text-sm font-bold md:text-base">
              <span>Подробнее о миссии</span>
              <span aria-hidden="true">›</span>
            </a>
          </div>

          <div class="grid grid-cols-2 gap-5 md:gap-6 lg:gap-8">
            <div class="border-l-2 border-orange pl-4 md:pl-5 lg:pl-6">
              <div class="text-[30px] font-black leading-none tracking-tighter2 text-text md:text-[38px] lg:text-[52px]">120+</div>
              <div class="mt-2 text-xs leading-5 text-muted md:text-sm">Проверенных фондов
                <br />в навигаторе</div>
            </div>

            <div class="border-l-2 border-olive pl-4 md:pl-5 lg:pl-6">
              <div class="flex items-end gap-1">
                <div class="text-[30px] font-black leading-none tracking-tighter2 text-text md:text-[38px] lg:text-[52px]">15</div>
                <div class="text-lg font-semibold leading-7 text-olive md:text-xl lg:text-2xl">тыс</div>
              </div>
              <div class="mt-2 text-xs leading-5 text-muted md:text-sm">Семей ежемесячно
                <br />получают маршрут</div>
            </div>

            <div class="border-l-2 border-violet pl-4 md:pl-5 lg:pl-6">
              <div class="text-[30px] font-black leading-none tracking-tighter2 text-text md:text-[38px] lg:text-[52px]">300+</div>
              <div class="mt-2 text-xs leading-5 text-muted md:text-sm">Материалов и
                <br />подробных инструкций</div>
            </div>

            <div class="border-l-2 border-line pl-4 md:pl-5 lg:pl-6">
              <div class="text-[30px] font-black leading-none tracking-tighter2 text-text md:text-[38px] lg:text-[52px]">80</div>
              <div class="mt-2 text-xs leading-5 text-muted md:text-sm">Регионов России
                <br />охвачено платформой</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section class="px-4 py-10 xs:px-5 md:px-6 md:py-12 lg:px-8 lg:py-16">
      <div class="mx-auto max-w-8xl">
        <h2 class="text-center font-display text-[28px] font-black leading-[1.02] tracking-tighter2 md:text-[36px] lg:text-[42px]">
          Как работает алгоритм поддержки
        </h2>

        <div class="relative mt-8 md:mt-10 lg:mt-14">
          <div class="absolute left-0 right-0 top-5 hidden h-px bg-line md:block lg:top-6"></div>

          <div class="grid grid-cols-1 gap-4 md:grid-cols-3 md:gap-5 lg:gap-10">
            <article>
              <div class="relative z-10 mb-4 flex h-11 w-11 items-center justify-center rounded-full border border-orange bg-white text-lg font-black text-orange lg:h-12 lg:w-12">1</div>
              <h3 class="text-base font-bold leading-6 lg:text-lg">Понимаем запрос</h3>
              <p class="mt-2 text-sm leading-6 text-muted">Вы отвечаете на несколько простых вопросов о возрасте, диагнозе и необходимом типе помощи.</p>
            </article>

            <article>
              <div class="relative z-10 mb-4 flex h-11 w-11 items-center justify-center rounded-full border border-olive bg-white text-lg font-black text-olive lg:h-12 lg:w-12">2</div>
              <h3 class="text-base font-bold leading-6 lg:text-lg">Показываем варианты</h3>
              <p class="mt-2 text-sm leading-6 text-muted">Система фильтрует базу и выдает только те фонды и инструкции, которые работают с вашей ситуацией.</p>
            </article>

            <article>
              <div class="relative z-10 mb-4 flex h-11 w-11 items-center justify-center rounded-full border border-violet bg-white text-lg font-black text-violet lg:h-12 lg:w-12">3</div>
              <h3 class="text-base font-bold leading-6 lg:text-lg">Переводим к действию</h3>
              <p class="mt-2 text-sm leading-6 text-muted">Мы даем прямые контакты, шаблоны писем и список документов для обращения за помощью.</p>
            </article>
          </div>
        </div>
      </div>
    </section>

    <section id="navigator" class="px-4 py-4 xs:px-5 md:px-6 md:py-6 lg:px-8 lg:py-8">
      <div class="section-dark mx-auto max-w-8xl overflow-hidden rounded-5xl px-4 py-8 text-white shadow-soft xs:px-5 md:px-8 md:py-10 lg:px-10 lg:py-12 xl:px-12 xl:py-16">
        <div class="flex flex-col gap-5 lg:flex-row lg:items-end lg:justify-between">
          <div class="max-w-[680px]">
            <div class="inline-flex rounded-full border border-white/15 bg-white/10 px-3 py-1.5 text-xs font-semibold text-white/90">
              Smart-сервис
            </div>
            <h2 class="mt-4 font-display text-[28px] font-black leading-[1.02] tracking-tighter2 md:text-[38px] lg:text-[46px]">
              Навигатор по фондам
            </h2>
            <p class="mt-4 max-w-[54ch] text-sm leading-6 text-white/68 md:text-base">
              Умный поиск среди проверенных НКО. Фильтруйте по диагнозу, региону или типу поддержки, чтобы найти тех, кто поможет.
            </p>
          </div>

          <a
            href="/"
            class="inline-flex w-fit items-center justify-center rounded-full bg-violet px-5 py-3 text-sm font-bold text-white shadow-glow transition hover:-translate-y-0.5 md:px-6 md:py-3.5"
          >Открыть навигатор</a>
        </div>

        <div class="mt-8 lg:mt-12 xl:mt-16">
          <div class="rounded-4xl border border-line bg-surface p-4 text-text shadow-soft md:p-5 xl:p-8">
            <div class="flex flex-wrap gap-2.5 md:gap-3">
              <button class="rounded-full border border-line bg-white px-4 py-2 text-xs font-medium md:text-sm">Диагноз ▾</button>
              <button class="rounded-full border border-violet bg-violet px-4 py-2 text-xs font-semibold text-white md:text-sm">Тип: Реабилитация ✕</button>
              <button class="rounded-full border border-line bg-white px-4 py-2 text-xs font-medium md:text-sm">Возраст ▾</button>
              <button class="rounded-full border border-line bg-white px-4 py-2 text-xs font-medium md:text-sm">Регион ▾</button>
            </div>

            <div class="mt-5 grid gap-4 xl:grid-cols-2 xl:gap-6">
              <article class="rounded-[24px] border border-line bg-white p-5 xl:p-6">
                <div class="flex items-start justify-between gap-3">
                  <div class="flex items-center gap-3">
                    <div class="flex h-10 w-10 items-center justify-center rounded-xl bg-card text-violet">
                      <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true"><path d="M12 2 3 7v6c0 5 3.84 9.74 9 11 5.16-1.26 9-6 9-11V7l-9-5Zm0 2.18 7 3.89V13c0 3.98-2.91 7.88-7 8.93C7.91 20.88 5 16.98 5 13V8.07l7-3.89Z"/></svg>
                    </div>
                    <div>
                      <h3 class="text-sm font-bold leading-6 md:text-base">Фонд «Подарок ангелу»</h3>
                      <p class="text-xs text-muted">Вся Россия</p>
                    </div>
                  </div>
                  <span class="rounded-md bg-green-100 px-2 py-1 text-[11px] font-bold text-green-800">Проверен</span>
                </div>
                <p class="mt-4 text-sm leading-6 text-muted">Оплата реабилитации для детей с ДЦП, обеспечение техническими средствами (ТСР).</p>
                <div class="mt-5 flex gap-2 border-t border-line pt-4">
                  <span class="rounded-md bg-surface px-2.5 py-1 text-xs">Реабилитация</span>
                  <span class="rounded-md bg-surface px-2.5 py-1 text-xs">ТСР</span>
                </div>
              </article>

              <article class="rounded-[24px] border border-line bg-white p-5 xl:p-6">
                <div class="flex items-start justify-between gap-3">
                  <div class="flex items-center gap-3">
                    <div class="flex h-10 w-10 items-center justify-center rounded-xl bg-surface text-violet">
                      <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true"><path d="M12 3 4 7v5c0 4.67 3.11 8.88 8 10 4.89-1.12 8-5.33 8-10V7l-8-4Zm0 2.2 6 3v3.8c0 3.58-2.29 6.93-6 8-3.71-1.07-6-4.42-6-8V8.2l6-3Z"/></svg>
                    </div>
                    <div>
                      <h3 class="text-sm font-bold leading-6 md:text-base">Фонд «Обнажённые сердца»</h3>
                      <p class="text-xs text-muted">Федеральный</p>
                    </div>
                  </div>
                  <span class="rounded-md bg-green-100 px-2 py-1 text-[11px] font-bold text-green-800">Проверен</span>
                </div>
                <p class="mt-4 text-sm leading-6 text-muted">Поддержка семей, воспитывающих детей с аутизмом и другими особенностями развития.</p>
                <div class="mt-5 flex gap-2 border-t border-line pt-4">
                  <span class="rounded-md bg-surface px-2.5 py-1 text-xs">РАС</span>
                  <span class="rounded-md bg-surface px-2.5 py-1 text-xs">Обучение</span>
                </div>
              </article>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="materials" class="px-4 py-10 xs:px-5 md:px-6 md:py-12 lg:px-8 lg:py-16">
      <div class="mx-auto max-w-8xl">
        <div class="flex flex-col gap-4 lg:flex-row lg:items-end lg:justify-between">
          <div>
            <h2 class="font-display text-[28px] font-black leading-[1.02] tracking-tighter2 md:text-[36px] lg:text-[42px]">
              Полезные материалы
            </h2>
            <p class="mt-3 max-w-[64ch] text-sm leading-6 text-muted md:text-base">
              Инструкции от юристов, советы психологов и личные истории, которые помогут найти почву под ногами.
            </p>
          </div>

          <div class="flex flex-wrap gap-3">
            <a href="/" class="inline-flex items-center rounded-full border border-line px-5 py-2.5 text-sm font-bold text-text">Все истории</a>
            <a href="/" class="inline-flex items-center rounded-full bg-ink px-5 py-2.5 text-sm font-bold text-white shadow-soft">Читать материалы</a>
          </div>
        </div>

        <div class="mt-8 grid gap-4 lg:grid-cols-12 lg:gap-6">
          <article class="relative overflow-hidden rounded-5xl lg:col-span-8">
            <img
              src="https://www.figma.com/api/mcp/asset/55c02276-861b-4b92-b6df-9af41ef16ef9"
              alt="Юридическая помощь"
              class="h-[260px] w-full object-cover xs:h-[300px] md:h-[360px] lg:h-[520px]"
            />
            <div class="article-overlay absolute inset-0"></div>
            <div class="absolute inset-x-0 bottom-0 p-4 text-white xs:p-5 md:p-6 lg:p-8">
              <span class="inline-flex rounded-full bg-orange px-3 py-1 text-[10px] font-bold uppercase tracking-[0.08em] shadow-orange md:text-xs">
                Юридическая помощь
              </span>
              <h3 class="mt-3 max-w-[18ch] font-display text-[24px] font-black leading-[1.02] tracking-tighter2 xs:text-[28px] md:max-w-[22ch] md:text-[34px] lg:mt-4 lg:max-w-[18ch] lg:text-[42px]">
                Как оформить инвалидность в 2024 году
              </h3>
              <p class="mt-3 max-w-[64ch] text-xs leading-5 text-white/80 md:text-sm md:leading-6">
                Разбираем новые правила МСЭ, какие документы собирать в первую очередь и что делать в случае отказа.
              </p>
            </div>
          </article>

          <div id="stories" class="grid gap-4 md:grid-cols-2 lg:col-span-4 lg:grid-cols-1 lg:gap-6">
            <article class="grid grid-cols-3 gap-3 rounded-4xl bg-surface p-3.5 md:p-4">
              <div class="overflow-hidden rounded-3xl">
                <img src="https://www.figma.com/api/mcp/asset/a3d05b76-3674-461a-abb6-fd685537c846" alt="" class="h-[96px] w-full object-cover md:h-[108px]" />
              </div>
              <div class="col-span-2">
                <div class="text-[10px] font-bold uppercase tracking-[0.08em] text-orange md:text-xs">Психология мамы</div>
                <h4 class="mt-2 text-sm font-bold leading-5 md:text-base">Где взять силы: как не выгореть в первый год</h4>
                <p class="mt-3 text-[11px] text-muted md:text-xs">5 мин чтения</p>
              </div>
            </article>

            <article class="grid grid-cols-3 gap-3 rounded-4xl bg-surface p-3.5 md:p-4">
              <div class="overflow-hidden rounded-3xl">
                <img src="https://www.figma.com/api/mcp/asset/cc9951c2-7c22-4d55-b134-746f4cf4f7d4" alt="" class="h-[96px] w-full object-cover md:h-[108px]" />
              </div>
              <div class="col-span-2">
                <div class="text-[10px] font-bold uppercase tracking-[0.08em] text-olive md:text-xs">Реабилитация</div>
                <h4 class="mt-2 text-sm font-bold leading-5 md:text-base">Как отличить эффективный метод от пустышки</h4>
                <p class="mt-3 text-[11px] text-muted md:text-xs">7 мин чтения</p>
              </div>
            </article>

            <article class="grid grid-cols-3 gap-3 rounded-4xl border border-violet/10 bg-violet/5 p-3.5 md:p-4">
              <div class="flex h-[96px] items-center justify-center rounded-3xl bg-violet/10 text-violet md:h-[108px]">
                <svg viewBox="0 0 24 24" class="h-8 w-8 fill-current" aria-hidden="true"><path d="M12 21s-6.7-4.35-8.93-9.01C1.4 8.46 3.2 4.5 7.1 4.5c2.02 0 3.45.98 4.4 2.37.95-1.39 2.38-2.37 4.4-2.37 3.9 0 5.7 3.96 4.03 7.49C18.7 16.65 12 21 12 21Z" /></svg>
              </div>
              <div class="col-span-2">
                <div class="text-[10px] font-bold uppercase tracking-[0.08em] text-violet md:text-xs">История мамы</div>
                <h4 class="mt-2 text-sm font-bold leading-5 md:text-base">«Мы приняли диагноз через три года отрицания»</h4>
                <p class="mt-3 text-[11px] text-muted md:text-xs">Опыт Анны, г. Самара</p>
              </div>
            </article>
          </div>
        </div>
      </div>
    </section>

    <section class="border-t border-line bg-card/40 px-4 py-10 xs:px-5 md:px-6 md:py-12 lg:px-8 lg:py-16">
      <div class="mx-auto max-w-8xl">
        <h2 class="text-center font-display text-[28px] font-black leading-[1.02] tracking-tighter2 md:text-[36px] lg:text-[42px]">
          Что говорят семьи и партнёры
        </h2>

        <div class="mt-8 grid gap-4 md:grid-cols-3 lg:gap-6">
          <blockquote class="rounded-4xl border border-line/80 bg-white p-5 shadow-soft lg:p-7">
            <p class="text-sm leading-7 text-text">
              Тут я нашла не просто список фондов, а чёткий алгоритм действий. До этого я месяц стучалась в закрытые двери. Через навигатор нужный фонд откликнулся за два дня.
            </p>
            <footer class="mt-5 flex items-center gap-3">
              <div class="flex h-10 w-10 items-center justify-center rounded-full border border-line bg-surface text-sm font-black">М</div>
              <div>
                <div class="text-sm font-bold">Мария К.</div>
                <div class="text-xs text-muted">Мама ребёнка с СМА</div>
              </div>
            </footer>
          </blockquote>

          <blockquote class="rounded-4xl bg-ink p-5 text-white shadow-soft lg:p-7">
            <p class="text-sm leading-7 text-white">
              Проект снял огромную нагрузку с наших координаторов. Теперь к нам приходят семьи с уже готовым, правильно оформленным пакетом документов.
            </p>
            <footer class="mt-5 flex items-center gap-3">
              <img src="https://www.figma.com/api/mcp/asset/f3b301f1-7163-4a06-aa1e-cf2f3554304b" alt="" class="h-10 w-10 rounded-full object-cover" />
              <div>
                <div class="text-sm font-bold">Евгений Смирнов</div>
                <div class="text-xs text-white/55">Представитель НКО</div>
              </div>
            </footer>
          </blockquote>

          <blockquote class="rounded-4xl border border-line/80 bg-white p-5 shadow-soft lg:p-7">
            <p class="text-sm leading-7 text-text">
              Статьи в разделе психологии читала как про себя. Очень поддерживающе, без токсичного позитива. Спасибо, что говорите о мамах, а не только о детях.
            </p>
            <footer class="mt-5 flex items-center gap-3">
              <div class="flex h-10 w-10 items-center justify-center rounded-full border border-violet/20 bg-violet/10 text-sm font-black text-violet">Е</div>
              <div>
                <div class="text-sm font-bold">Елена В.</div>
                <div class="text-xs text-muted">Читает материалы</div>
              </div>
            </footer>
          </blockquote>
        </div>
      </div>
    </section>

    <section id="donate" class="px-4 py-10 xs:px-5 md:px-6 md:py-12 lg:px-8 lg:py-16">
      <div class="section-orange mx-auto max-w-8xl rounded-5xl px-4 py-8 text-white shadow-orange xs:px-5 md:px-8 md:py-10 lg:px-10 lg:py-14 xl:px-12">
        <div class="mx-auto max-w-[920px]">
          <div class="text-center">
            <h2 class="font-display text-[28px] font-black leading-[1.02] tracking-tighter2 md:text-[38px] lg:text-[46px]">
              Поддержите проект
            </h2>
            <p class="mx-auto mt-4 max-w-[62ch] text-sm leading-6 text-white/85 md:text-base">
              Платформа существует и развивается благодаря пожертвованиям. Ваши средства идут на оплату работы юристов, редакторов, психологов и развитие алгоритмов навигатора.
            </p>
          </div>

          <div class="mx-auto mt-7 max-w-[780px] rounded-4xl bg-white p-4 text-text shadow-soft md:p-6 lg:mt-9 lg:p-8 xl:p-10">
            <h3 class="text-center text-xl font-black md:text-2xl">Сделать пожертвование</h3>

            <div class="mx-auto mt-5 inline-flex rounded-xl bg-surface p-1">
              <button class="rounded-lg bg-white px-4 py-2 text-xs font-bold shadow-sm md:px-6 md:text-sm">Ежемесячно</button>
              <button class="rounded-lg px-4 py-2 text-xs font-medium text-muted md:px-6 md:text-sm">Разово</button>
            </div>

            <div class="mt-5 grid grid-cols-2 gap-2.5 md:grid-cols-4 md:gap-3">
              <button class="rounded-2xl border border-line px-3 py-3 text-sm font-bold md:px-4 md:text-base">300 ₽</button>
              <button class="rounded-2xl border border-violet bg-violet/5 px-3 py-3 text-sm font-bold text-violet shadow-glow md:px-4 md:text-base">500 ₽</button>
              <button class="rounded-2xl border border-line px-3 py-3 text-sm font-bold md:px-4 md:text-base">1000 ₽</button>
              <button class="rounded-2xl border border-line px-3 py-3 text-xs font-semibold text-muted md:px-4 md:text-sm">Другая сумма</button>
            </div>

            <p class="mt-4 text-center text-[11px] leading-5 text-muted md:text-xs">
              500 ₽ в месяц помогут нам проверять данные одного фонда и поддерживать контактную базу в порядке.
            </p>

            <button class="mt-5 w-full rounded-2xl bg-ink py-3.5 text-sm font-black text-white shadow-soft md:py-4 md:text-lg">
              Сделать пожертвование
            </button>
          </div>
        </div>
      </div>
    </section>

    <section class="px-4 py-10 xs:px-5 md:px-6 md:py-12 lg:px-8 lg:py-16">
      <div class="mx-auto max-w-8xl">
        <div class="border-b border-line pb-8 lg:px-8">
          <h2 class="font-display text-[24px] font-black leading-[1.02] tracking-tighter2 md:text-[30px]">
            Команда платформы
          </h2>
          <p class="mt-3 max-w-[52ch] text-sm leading-6 text-muted md:text-base">
            Мы — юристы, журналисты, разработчики и, прежде всего, люди, которые знают систему изнутри.
          </p>
        </div>

        <div class="mt-8 grid grid-cols-2 gap-x-4 gap-y-6 text-center md:grid-cols-4 md:gap-6 lg:mt-10 lg:px-8 lg:gap-8">
          <article>
            <img src="https://www.figma.com/api/mcp/asset/f95ab1ad-35b2-401c-aebc-7a93c2873270" alt="Анна Иванова" class="mx-auto h-20 w-20 rounded-full object-cover grayscale lg:h-24 lg:w-24" />
            <div class="mt-3 text-sm font-bold lg:text-base">Анна Иванова</div>
            <div class="text-xs text-muted lg:text-sm">Руководитель проекта</div>
          </article>

          <article>
            <img src="https://www.figma.com/api/mcp/asset/acd15d28-39ba-4504-b073-daf4acf6b01b" alt="Михаил Петров" class="mx-auto h-20 w-20 rounded-full object-cover grayscale lg:h-24 lg:w-24" />
            <div class="mt-3 text-sm font-bold lg:text-base">Михаил Петров</div>
            <div class="text-xs text-muted lg:text-sm">Главный юрист</div>
          </article>

          <article>
            <img src="https://www.figma.com/api/mcp/asset/c3c11bfa-3cfd-4e81-bb5f-82dfff8d2b01" alt="Елена Смирнова" class="mx-auto h-20 w-20 rounded-full object-cover grayscale lg:h-24 lg:w-24" />
            <div class="mt-3 text-sm font-bold lg:text-base">Елена Смирнова</div>
            <div class="text-xs text-muted lg:text-sm">Шеф-редактор историй</div>
          </article>

          <article>
            <img src="https://www.figma.com/api/mcp/asset/fc605462-b66f-4c09-8ca1-3680bf7be4d0" alt="Ольга Светлова" class="mx-auto h-20 w-20 rounded-full object-cover grayscale lg:h-24 lg:w-24" />
            <div class="mt-3 text-sm font-bold lg:text-base">Ольга Светлова</div>
            <div class="text-xs text-muted lg:text-sm">Координатор фондов</div>
          </article>
        </div>
      </div>
    </section>

    <section class="px-4 py-4 xs:px-5 md:px-6 md:py-6 lg:px-8 lg:py-8">
      <div class="section-dark mx-auto max-w-8xl rounded-5xl px-4 py-8 text-white shadow-soft xs:px-5 md:px-8 md:py-10 lg:px-10 lg:py-14 xl:px-12">
        <div class="mx-auto max-w-[920px] text-center">
          <h2 class="font-display text-[32px] font-black leading-[1.02] tracking-tighter2 md:text-[46px] lg:text-[60px]">
            Сделайте первый шаг
          </h2>
          <p class="mt-4 text-sm leading-6 text-white/70 md:text-base lg:text-[20px] lg:leading-8">
            Выберите действие, которое необходимо вам прямо сейчас.
          </p>

          <div class="mt-6 flex flex-wrap justify-center gap-3 lg:mt-8">
            <a href="#help" class="inline-flex items-center rounded-full bg-violet px-5 py-3 text-sm font-bold text-white shadow-glow md:px-6 md:py-3.5 lg:px-8 lg:py-4 lg:text-lg">Получить помощь</a>
            <a href="#navigator" class="inline-flex items-center rounded-full border border-white/20 bg-white/10 px-5 py-3 text-sm font-bold text-white md:px-6 md:py-3.5 lg:px-8 lg:py-4 lg:text-lg">Найти фонд</a>
            <a href="#donate" class="inline-flex items-center rounded-full px-5 py-3 text-sm font-bold text-white/72 underline underline-offset-4 md:px-6 md:py-3.5 lg:px-8 lg:py-4 lg:text-lg">Поддержать проект</a>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer class="border-t border-line bg-surface px-4 py-10 xs:px-5 md:px-6 md:py-12 lg:px-8 lg:py-16">
    <div class="mx-auto max-w-8xl">
      <div class="grid gap-8 md:grid-cols-2 lg:grid-cols-5 lg:gap-8">
        <div class="md:col-span-2 lg:col-span-2">
          <div class="flex items-center gap-3">
            <span class="flex h-9 w-9 items-center justify-center rounded-full bg-violet/10 text-violet">
              <svg viewBox="0 0 24 24" class="h-5 w-5 fill-current" aria-hidden="true">
                <path d="M12 21s-6.7-4.35-8.93-9.01C1.4 8.46 3.2 4.5 7.1 4.5c2.02 0 3.45.98 4.4 2.37.95-1.39 2.38-2.37 4.4-2.37 3.9 0 5.7 3.96 4.03 7.49C18.7 16.65 12 21 12 21Z" />
              </svg>
            </span>
            <span class="text-xl font-extrabold tracking-tighter2 md:text-2xl">Особенная мама</span>
          </div>

          <p class="mt-4 max-w-[420px] text-sm leading-6 text-muted">
            Навигатор помощи, база проверенных фондов и поддерживающие материалы для семей, воспитывающих детей с особенностями развития.
          </p>

          <a href="#donate" class="mt-5 inline-flex items-center rounded-full bg-violet px-5 py-2.5 text-sm font-bold text-white shadow-glow">
            Поддержать проект
          </a>
        </div>

        <div>
          <h4 class="text-base font-bold">Навигация</h4>
          <ul class="mt-4 space-y-3 text-sm text-muted">
            <li><a href="#hero">Главная</a></li>
            <li><a href="#help">Получить помощь</a></li>
            <li><a href="#navigator">Навигатор по фондам</a></li>
            <li><a href="#materials">Полезные материалы</a></li>
            <li><a href="#stories">Истории мам</a></li>
          </ul>
        </div>

        <div>
          <h4 class="text-base font-bold">О проекте</h4>
          <ul class="mt-4 space-y-3 text-sm text-muted">
            <li><a href="#about">Миссия и команда</a></li>
            <li><a href="/">Партнёрам и НКО</a></li>
            <li><a href="/">Волонтёрство</a></li>
            <li><a href="/">Отчёты</a></li>
            <li><a href="/">Контакты</a></li>
          </ul>
        </div>

        <div>
          <h4 class="text-base font-bold">Соцсети</h4>
          <div class="mt-4 flex gap-4">
            <a href="/" class="flex h-10 w-10 items-center justify-center rounded-full border border-line text-text">✦</a>
            <a href="/" class="flex h-10 w-10 items-center justify-center rounded-full border border-line text-text">✧</a>
          </div>
        </div>
      </div>

      <div class="mt-10 flex flex-col gap-3 border-t border-line pt-6 text-xs text-muted md:flex-row md:items-center md:justify-between lg:mt-12 lg:pt-8">
        <p>© 2024 Проект «Особенная мама». Все права защищены.</p>
        <div class="flex flex-wrap gap-4">
          <a href="/">Политика конфиденциальности</a>
          <a href="/">Пользовательское соглашение</a>
        </div>
      </div>
    </div>
  </footer>
</div>
