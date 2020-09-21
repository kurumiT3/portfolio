<template>
  <div class="container">
    <div id="name-container">
      <img id="avatar" src="./../assets/images/av.png" alt="avatar" />
      <h1>Kurumit3</h1>
    </div>
    <div class="title-desc-container">
      <a id="github" href="https://github.com/kurumiT3"
        ><img class="title-font" src="./../assets/images/github.svg" />Developer</a
      >
      <span>/</span>
      <a id="sspai" href="https://sspai.com/u/kurumit3/posts"
        ><img class="title-font" src="./../assets/images/sspai.svg" />Writer</a
      >
      <span>/</span>
      <a id="blog" href="https://kurumit3.top/"
        ><img class="title-font" src="./../assets/images/zeit.svg" />Blogger</a
      >
    </div>
    <div class="article">
      <h2>Name</h2>
      <p>
        I go by the name of <i>Spencer Woo</i>. Various other IDs across the net:
        <a href="https://www.instagram.com/nightmare_t3/">@nightmare_t3</a> /
        <a href="https://weibo.com/kurumit3">@逆旅光</a> /
        <a href="https://github.com/kurumiT3">@kurumiT3</a>.
      </p>

      <h2>Academics</h2>
      <ul>
        <li><b>Current:</b> Student at Shanghai Xiangming High School </li>
        <li>
          <b>Future:</b> UNCERTAIN
        </li>
        <li><b>Fields of interest:</b> Coding / Literature </li>
      </ul>

      <h2>Devices</h2>
      <ul>
        <li>Macbook PRO</li>
        <li>final e4000|Sora 碧 Lite</li>
        <li>Redmi Note 7 / A Poor Guy😭</li>
      </ul>

      <h2>Contacts</h2>
      <ul>
        <li>
          <b>Email：</b>
          <a href="mailto:kurumiyout3@gmail.com">kurumiyout3@gmail.com</a><i> (Preferred)</i>
        </li>
        <li><b>Catch me: </b> Shanghai, China</li>
      </ul>
    </div>
  </div>
</template>

<style lang="css" scoped>
#name-container {
	display: flex;
	flex-direction: row;
	justify-content: flex-start;
	align-items: center;
}
#avatar {
  width: 42px;
  height: 42px;
  border-radius: 50%;
  margin-right: 12px;
}
#copyright:hover {
  border: none;
}
.title-font {
  width: 16px;
  height: 16px;
  margin-right: 4px;
}
.title-desc-container {
  display: flex;
  align-items: center;
  justify-content: flex-start;
  margin: 8px 0;
}
.title-desc-container a {
  display: flex;
  align-items: center;
}
.title-desc-container span {
  margin: 0px 4px;
}
.title-desc-container #github {
  color: #24292e;
}
.title-desc-container #sspai {
  color: #ca2c2a;
}
.title-desc-container #blog {
  color: #0070f3;
}
a:hover {
  border-bottom: none;
}
h2 {
  font-size: 20px;
  padding: 16px 0 4px 0;
}
ul {
  padding-left: 15px;
  line-height: 30px;
  margin: 0;
}
p {
  line-height: 30px;
}
</style> 
