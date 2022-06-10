<template>
  <div id="NovoTicket" class="modal">
    <div>
      <a href="#fechar" title="Fechar" class="fechar">x</a>
      <h1>Novo Ticket</h1>
      <form>
        <div class="input-field" style="width: 100%;">
          <h6>Título</h6>
          <input type="text">
        </div>
        <div class="input-field" style="width: 20%;">
          <h6>Empresa</h6>
          <input type="text">
        </div>
        <div class="input-field" style="width: 20%;">
          <h6>Cliente</h6>
          <input type="text">
        </div>
        <div class="input-field" style="width: 20%;">
          <h6>Tipo de problema</h6>
          <input type="text">
        </div>
        <div class="input-field" style="width: 20%;">
          <h6>Analista</h6>
          <input type="text">
        </div>
        <div class="input-field" style="width: 100%;">
          <h6>Descrição do cliente</h6>
          <textarea type="text"></textarea>
        </div>
        <div class="input-field" style="width: 100%;text-align: right;">
          <button type="submit">Criar</button>
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Modal',
    data () {
        return {

        }
    }
}
</script>

<style scoped>
/* * {
  border: 1px solid salmon;
} */
.modal {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    /* margin: 64px; */
    background: rgba(0, 0, 0, 0.8);
    z-index: 99999;
    opacity:0;
    transition: opacity 200ms ease-in;
    pointer-events: none;
}
.modal:target {
  opacity: 1;
  pointer-events: auto;
}
.modal > div {
  position: fixed;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;

  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  margin: 64px;
  padding: 15px 20px;
  background: #fff;
}
.modal > div form {
  display: flex;
  flex-wrap: wrap;
  justify-content: flex-start;
  align-items: flex-start;
  width: 80%;
  height: 80%;
}
.fechar {
  position: absolute;
  right: 0;
  top: 0;
  width: 30px;
  line-height: 30px;
  text-align: center;
  font-size: 16px;
  background: #ff4545;
  color: #8d0000;
  text-decoration: unset;
}
.fechar:hover {
  background: #ff2f2f;
}
h1 {
  font-size: 30px;
  margin-bottom: 32px;
  width: 100%;
  padding-left: 10%;
}
.input-field {
  margin: 0 16px 0 16px;
}
.input-field button {
  width: 100px;
  height: 30px;
}
input {
  width: 100%;
}
textarea {
  width: 100%;
  margin-top: 4px;
}
button {
  border: none;
  background-color: rgb(191, 191, 191);
}
button:hover {
  background-color: rgb(146, 146, 146);
}
</style>