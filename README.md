## Tailwind CSS 04
## Chapter 4: Animated Mobile Menu & Hamburger Icon
It is my coding practice with the TUTORIAL of Dave Gray. 

## Source
### Dave Gray 的 Tailwind CSS 資源
https://github.com/gitdagray/tailwind-css-course

### Dave Gray 的 Tailwind CSS 課程
https://youtube.com/playlist?list=PL0Zuz27SZ-6M8znNpim8dRiICRrP5HPft&si=TYz4MlVwoMJZuO69

### Dave Gray 的 YouTube 頻道
https://www.youtube.com/@DaveGrayTeachesCode

## Quick Concept offline
###  1. Intro
        教學影片開頭和介紹

###  2. Welcome

###  3. Overview & Starter Code
        (1)在 terminal 輸入 npx tailwindcss init
        (2)新增資料夾 build
        (3)新增資料夾 src
        (4)新增 input.css
        (5)新增 base
        (6)新增 components
        (7)新增 utilities
        (8)新增 index.html，修改 index.html
        (9)新增資料夾 img
        (10)新增 rocketride.png, rocketman.png, rocketlaunch.png, rocketdab.png
        (11)新增 favicon.ico
        (12)加入 html 路徑為 ./build/*.html
        (13)在 terminal 輸入 npm init -y
        (14)在 package.json 的 scripts，
        設定 tailwind，指令為 npx tailwindcss -i ./src/input.css -o ./build/css/style.css --watch
        (15)在 terminal 輸入 npm i -D prettier-plugin-tailwindcss
        (16)新增 .gitignore，輸入 node_modules
        (17)在 package.json 的 scripts，
        設定 prettier，指令為 npx prettier --write **/*.html
        (18)在 terminal 輸入 npm run tailwind
        即在 terminal 執行 npx tailwindcss -i ./src/input.css -o ./build/css/style.css --watch

###  4. Small Changes to Project
        (1)修改 button 元素，id 為 hamburger-button
        設定 button元素的 Class 為 text-3xl md:hidden focus:outline-none
        md:hidden 為 
        @media (min-width: 768px) {
                display: none;
        }

        (2)設定 nav 元素的 Class 為 hidden md:block space-x-8 text-xl
        md:block 為 
        @media (min-width: 768px) {
                display: block
        }

        (3)修改 button 元素，id 為 hamburger-button
        設定 button元素的 Class 為 text-3xl md:hidden cursor-pointer
        cursor-pointer 為 cursor: pointer;

        tailwind.config.js
        (4)在 extend 中，修改 tallscreen 的最小長寬比例為 65%
        輸入 screens: {
                "widescreen": { "raw": "(min-aspect-ratio: 3/2)"},
                "tallscreen": { "raw": "(min-aspect-ratio: 13/20)"},
        }

###  5. Two Menu Versions
        第一個是顯示選單，並在選單螢幕上顯示關閉按鈕
        第二個版本中的漢堡圖標設置動畫

###  6. Build the Mobile Menu
        (1)設定 section 元素的 id 為 mobile-menu
        設定 section元素的 Class，
        新增 absolute 為 position: absolute;
        新增 top-0 為 top: 0px;
        新增 bg-black 為 background-color: rgb(0 0 0);
        新增 w-full 為 width: 100%;
        新增 text-5xl 為 
        font-size: 3rem; /* 48px */
        line-height: 1;
        新增 flex 為 display: flex;
        新增 flex-col 為 flex-direction: column;
        新增 justify-center 為 justify-content: center;

        (2)設定 button 元素的 Class，
        新增 text-8xl 為 
        font-size: 6rem; /* 96px */
        line-height: 1;
        新增 self-end 為 align-self: flex-end;
        新增 w-full 為 width: 100%;
        新增 px-6 為 
        padding-left: 1.5rem; /* 24px */
        padding-right: 1.5rem; /* 24px */
        圖標 &times;

        (3)在 termianl 輸入 npm run tailwind

        (4)設定 nav 元素的 aria-label 為 mobile
        設定 nav元素的 Class，
        新增 flex 為 display: flex;
        新增 flex-col 為 flex-direction: column;
        新增 min-h-screen 為 min-height: 100vh;
        新增 items-center 為 align-items: center;
        新增 py-8 為 
        padding-top: 2rem; /* 32px */
        padding-bottom: 2rem; /* 32px */

        (5)設定 a 元素的 aria-label 為 #hero
        設定 a 元素的 Class，
        新增 w-full 為 width: 100%;
        新增 text-center 為 text-align: center;
        新增 py-6 為 
        padding-top: 1.5rem; /* 24px */
        padding-bottom: 1.5rem; /* 24px */
        新增 hover:opacity-90 為 
        a:hover {
                opacity: 0.9;
        }
        文字 Home

        (6)設定 a 元素的 aria-label 為 #rockets
        文字 Our Rockets

        (7)設定 a 元素的 aria-label 為 #testimonials
        文字 Testimonials

        (8)設定 a 元素的 aria-label 為 #contact
        文字 Contact Us
        
        (9)設定 a 元素的 aria-label 為 #footer
        文字 Legal

