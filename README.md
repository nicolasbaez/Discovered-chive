# Discovered-chive
Sunny days

![buh](https://github.com/nicolasbaez/Discovered-chive/blob/main/xp024.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  rotateX(1);
  clear();
  for (i = 0; i < 4 * PI; i += 0.1) {
    stroke(0, map(i, 0, 12, 255, 0), 255);
    push();
    translate(0, 0, map(sin(w + i), -1, 1, 0, map(i, 0, 4 * PI, 180, 0)));
    r = i * 16;
    for (j = 0; j < 2 * PI; j += 1 / i) {
      point(r * cos(j), r * sin(j));
    }
    pop();
  }
  w -= 0.05;
};
keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp024.gif", 251, { delay: 0, units: "frames" });
  }
};
