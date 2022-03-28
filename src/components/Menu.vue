<template>
  <div class="menuContainer">
    <div class="greetingSection">
      <div class="greetingName">
        <div class="greeting">Hello</div>
        <h3 class="name">Mahier 님</h3>
      </div>
      <div class="barcode">
        <img class="barcodePic" src="../assets/barcode.jpg" alt="" />
      </div>
    </div>
    <div class="menu">
      <div class="menuItem">
        <div class="menuItemImage">
          <router-link to="/order"
            ><img class="IconPic" src="../assets/coffeeIcon.png" alt=""
          /></router-link>
        </div>
        <div class="menuItemName">Order/주문</div>
      </div>
      <div class="menuItem">
        <div class="menuItemImage">
          <img class="IconPic" src="../assets/coffeeIcon.png" alt="" />
        </div>
        <div class="menuItemName">Coupons/쿠폰</div>
      </div>
      <div class="menuItem">
        <div class="menuItemImage">
          <img class="IconPic" src="../assets/coffeeIcon.png" alt="" />
        </div>
        <div class="menuItemName">Events/이벤트</div>
      </div>
      <div class="menuItem">
        <div class="menuItemImage">
          <img class="IconPic" src="../assets/coffeeIcon.png" alt="" />
        </div>
        <div class="menuItemName">Stamps/우표</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style scoped>
.menuContainer {
  background: white;
  margin-top: 50px;
}

.greetingSection {
  display: flex;
  margin-left: 100px;
}

.barcodePic {
  width: 10%;
}

.menu {
  display: flex;
  margin-top: 100px;
}

.IconPic {
  width: 10%;
}
</style>
