<template>
  <form>
    <input type="text" placeholder="Ditt namn" />

    <input type="text" placeholder="Mailadress" />

    <textarea
      name=""
      id=""
      cols="30"
      rows="10"
      placeholder="Medelande"
    ></textarea>

    <button class="send">skicka</button>
  </form>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import "../styles/global-styles.scss";
form {
  width: 100%;
  margin: 1rem;
  padding: 0.8rem 1.2rem;
  background: rgba(252, 229, 217, 0.5);
  border-radius: 20px;
  @include flex();
  justify-content: flex-start;

  input,
  textarea {
    width: 100%;
    border: none;
    background: #fff;

    &::placeholder {
      color: #aaa;
    }
  }

  textarea {
    border-radius: 10px;
    padding: 2rem;
    margin: 0.5rem;
    font-family: $p-font;
  }

  input {
    margin: 0.5rem 0rem;
    border-radius: 20px;
    width: 100%;
    background: #fff;
    border-radius: 2rem;
    padding: 1.05rem 2rem;
  }

  .send {
    @include cta-mobile();
    margin: 1rem 0rem;
    padding: 0.6rem 3rem;
  }
}

@media screen and (min-width: 1200px) {
  form {
    padding: 1rem 2rem;

    input {
      padding: 1.6rem 2rem;
      font-size: 1rem;
      margin: 0.8rem 0rem;
    }

    textarea {
      font-size: 1rem;
      margin: 1rem;
    }

    .send {
      @include cta();
      @include cta-animation;
      width: initial;
      padding: 1rem 4rem;
      margin: 0.8rem 0rem;
      align-self: flex-end;
    }
  }
}
</style>
