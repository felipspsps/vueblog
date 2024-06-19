<script>
import { useRouter } from 'vue-router';

export default {
  setup() {
    var email = '';
    var password = '';
    const router = useRouter();

    const goToPosts = () => {
      router.push('/post'); 
    };
    return { email, password, goToPosts };
  },
};
</script>

<template>
    <div class="login-container">
      <div class="login-card">
        <form @submit.prevent="goToPosts">
          <div class="form-group">
            <label for="email">E-mail:</label>
            <input type="email" id="email" v-model="email" class="input-field">
          </div>
          <div class="form-group">
            <label for="password">Senha:</label>
            <input type="password" id="password" v-model="password" class="input-field">
          </div>
          <div id="botao" >
            <button type="submit" class="btn btn-primary">Entrar</button>
          </div>
        </form>
      </div>
    </div>
</template>

<style scoped>
.login-container {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: white;
}

.login-card {
  border: 1px solid rgba(0, 0, 0, 0.1);
  background-color: #fff;
  padding: 40px;
  border-radius: 10px;
  box-shadow: 8px 8px 2px 2px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 20px;
}

.input-field {
  width: 100%;
  padding: 12px;
  border: 1px solid #ddd;
  border-radius: 5px;
  box-sizing: border-box;
}
#botao{
  margin: auto;
  text-align: center;
}
button{
  width: 120px;
}
</style>