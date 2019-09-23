<template>
  <div>
    <h1 class="text-center">RSA 加密解密 -- rsaencrypt</h1>
    <div class="box">
      <div class="box-item">
        <div>用于加密的公钥：</div>
        <textarea v-model="key.publicKey" @input="inputPublicKey" rows="15"></textarea>
      </div>
      <div class="box-item">
        <div>用于解密的私钥：</div>
        <textarea v-model="key.privateKey" @input="inputPrivateKey" rows="15"></textarea>
      </div>
    </div>
    <div class="box">
      <div class="box-item">
        <div>明文：</div>
        <textarea v-model="decryptData" rows="20"></textarea>
      </div>
      <div class="box-item">
        <div>密文：</div>
        <textarea v-model="encryptData" rows="20"></textarea>
      </div>
    </div>
    <div class="text-center">
      <button @click="encrypt">加密</button>
      <button @click="decrypt">解密</button>
    </div>
  </div>
</template>

<script>
import { encryptPublicLong, decryptPrivateLong } from "@lsqswl/rsaencrypt";
export default {
  name: "rsaencrypt",
  data() {
    return {
      key: {
        publicKey:
          "MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQCbwgUR4qyEHDm/S2EizPCnTIFgJrqN8SXYmDzZW6scOgz4ZM9IUDNa0lfIw2y8qcd+QS25ZXj+YrOyGhODyn3lD6hGR5NMwfQhV+kPAQEKft/Ub8+E3ITvQdZOCfpYALcMGZhgwWJQULuH2ThKriX4qHCuvkLnUYv/U9O5qU5dnQIDAQAB",
        privateKey:
          "MIICdQIBADANBgkqhkiG9w0BAQEFAASCAl8wggJbAgEAAoGBAJvCBRHirIQcOb9LYSLM8KdMgWAmuo3xJdiYPNlbqxw6DPhkz0hQM1rSV8jDbLypx35BLblleP5is7IaE4PKfeUPqEZHk0zB9CFX6Q8BAQp+39Rvz4TchO9B1k4J+lgAtwwZmGDBYlBQu4fZOEquJfiocK6+QudRi/9T07mpTl2dAgMBAAECgYAHHjfDGHvP0cZl0pkO0RTSYHGtJjfyUqnrGxH00Pah5JlBJMJASMIADYrLdvraKFwgjfP7/AIqhfI2WnC33iIgqnTp0q+mON5TZhZCR1W7iLe5LBVN5TlUbnIQfTtCu3IyfdNCDSO/Ok5ITZGYXLSwces7vwhk+0LXjILaTydY9QJBAMno8GGHNUcxt3xUi7xF5jGlX6y27MRLTA3eW6QQzR5huVWosG2saU7zgkhFlU38+Ei+XjgFyGP7jYX3QFNhNH8CQQDFe/Tq9ubMrxK4/d+IFcHha97apYunziNvlphzx94/gghQZPjcqPbQwpWw7LspiWe/Xxb59gD0lp1zvEPTxq/jAkAOqjSLYN6lxR6mkR11Fz6Y7IH+cWrQ9wcXGsddKzs6sa5cYlwuGw+rBFS6GxO1DmKaJfmB6Cmd2W92A3dQlwbRAkAuQe3Jh9HiCfQxvs24O5hxa+oEfxhqUv+76KOHIz7s01GNO0mLrkw59ApKKflhLl1N10EzhasNn6X78RJWLckPAkB4kGsvR7Q53V4tgNStJjYJS5LbxjOy15ld4Z4x/mJSKBgghisoAjrEvkrr4glcl3L9VLVICxrDsYmn5oGKfOpN"
      },
      decryptData: "",
      encryptData: ""
    };
  },
  methods: {
    async encryption(str) {
      return await encryptPublicLong(str, this.key.publicKey);
    },
    async decryption(str) {
      return await decryptPrivateLong(str, this.key.privateKey);
    },
    encrypt() {
      this.encryption(this.decryptData)
        .then(result => {
          this.encryptData = result;
        })
        .catch(err => {
          console.log(err);
        });
    },
    decrypt() {
      this.decryption(this.encryptData)
        .then(result => {
          this.decryptData = result;
        })
        .catch(err => {
          console.log(err);
        });
    },
    inputPublicKey() {},
    inputPrivateKey() {}
  }
};
</script>
<style scoped>
.box {
  display: flex;
  justify-content: space-around;
  width: 100%;
}
.box-item {
  width: 48%;
}
textarea {
  width: 100%;
}
</style>