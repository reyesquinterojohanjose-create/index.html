<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DiamondZone FF PRO</title>
<script src="https://js.stripe.com/v3/"></script>
<style>
body{margin:0;font-family:Arial;background:#020617;color:#fff}
header{padding:15px 30px;background:#0f172a;display:flex;justify-content:space-between}
h1{color:#ff3c00}
.container{padding:20px}
.product{background:#0f172a;padding:15px;border-radius:10px;margin-bottom:10px}
.btn{background:#ff3c00;border:none;padding:8px 12px;color:white;border-radius:6px;cursor:pointer;margin:3px}
input, select{padding:8px;margin:5px 0;width:100%;border-radius:6px;border:none}
.admin{background:#111827;padding:20px;border-radius:10px;margin-top:20px;display:none}
.login{max-width:300px;margin:100px auto;background:#111827;padding:20px;border-radius:10px}
</style>
</head>
<body>

<header>
<h1>💎 DiamondZone FF PRO</h1>
<button class="btn" onclick="showLogin()">Admin</button>
</header>

<div class="container">
<h2>🌍 Selecciona tu país</h2>
<select id="country" onchange="render()">
<option value="CO">Colombia</option>
<option value="OTHER">Otro país</option>
</select>

<h2>🛍️ Tienda</h2>
<div id="products"></div>

<h2>💳 Pago</h2>
<input type="text" id="playerId" placeholder="ID del jugador">
<button class="btn" onclick="checkout()">Pagar con tarjeta</button>

<div class="admin" id="adminPanel">
<h2>⚙️ Panel Admin</h2>
<input type="text" id="name" placeholder="Nombre">
<input type="number" id="price" placeholder="Precio USD">
<button class="btn" onclick="addProduct()">Agregar</button>

<h3>✏️ Editar productos</h3>
<div id="adminProducts"></div>
</div>
</div>

<div class="login" id="loginBox" style="display:none">
<h3>Login Admin</h3>
<input type="password" id="pass" placeholder="Contraseña">
<button class="btn" onclick="login()">Entrar</button>
</div>

<script>
let stripe = Stripe('TU_PUBLIC_KEY_AQUI');

let products = JSON.parse(localStorage.getItem('products')) || [
{name:"100 Diamantes",price:1.99},
{name:"310 Diamantes",price:4.99},
{name:"520 Diamantes",price:7.99},
{name:"1060 Diamantes",price:14.99}
];

let selectedProduct = null;

function save(){localStorage.setItem('products',JSON.stringify(products));}

function render(){
const country=document.getElementById('country').value;
const container=document.getElementById('products');
container.innerHTML="";

products.forEach((p,i)=>{
// Restricción por país
if(country==='OTHER' && (p.name.includes('100') || p.name.includes('310'))){return;}

container.innerHTML+=`<div class="product">
<h3>${p.name}</h3>
<p>$${p.price}</p>
<button class="btn" onclick="selectProduct(${i})">Comprar</button>
</div>`;
});

renderAdmin();
}

function renderAdmin(){
const admin=document.getElementById('adminProducts');
admin.innerHTML="";
products.forEach((p,i)=>{
admin.innerHTML+=`
<div class="product">
<input value="${p.name}" onchange="updateName(${i}, this.value)">
<input type="number" value="${p.price}" onchange="updatePrice(${i}, this.value)">
<button class="btn" onclick="deleteProduct(${i})">Eliminar</button>
</div>`;
});
}

function updateName(i,val){products[i].name=val;save();render();}
function updatePrice(i,val){products[i].price=parseFloat(val);save();render();}

function selectProduct(i){selectedProduct=products[i];alert('Seleccionaste '+products[i].name);}

function checkout(){
if(!selectedProduct){alert('Selecciona un producto');return;}

fetch('http://localhost:3000/create-checkout-session',{
method:'POST',headers:{'Content-Type':'application/json'},
body:JSON.stringify({product:selectedProduct})
})
.then(res=>res.json())
.then(data=>stripe.redirectToCheckout({sessionId:data.id}));
}

function addProduct(){
const name=document.getElementById('name').value;
const price=parseFloat(document.getElementById('price').value);
if(name&&price){products.push({name,price});save();render();}
}

function deleteProduct(i){products.splice(i,1);save();render();}

function showLogin(){document.getElementById('loginBox').style.display='block';}

function login(){
const pass=document.getElementById('pass').value;
if(pass==='admin123'){
document.getElementById('adminPanel').style.display='block';
document.getElementById('loginBox').style.display='none';
}else{alert('Contraseña incorrecta');}
}

render();
</script>

</body>
</html>
