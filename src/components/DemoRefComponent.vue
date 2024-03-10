<template>
  <div style="margin-top: 30px">
    <button @click="handleUploadAvatar()">Upload file</button>
    <input
      type="file"
      style="display: none"
      ref="fileUpload"
      @change="(e) => handleChangeFile(e)"
    />
  </div>
</template>
<script>
export default {
  methods: {
    handleUploadAvatar() {
      this.$refs.fileUpload.click();
    },
    handleChangeFile(e) {
      console.log("files", e.target.files);
    },
  },
};
</script>
<style></style>
