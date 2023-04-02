<template>
  <div class="gitalk-container">
    <div id="gitalk-container"></div>
  </div>
</template>
<script>
import md5 from 'md5';
import Gitalk from 'gitalk';
import 'gitalk/dist/gitalk.css';
export default {
  name: 'git-talk',
  mounted() {
    const commentConfig = {
      clientID: '2c6895018ae1351b8b2b',
      clientSecret: 'c6f42ede72eb023bd6c6616480574ee0b5b6a149',
      repo: 'compiler-sfc',
      owner: 'readVueCode',
      admin: ['zqy233', 'ys3322'],
      id: md5(location.pathname),
      distractionFreeMode: false,
    };
    const gitalk = new Gitalk(commentConfig);
    gitalk.render('gitalk-container');
  },
};
</script>
<style>
.gt-container .gt-header-textarea {
  color: #000;
}
.dark .gt-container .gt-header-textarea {
  background-color: #1a1a1a;
}
.dark .gt-container .gt-header-preview {
  background-color: #1a1a1a;
  color: #fff;
}
.dark .gt-container .gt-header-textarea {
  color: #fff;
}
.dark .gt-container .gt-comment-admin .gt-comment-content {
  background-color: #1a1a1a;
}
.dark .gt-container .gt-comment-body {
  color: #fff !important;
}
</style>
