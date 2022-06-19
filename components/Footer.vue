<template>
  <footer class="grid-container">
    <div class="grid-inner">
      <div class="footer-links">
        <ul class="footer-links--main">
          <li><a href="./docs/resume.pdf">View Resume</a></li>
          <li><a href="mailto:stephdolgo@gmail.com?subject=Inquiry:">Send Email</a></li>
        </ul>
        <ul class="footer-links--social">
          <li><a href="https://www.github.com/Stephdolgo"><img src="/icons/github-icon.svg" alt="Github icon"></a></li>
          <li><a href="https://www.dribbble.com/StephaniaD"><img src="/icons/dribbble-icon.svg" alt="Dribbble icon"></a></li>
          <li><a href="https://www.behance.net/StephaniaD"><img src="/icons/behance-icon.svg" alt="Behance icon"></a></li>
        </ul>
      </div>
      <div class="copyright">©2022 Stephania Dolgopolova. All Rights Reserved</div>
    </div>
  </footer>
</template>

<script>
    export default {
        name: 'Footer'
    }
</script>

<style lang="scss">

  footer {
    padding: 5px;
    position: sticky;
    color: var(--light);
    background-color: var(--footer);

    .footer-links,
    .footer-links--main,
    .footer-links--social {
      display: flex;
      flex-direction: row;
      align-items: center;

      .footer-links--main  {
        margin-left: 0;
        padding-left: 0;

        li {
          padding-left: 0;
          margin-right: 20px;
          font-size: 14px;
        }
      }

      .footer-links--social  {
        padding-left: 0;

        li {
          margin: 20px;
        }
        li:last-child {
          margin-right: 15px;
        }
      }
    }

    .footer-links {
      justify-content: space-between;
      align-content: stretch;
    }
    
    a {
      color: var(--light);
      text-decoration: none;
      opacity: 1;
      padding: 10px;

      &:hover {
        opacity: 0.75;
        justify-self: end;
      }

    ul {
      flex-direction: row;

      }
    }
    .copyright {
      text-align: right;
      font-size: 11px;
      opacity: 0.7;
      padding-bottom: 20px;
      display: flex;
      justify-content: flex-end;
    }
  }

</style>