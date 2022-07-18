<template>
  <header>
    <div class="menu-esquerdo">
      <span><RouterLink to="/">Home</RouterLink></span>
      <Span>|</Span>
      <span><RouterLink to="/times">Times</RouterLink></span>
      <Span>|</Span>
      <span><RouterLink to="/jogadores">Jogadores</RouterLink></span>
    </div>
    <div class="menu-direita"><span>Sair</span></div>
  </header>
</template>

<style>
header {
  background-color: rgb(89, 89, 182);
  height: 15%;
  font-size: 1.3rem;
  color: white;
  display: flex;
  align-items: center;
  padding-left: 1.5rem;
  justify-content: space-between;
}
header span {
  padding: 0 20px;
}
</style>
