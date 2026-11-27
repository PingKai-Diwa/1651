<template>
  <div class="page">
    <form class="card" @submit.prevent="submitForm">
      <h1>สมัครสมาชิก</h1>
      <p class="subtitle">ระบบประเมินบุคลากร HR</p>

      <label>
        Username
        <input v-model="username" placeholder="ชื่อผู้ใช้" />
      </label>

      <label>
        Email
        <input v-model="email" type="email" placeholder="you@example.com" />
      </label>

      <label>
        Password
        <input v-model="password" type="password" placeholder="รหัสผ่าน" />
      </label>

      <button type="submit" :disabled="loading">
        {{ loading ? 'กำลังส่งข้อมูล...' : 'Sign Up' }}
      </button>

      <p v-if="message" class="message" :class="{ error: isError }">
        {{ message }}
      </p>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      username: '',
      email: '',
      password: '',
      message: '',
      isError: false,
      loading: false
    };
  },
  methods: {
    async submitForm() {
      this.loading = true;
      this.message = '';
      try {
        const response = await fetch('http://localhost:3000/signup', {
          method: 'POST',
          headers: {
            'Content-Type': 'application/json'
          },
          body: JSON.stringify({
            username: this.username,
            email: this.email,
            password: this.password
          })
        });

        const result = await response.json();
        this.isError = !response.ok;
        this.message = result.message;

        if (response.ok) {
          this.username = '';
          this.email = '';
          this.password = '';
        }
      } catch (error) {
        this.isError = true;
        this.message = 'Error: ' + error.message;
      } finally {
        this.loading = false;
      }
    }
  }
};
</script>

<style scoped>
.page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #e0f7ec, #e8f0ff);
  padding: 20px;
  box-sizing: border-box;
}

.card {
  width: 100%;
  max-width: 380px;
  background: #ffffff;
  padding: 32px 28px;
  border-radius: 16px;
  box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  gap: 16px;
}

h1 {
  margin: 0;
  font-size: 26px;
  text-align: center;
  color: #213547;
}

.subtitle {
  margin: -8px 0 4px;
  text-align: center;
  font-size: 14px;
  color: #7b8794;
}

label {
  display: flex;
  flex-direction: column;
  gap: 6px;
  font-size: 14px;
  font-weight: 600;
  color: #3e4c59;
}

input {
  padding: 11px 14px;
  border: 1.5px solid #d3dce6;
  border-radius: 10px;
  font-size: 15px;
  outline: none;
  transition: border-color 0.2s, box-shadow 0.2s;
}

input:focus {
  border-color: #42b883;
  box-shadow: 0 0 0 3px rgba(66, 184, 131, 0.2);
}

button {
  margin-top: 6px;
  padding: 12px;
  border: none;
  border-radius: 10px;
  background: #42b883;
  color: #fff;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: background 0.2s, transform 0.1s;
}

button:hover:not(:disabled) {
  background: #36a374;
}

button:active:not(:disabled) {
  transform: scale(0.98);
}

button:disabled {
  opacity: 0.6;
  cursor: not-allowed;
}

.message {
  margin: 0;
  padding: 10px 12px;
  border-radius: 8px;
  text-align: center;
  font-size: 14px;
  background: #e6f7ee;
  color: #1e7e52;
}

.message.error {
  background: #fdecea;
  color: #c0392b;
}
</style>