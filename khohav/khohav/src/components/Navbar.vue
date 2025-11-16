<template>
  <nav class="navbar">
    <div class="logo">✨ khohav ✨</div>
    <ul class="nav-links">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About Us</a></li>
      <li><a href="#products">Products</a></li>
      <li><a href="#checkout">Checkout</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</template>

<style scoped>
.navbar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 2rem;
  background-color: black;
  border-bottom: 2px solid #d4a353;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  position: sticky;
  top: 0;
  z-index: 1000;
}

.logo {
  font-size: 2rem;
  font-weight: 700;
  color: #d4a353;
  font-family: 'Georgia', serif;
  letter-spacing: 1px;
  text-shadow: 1px 1px 3px rgba(204, 51, 102, 0.4);
  cursor: pointer;
  transition: transform 0.3s ease, color 0.3s ease;
}

.logo:hover {
  transform: scale(1.05);
  color: white;
}

.nav-links {
  list-style: none;
  display: flex;
  gap: 1.5rem;
  margin: 0;
  padding: 0;
}

.nav-links li a {
  text-decoration: none;
  color: white;
  font-weight: 600;
  font-size: 1rem;
  transition: color 0.3s ease, transform 0.3s ease;
}

.nav-links li a:hover {
  color: #d4a353;
  transform: scale(1.1);
}
</style>



