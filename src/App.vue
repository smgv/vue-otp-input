<script setup lang="ts">
import { ref } from 'vue'
import { OtpInput } from '@toruslabs/vue-components'

const otp = ref('')
</script>

<template>
  <div class="container">
    <code>
      <p>Message Format:</p>
      <br />
      <p>Your verification code is 123456.</p>
      <p>@otp-autofill-pi.vercel.app #123456</p>
    </code>
    <br />
    <p>Enter OTP</p>
    <br />
    <OtpInput
      :length="6"
      @on-complete="(value: string) => (otp = value)"
      :showCta="false"
      @on-change="(value: string) => console.log(value, 'OTP')"
    />
    <br />
    <p>OTP: {{ otp }}</p>
    <br />
    <p>V1.0.2</p>
  </div>
</template>

<style scoped>
.container {
  height: 100dvh;
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  margin: auto;
}
</style>
