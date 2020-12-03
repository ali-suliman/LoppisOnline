<template>
  <form>
    <article>
      <img src="../assets/images/form-name.svg" alt="" /><input
        type="text"
        placeholder="Ditt namn"
      />
    </article>
    <article>
      <img src="../assets/images/form-email.svg" alt="" /><input
        type="text"
        placeholder="E-post adress"
      />
    </article>
    <textarea
      name=""
      id=""
      cols="30"
      rows="10"
      placeholder="Ditt medelande"
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
    border-radius: 20px;
    padding: 2rem;
  }

  article {
    width: 100%;
    background: #fff;
    overflow: hidden;
    @include flex();
    flex-direction: row;
    justify-content: flex-start;
    margin: 1rem 0rem;
    border-radius: 20px;

    img {
      margin-left: 1.5rem;
      transform: scale(0.86);
    }

    input {
      border-radius: 2rem;
      padding: 1.05rem 1.2rem;
    }
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
    article {
      border-radius: 30rem;
      margin: 1rem 0rem;
      input {
        padding: 1.6rem;
        font-size: 1rem;
      }
      img {
        transform: scale(1.1);
        margin-left: 2.5rem;
      }
    }

    textarea {
      font-size: 1.3rem;
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
