<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>AURA HOME</title>
<style>
  :root{ --accent:#d7b4b4; --bg:#faf2e4; --text:#111; }
  *{box-sizing:border-box}
  body{margin:0;font-family:Arial, sans-serif;background:var(--bg);padding-top:80px;padding-bottom:80px;}
  header{position:fixed;top:0;left:0;width:100%;background:var(--accent);padding:14px;z-index:1000}
  nav{max-width:1200px;margin:0 auto;display:flex;gap:18px;justify-content:center;align-items:center}
  nav a{color:var(--text);text-decoration:none;padding:6px 10px;border-radius:6px;cursor:pointer;font-weight:600}
  nav a.active{color:#fff;background:rgba(0,0,0,0.08)}
  .container{max-width:1200px;margin:0 auto;padding:20px}
  section{display:none;min-height:calc(100vh - 170px);padding-top:20px}
  section.show{display:block}
  /* Home */
  #home .title{font-size:clamp(36px,6vw,72px);text-align:center;margin-top:60px}
  #home .sub{font-size:clamp(14px,2.2vw,22px);text-align:center;margin-top:12px;color:#333}
  /* Forms */
  .form-box{max-width:420px;margin:0 auto}
  input{width:100%;padding:10px;margin:10px 0;border:1px solid rgba(0,0,0,0.12);border-radius:8px;font-size:15px}
  button.btn{background:var(--accent);border:none;padding:10px 14px;border-radius:8px;cursor:pointer;font-weight:700}
  /* About: text then centered image below */
  #about .about-inner{max-width:900px;margin:0 auto;background:#fff;padding:28px;border-radius:12px;box-shadow:0 8px 20px rgba(0,0,0,0.08)}
  #about .about-text{font-size:18px;line-height:1.6;color:#2a2a2a}
  .about-image-box{display:flex;justify-content:center;margin-top:20px}
  .about-image-box img{width:60%;max-width:540px;border-radius:12px;box-shadow:0 6px 18px rgba(0,0,0,0.12)}
  /* Catalog */
  .grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:20px}
  .product-card{background:#fff;padding:12px;border-radius:10px;text-align:center;box-shadow:0 6px 18px rgba(0,0,0,0.06)}
  .product-card img{width:100%;height:180px;object-fit:cover;border-radius:8px}
  .product-card h4{margin:10px 0 6px;font-size:16px}
  .product-card p{margin:0;color:#444}
  /* Cart */
  .cart-box{max-width:900px;margin:0 auto;background:#fff;padding:18px;border-radius:10px;box-shadow:0 6px 20px rgba(0,0,0,0.06)}
  .cart-item{display:flex;justify-content:space-between;padding:8px 0;border-bottom:1px dashed rgba(0,0,0,0.06)}
  .cart-empty{color:#666;padding:12px 0}
  footer{position:fixed;bottom:0;left:0;width:100%;background:var(--accent);padding:12px;text-align:center}
  /* Responsive */
  @media(max-width:720px){
    nav{gap:8px}
    .about-image-box img{width:90%}
    .product-card img{height:150px}
  }
  @media(max-width:420px){
    .container{padding:12px}
  }
</style>
</head>
<body>

<header>
  <nav id="mainNav">
    <a data-target="home">Главная</a>
    <a data-target="login">Войти</a>
    <a data-target="register">Регистрация</a>
    <a data-target="about">О нас</a>
    <a data-target="catalog">Каталог</a>
    <a data-target="cart">Корзина </a>
  </nav>
</header>

<main class="container">
  <!-- HOME -->
  <section id="home" class="show">
    <div class="title">ΔURA HOME</div>
    <div class="sub">«Атмосфера вашего дома»</div>
  </section>

  <!-- LOGIN -->
  <section id="login">
    <h2 style="text-align:center">Войти</h2>
    <div class="form-box">
      <label style="display:block;text-align:left;font-weight:600">E-mail</label>
      <input id="loginEmail" type="email" placeholder="you@mail.ru">
      <label style="display:block;text-align:left;font-weight:600">Пароль</label>
      <input id="loginPass" type="password" placeholder="••••••">
      <button class="btn" id="loginBtn">Войти</button>
    </div>
  </section>

  <!-- REGISTER -->
  <section id="register">
    <h2 style="text-align:center">Регистрация</h2>
    <div class="form-box">
      <label style="display:block;text-align:left;font-weight:600">E-mail</label>
      <input id="regEmail" type="email" placeholder="you@mail.ru">
      <label style="display:block;text-align:left;font-weight:600">Пароль</label>
      <input id="regPass" type="password" placeholder="придумайте пароль">
      <button class="btn" id="regBtn">Зарегистрироваться</button>
    </div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <div class="about-inner">
      <div class="about-text">
        <h2>О нас</h2>
         <p>Мы создаём коллекции ароматов, которые помогают наполнить дом теплом, уютом 
                и атмосферой спокойствия. Наши арома-композиции тщательно подобраны, 
                чтобы пробуждать эмоции, дарить гармонию и превращать пространство в место силы.</p>
        <p style="margin-top:12px;">Все наши изделия производятся вручную: от свечей до диффузоров. 
                Мы используем натуральные компоненты, безопасные масла 
                и экологичные материалы — чтобы каждая деталь дарила эстетическое удовольствие.</p>   
      </div>
    </div>
  </section>

  <!-- CATALOG -->
  <section id="catalog">
    <h2 style="text-align:center;margin-bottom:14px">Каталог</h2>
    <div id="catalogGrid" class="grid"></div>
  </section>

  <!-- CART -->
  <section id="cart">
    <h2 style="text-align:center;margin-bottom:14px">Корзина</h2>
    <div class="cart-box">
      <div id="cartItems" class="cart-items"><div class="cart-empty">Ваша корзина пуста</div></div>
      <div style="text-align:right;margin-top:12px;font-weight:700" id="cartTotal">Итого: 0 ₽</div>
      <div style="text-align:center;margin-top:12px"><button class="btn" id="checkoutBtn">Оформить заказ</button></div>
    </div>
  </section>
</main>

<footer>+7 (946) 324-69-22 | AUROHOME@MAIL.RU</footer>

<script>
/* --- Навигация и подсветка активного пункта --- */
const navLinks = document.querySelectorAll('nav a');
function showSection(id){
  document.querySelectorAll('main section').forEach(s=>s.classList.remove('show'));
  const sec = document.getElementById(id);
  if(sec) sec.classList.add('show');

  navLinks.forEach(a=>a.classList.remove('active'));
  const active = Array.from(navLinks).find(a=>a.dataset.target === id);
  if(active) active.classList.add('active');
}
navLinks.forEach(a=>{
  a.addEventListener('click', e=>{
    e.preventDefault();
    const t = a.dataset.target;
    showSection(t);
  });
});
/* стартовая страница */
showSection('home');

/* --- Продукты (12 шт.) --- */
const products = [
  {name:"Диффузор вишня", price:599, img:"https://i.pinimg.com/736x/7e/5a/61/7e5a61c7c272e7947375eee6ef5763cb.jpg"},
  {name:"Диффузор клубника", price:599, img:"https://i.pinimg.com/736x/8c/3d/47/8c3d479d5ca7f20d0bb0e3b0a219c2f9.jpg"},
  {name:"Диффузор лаванда", price:599, img:"https://i.pinimg.com/736x/31/12/4d/31124d8dbf54c1fac1e0adf7eecca40f.jpg"},
  {name:"Свеча малина", price:1199, img:"https://i.pinimg.com/736x/4e/51/25/4e5125acdea4ed52b21965b1b845a70d.jpg"},
  {name:"Свеча кофе", price:899, img:"https://i.pinimg.com/736x/48/df/6c/48df6c8d8a69dca38ae7cc1a2ddcaad4.jpg"},
  {name:"Свеча ваниль", price:699, img:"https://i.pinimg.com/736x/64/2d/7a/642d7a3187ad949e90d0d8a7f2433c66.jpg"},
  {name:"Аромамасло апельсин", price:499, img:"https://i.pinimg.com/736x/7a/0d/4a/7a0d4a030c38da7a5e768f8b1a79cd13.jpg"},
  {name:"Аромамасло лаванда", price:499, img:"https://i.pinimg.com/736x/8b/20/4f/8b204f497d25df59b386353d401dd471.jpg"},
  {name:"Аромаспрей хлопок", price:799, img:"https://i.pinimg.com/736x/52/50/4e/52504eba86e32f0f82effe40329d404a.jpg"},
  {name:"Аромаспрей весна", price:799, img:"https://i.pinimg.com/736x/ae/b3/a7/aeb3a744a29d2ce143bbd44a14bcbb10.jpg"},
  {name:"Саше цветочное", price:349, img:"https://i.pinimg.com/736x/59/15/70/59157061e8b9ac2b33cd807401e33ad3.jpg"},
  {name:"Саше ванильное", price:349, img:"https://i.pinimg.com/736x/eb/56/62/eb566257f6933db45b2c338387046d0b.jpg"}
];

/* --- Рендер каталога (делегирование) --- */
const catalogGrid = document.getElementById('catalogGrid');
function renderCatalog(){
  catalogGrid.innerHTML = '';
  products.forEach((p,i)=>{
    const d = document.createElement('div');
    d.className = 'product-card';
    d.innerHTML = `
      <img src="${p.img}" alt="${p.name}">
      <h4>${p.name}</h4>
      <p>${p.price} ₽</p>
      <button data-add="${i}" class="btn">В корзину</button>
    `;
    catalogGrid.appendChild(d);
  });
}
renderCatalog();

/* --- Корзина --- */
let cart = [];
const cartItemsEl = document.getElementById('cartItems');
const cartTotalEl = document.getElementById('cartTotal');

function renderCart(){
  cartItemsEl.innerHTML = '';
  if(cart.length === 0){
    cartItemsEl.innerHTML = '<div class="cart-empty">Ваша корзина пуста</div>';
    cartTotalEl.textContent = 'Итого: 0 ₽';
    return;
  }
  let total = 0;
  cart.forEach((item, idx)=>{
    total += item.price;
    const div = document.createElement('div');
    div.className = 'cart-item';
    div.innerHTML = `<div>${item.name}</div><div>${item.price} ₽</div>`;
    cartItemsEl.appendChild(div);
  });
  cartTotalEl.textContent = `Итого: ${total} ₽`;
}

/* Делегирование кликов по кнопкам "В корзину" */
document.addEventListener('click', (e)=>{
  const add = e.target.closest('button[data-add]');
  if(add){
    const id = Number(add.getAttribute('data-add'));
    if(!Number.isNaN(id) && products[id]) {
      cart.push(products[id]);
      renderCart();
      // показать быстрый визуальный отклик
      add.textContent = 'Добавлено';
      setTimeout(()=> add.textContent = 'В корзину', 700);
    }
  }
});

/* Регистрация/Вход — простая демонстрация */
// Проверка email (наличие @)
function validateEmail(email) {
  if (!email.includes("@")) {
    alert("Ошибка: e-mail должен содержать символ @");
    return false;
  }
  return true;
}

/* --- Регистрация --- */
document.getElementById('regBtn')?.addEventListener('click', ()=>{
  const email = document.getElementById('regEmail').value.trim();
  const pass = document.getElementById('regPass').value.trim();

  if (!validateEmail(email)) return;

  if (pass.length < 1) {
    alert("Введите пароль");
    return;
  }

  alert('Регистрация (демо) — успешно');
  showSection('home');
});

/* --- Вход --- */
document.getElementById('loginBtn')?.addEventListener('click', ()=>{
  const email = document.getElementById('loginEmail').value.trim();
  const pass = document.getElementById('loginPass').value.trim();

  if (!validateEmail(email)) return;

  if (pass.length < 1) {
    alert("Введите пароль");
    return;
  }

  alert('Вход (демо) — успешно');
  showSection('home');
});
/* Кнопка оформления */
document.getElementById('checkoutBtn')?.addEventListener('click', ()=>{
  if(cart.length === 0) { alert('Корзина пуста'); return; }
  alert('Заказ оформлен! Спасибо :)');
  cart = [];
  renderCart();
  showSection('home');
});

</script>
</body>

</html>
