<template>
  <div id="div">
    <div id="div2">
      <div class="input-group">
        <select name="" id="">
          <option>Escolha uma cidade</option>
          <option value="Maputo" >Maputo</option>
          <option value="Xai-Xai">Xai-Xai</option>
          <option value="Inhambane" >Inhambane</option>
          <option value="Beira" >Beira</option>
          <option value="Chimoio" >Chimoio</option>
          <option value="Tete" >Tete</option>
          <option value="Quelimane" >Quelimane</option>
          <option value="Nampula" >Nampula</option>
          <option value="Pemba" >Pemba</option>
          <option value="Lichinga" >Lichinga</option>
        </select>
        <div class="input-group-append">
          <button type="button" class="btn btn-outline-secondary">
            Pesquisar
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "serachComponent",
};
</script>

<style scoped>
#div {
  display: flex;
  justify-content: center;
  align-items: center;
}

#div2 {
  margin-top: 0px;
  border-radius: 5px;
  height: 50px;
  width: 450px;
  background: white;
  display: flex;
  justify-content: center;
}

.input-group {
  width: 100%;
}

.input-group select {
  width: 74%;
  background: transparent;
  border: transparent;
  outline: none;
  margin-left: 5px;
}

option {
  background: white;
}

.input-group button {
  margin-left: 10px;
  margin-top: 3px;
  width: 100px;
  border: transparent;
  height: 45px;
  background: #411530c1;
  color: white;
}
</style>