###  7. Add keyframes and animations
        tailwind.config.js
        (1)加入 keyframes，名稱為 open-menu
        (2)加入 keyframes，名稱為 animation

        index.html
        (3)在 id 為 mobile-menu 的 section 元素
        設定 section 元素的 Class 為 absolute top-68 bg-black w-full text-5xl flex-col justify-center origin-top animate-open-menu hidden
        top-68 為 top: 17rem; /* 272px */
        origin-top 為 transform-origin: top;
        animate-open-menu 為 
        animation: open-menu 0.5s ease-in-out forwards;
        Keyframes: open-menu": {
                "0%": { 
                        transform: "scaleY(0)"
                },
                "80%": { 
                        transform: "scaleY(1.2)"
                },
                "100%": { 
                        transform: "scaleY(1)"},
        }
        移除 flex，
        hidden 為 display: hidden;

###  8. Add a little JavaScript
        (1)新增資料夾 js
        (2)新增 main.js
        (3)宣告 initApp
        (4)宣告 hamburgerBtn，
        使用 document.getElementById 選取 hamburger-button
        (5)宣告 mobileMenu，
        使用 document.getElementById 選取 mobile-menu
        (6)宣告 toggleMenu，
        使用 element.classList 和 toggle，
        針對 mobileMenu 使用 hidden 和 flex 的 Class
        (7)使用 addEventListener 加入 click 監聽事件，
        針對 hamburgerBtn 和 mobileMenu 執行 toggleMenu
        (8)使用 document.addEventListener 加載 initApp
        (9)加入 main.js 於 index.html

        tailwind.config.js
        (10)加入 javascript 路徑為 ./build/js/*.js

###  9. Start Menu Version 2
        第二個版本中的漢堡圖標設置動畫
        (1)在 id 為 hamburger-button 的 button 元素
        移除 hamburger icon &#9776;

        (2)在 id 為 mobile-menu 的 section 元素
        移除 button 元素

        (3)在 id 為 hamburger-button 的 button 元素
        設定 button元素的 Class 為 text-3xl md:hidden cursor-pointer relative w-8 h-8
        新增 relative 為 position: relative;
        新增 w-8 為 width: 2rem; /* 32px */
        新增 h-8 為 height: 2rem; /* 32px */

