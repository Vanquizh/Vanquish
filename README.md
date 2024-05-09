<div class="wrap">
  <div class="line">
    <div class="left">
      <div class="content">
        <span class="spanSlow">HAPPY</span>
      </div>
    </div>
    <div class="right">
      <div class="content">
        <span class="spanSlow">I</span>
      </div>
    </div>
  </div>
  <div class="line">
    <div class="left">
      <div class="content">
        <span class="spanSlow">Mother's</span>
      </div>
    </div>
    <div class="right">
      <div class="content">
        <span class="spanSlow">Love</span>
      </div>
    </div>
  </div>
  <div class="line">
    <div class="left">
      <div class="content">
        <span class="spanFast">Day</span>
      </div>
    </div>
    <div class="right">
      <div class="content">
        <span class="spanFast">You</span>
      </div>
    </div>
  </div>
  <div class="line">
    <div class="left">
      <div class="content">
        <span class="spanSlow">Mommy</span>
      </div>
    </div>
    <div class="right">
      <div class="content">
        <span class="spanSlow">mommy</span>
      </div>
    </div>
  </div>
</div>

* {
  margin: 0;
  padding: 0;
}
body {
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
.line {
  width: 100vw;
  display: flex;
}
.left,
.right {
  width: 50vw;
  overflow: hidden;
  display: inline-block;
}
.left {
  color: pink;
  transform: skew(0deg, -15deg);
}
.right {
  color: black;
  transform: skew(0deg, 15deg);
}
.left .content {
  width: 100vw;
  text-align: center;
}
.right .content {
  width: 100vw;
  text-align: center;
  transform: translate(-50vw);
}
span {
  display: inline-block;
  font-family: "Montserrat", sans-serif;
  font-size: 9vw;
  text-transform: uppercase;
  line-height: 0.8;
  transition: ease-out 0.6s;
}
window.addEventListener("mousemove", handleMouseMove);
window.addEventListener("resize", handleWindowResize);

const spansSlow = document.querySelectorAll(".spanSlow");
const spansFast = document.querySelectorAll(".spanFast");

let width = window.innerWidth;

function handleMouseMove(e) {
  let normalizePosition = e.pageX / (width / 2) - 1;
  let speedSlow = 100 * normalizePosition;
  let speedFast = 200 * normalizePosition;
  spansSlow.forEach((span) => {
    span.style.transform = `translate(${speedSlow}px)`;
  });
  spansFast.forEach((span) => {
    span.style.transform = `translate(${speedFast}px)`;
  });
}

function handleWindowResize() {
  width = window.innerWidth;
}