### 10. Create a Hamburger Menu Icon
        (1)設定 div 元素的 Class，
        新增 bg-white 為 background-color: rgb(255 255 255);
        新增 w-8 為 width: 2rem; /* 32px */
        新增 h-1 為 height: 0.25rem; /* 4px */
        新增 rounded 為 border-radius: 0.25rem; /* 4px */
        新增 absolute 為 position: absolute;
        新增 top-4 為 top: 1rem; /* 16px */
        新增 -mt-0.5 為 margin-top: -0.125rem; /* -2px */

        (2)設定 div 元素的 Class，
        新增 before:content-[''] 為
        div::before {
                
        }
        新增 before:bg-white 為 
        div::before {
                background-color: rgb(255 255 255);
        }
        新增 before:w-8 為 
        div::before {
                width: 2rem; /* 32px */
        }
        新增 before:h-1 為 
        div::before {
                height: 0.25rem; /* 4px */
        }
        新增 before:rounded 為 
        div::before {
                border-radius: 0.25rem; /* 4px */
        }
        新增 before:absolute 為 
        div::before {
                position: absolute;
        }
        新增 before:-translate-x-4 為 
        div::before {
                transform: translateX(-1rem);
        }
        新增 before:-translate-y-3 為 
        div::before {
                transform: translateY(-0.75rem);
        }

        (3)設定 div 元素的 Class，
        新增 after:content-[''] 為 
        div::after {
                
        }
        新增 after:bg-white 為 
        div::after {
                background-color: rgb(255 255 255);
        }
        新增 after:w-8 為 
        div::after {
                width: 2rem; /* 32px */
        }
        新增 after:h-1 為 
        div::after {
                height: 0.25rem; /* 4px */
        }
        新增 after:rounded 為 
        div::after {
                border-radius: 0.25rem; /* 4px */
        }
        新增 after:absolute 為 
        div::after {
                position: absolute;
        }
        新增 after:-translate-x-4 為 
        div::after {
                transform: translateX(-1rem);
        }
        新增 after:translate-y-3 為 
        div::after {
                translateY(0.75rem);
        }

        (4)設定 div 元素的 Class，
        新增 transition-all 為 
                transition-property: all;
                transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
                transition-duration: 150ms;
        新增 duration-500 為 transition-duration: 500ms;
        新增 before:transition-all 為 
        div::before {
                transition-property: all;
                transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
                transition-duration: 150ms;
        }
        新增 before:duration-500 為 
        div::before {
                transition-duration: 500ms;
        }
        新增 after:transition-all 為 
        div::after {
                transition-property: all;
                transition-timing-function: cubic-bezier(0.4, 0, 0.2, 1);
                transition-duration: 150ms;
        }
        新增 after:duration-500 為 
        div::after {
                transition-duration: 500ms;
        }

### 11. Arbitrary Values in Tailwind CSS
        Using arbitrary values
        https://tailwindcss.com/docs/adding-custom-styles#using-arbitrary-values

### 12. Extract Classes with @apply
        Extracting classes with @apply
        https://tailwindcss.com/docs/reusing-styles#extracting-classes-with-apply

### 13. Create the Hamburger Animation
        input.css
        輸入 @layer utilities { ... }
        Class 為 .toggle-btn
        新增 @apply [&>div::before]:translate-y-0 [&>div::before]:rotate-45 [&>div::after]:translate-y-0 [&>div::after]:rotate-45 [&>div]:bg-transparent
        [&>div::before]:translate-y-0 為 
        .toggle-btn > div::before {
                transform: translateY(0px);
        }

        [&>div::before]:rotate-45 為 
        .toggle-btn > div::before {
                transform: rotate(45deg);
        }
        [&>div::after]:translate-y-0 為 
        .toggle-btn > div::after {
                transform: translateY(0px);
        }
        [&>div::after]:-rotate-45 為 
        .toggle-btn > div::before {
                transform: rotate(-45deg);
        }
        [&>div]:bg-transparent 為
        .toggle-btn > div::before {
                background-color: transparent;
        }

### 14. VS Code: Disable Format on Save
        點擊 File > Preferences > Settings
        確認 CSS > Format : Enable
        預設勾選 Enable/disable default CSS formatter

### 15. Add One More Line of JS
        在 toggleMenu 新增
        使用 element.classList 和 toggle，
        針對 hamburgerBtn 使用 toggle-btn 的 Class

### 16. Checking the Hamburger Animation
        input.css
        輸入 @layer utilities { ... }
        Class 為 .toggle-btn
        新增 @apply [&>div::before]:translate-y-0 [&>div::before]:rotate-45 [&>div::after]:translate-y-0 [&>div::after]:rotate-45 [&>div]:bg-transparent [&>div]:rotate-[720deg]
        [&>div]:rotate-[720deg] 為 
        .toggle-btn > div::before {
                transform: rotate(720deg);
        }

### 17. Future Tailwind CSS Topics
        Customization
        Configuration
        https://tailwindcss.com/docs/configuration
        Content Configuration
        https://tailwindcss.com/docs/content-configuration
        Theme Configuration
        https://tailwindcss.com/docs/theme
        Customizing Screens
        https://tailwindcss.com/docs/screens
        Customizing Colors
        https://tailwindcss.com/docs/customizing-colors
        Customizing Spacing
        https://tailwindcss.com/docs/customizing-spacing
        Plugins
        https://tailwindcss.com/docs/plugins
        Presets
        https://tailwindcss.com/docs/presets

### 18. Organize Classes with Prettier
        (1)在 terminal 輸入 npm i prettier-plugin-tailwindcss -D
        (2)在 package.json 的 scripts，
        設定 prettier，指令為 npx prettier --write **/*.html
        (3)在 terminal 輸入 npm run prettier