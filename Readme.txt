CSS代码：
	<style type="text/css">
		/* ---- reset ---- */
		body {
		  margin: 0;
		  font:normal 75% Arial, Helvetica, sans-serif;
		}

		canvas {
		  display: block;
		  vertical-align: bottom;
		}
		/* ---- particles.js container ---- */

		#particles-js {
		  position: absolute;
		  width: 100%;
		  height: 100%;
		  /*background-color: #b61924;*/
		  background-color:#000;
		  background-image: url("./images/1.jpg");
		  background-repeat: no-repeat;
		  background-size: cover;
		  background-position: 50% 50%;
		}
	</style>

如果在服务器环境下，可以将配置信息写在一个json文件内，然后使用XHR去获取：
/* particlesJS.load(@dom-id, @path-json, @callback (optional)); */
particlesJS.load('particles-js', 'js/particles.json', function() {
  console.log('callback - particles.js config loaded');
});

particles.json文件的配置：
// 配置文件中只需要写json就行
particlesJS("particles-js", {
  "particles": {
    "number": {
      "value": 80,
      "density": {
        "enable": true,
        "value_area": 800
      }
    },
    "color": {
      "value": "#ffffff"
    },
    "shape": {
      "type": ["circle", "triangle", "image"],
      "stroke": {
        "width": 1,
        "color": "#000000"
      },
      "polygon": {
        "nb_sides": 5
      },
      "image": {
        "src": "img/github.svg",
        "width": 100,
        "height": 100
      }
    },
    "opacity": {
      "value": 0.5,
      "random": false,
      "anim": {
        "enable": false,
        "speed": 1,
        "opacity_min": 0.1,
        "sync": false
      }
    },
    "size": {
      "value": 3,
      "random": true,
      "anim": {
        "enable": false,
        "speed": 40,
        "size_min": 0.1,
        "sync": false
      }
    },
    "line_linked": {
      "enable": true,
      "distance": 150,
      "color": "#ffffff",
      "opacity": 0.4,
      "width": 1
    },
    "move": {
      "enable": true,
      "speed": 6,
      "direction": "none",
      "random": false,
      "straight": false,
      "out_mode": "out",
      "bounce": false,
      "attract": {
        "enable": false,
        "rotateX": 600,
        "rotateY": 1200
      }
    }
  },
  "interactivity": {
    "detect_on": "canvas",
    "events": {
      "onhover": {
        "enable": true,
        "mode": "grab"
      },
      "onclick": {
        "enable": true,
        "mode": "push"
      },
      "resize": true
    },
    "modes": {
      "grab": {
        "distance": 140,
        "line_linked": {
          "opacity": 1
        }
      },
      "bubble": {
        "distance": 400,
        "size": 40,
        "duration": 2,
        "opacity": 8,
        "speed": 3
      },
      "repulse": {
        "distance": 200,
        "duration": 0.4
      },
      "push": {
        "particles_nb": 4
      },
      "remove": {
        "particles_nb": 2
      }
    }
  },
  "retina_detect": true
});

参数说明：
particles（颗粒）配置：
particles.number.value  （屏幕中点的个数）	number	40
particles.number.density.enable（密度是否启用）	boolean	true / false
particles.number.density.value_area（密度.值区域）	number	800


particles.color.value：点的颜色	：
HEX (string) 
RGB (object) 
HSL (object) 
array selection (HEX) 
random (string)	
例如：
"#b61924" 
{r:182, g:25, b:36} 
{h:356, s:76, l:41} 
["#b61924", "#333333", "999999"] 
"random"

particles.shape.type（点的形状）	string 
array selection	

例如：
"circle" （圆）
"edge" （棱）
"triangle" （三角形）
"polygon" （多边形）
"star" 
"image" 
["circle", "triangle", "image"]

particles.shape.stroke.width（点的宽度）	number	2
particles.shape.stroke.color（点周围的颜色）	HEX (string)	"#222222"
particles.shape.polygon.nb_slides（多边形的边数）	number	5

particles.shape.image.src	path link 
svg / png / gif / jpg	"assets/img/yop.svg" 
"http://mywebsite.com/assets/img/yop.png"

particles.shape.image.width	number 100
particles.shape.image.height number 100

particles.opacity.value（中间点的透明度，0是全透明）	number (0 to 1)	0.75
particles.opacity.random（随机值）	boolean	true / false
particles.opacity.anim.enable（透明度动画开启）	boolean	true / false
particles.opacity.anim.speed（透明动画速度）	number	3
particles.opacity.anim.opacity_min（透明度最小值）	number (0 to 1)	0.25
particles.opacity.anim.sync（是否同步）	boolean	true / false
particles.size.value（点的大小）	number	20
particles.size.random（随机大小）	boolean	true / false
particles.size.anim.enable（开启size的动画模式）	boolean	true / false
particles.size.anim.speed（变化速度，从size的大小到size_min大小变化的速度）	number	3
particles.size.anim.size_min（size最小值）	number	0.25
particles.size.anim.sync（是否同步的变化）	boolean	true / false
particles.line_linked.enable（线是否连接）	boolean	true / false
particles.line_linked.distance（超过这个值，线将会消失）	number	150
particles.line_linked.color（线的颜色）	HEX (string)	#ffffff
particles.line_linked.opacity（线的透明度）	number (0 to 1)	0.5
particles.line_linked.width（线的宽度）	number	1.5
particles.move.enable（是否移动）	boolean	true / false
particles.move.speed（点的移动速度）	number	4
particles.move.direction（移动方向）	string	
"none" 
"top" 
"top-right" 
"right" 
"bottom-right" 
"bottom" 
"bottom-left" 
"left" 
"top-left"

particles.move.random（随机的移动）	boolean	true / false
particles.move.straight（设置true可能会导致线条无法移动）	boolean	true / false
particles.move.out_mode
（out如果点超过了canvas区域，则会消失，如果bounce选择了，则会弹回区域内）	string 
"out" 或者 "bounce"

particles.move.bounce（两个点之间碰撞会弹开）	boolean true / false
particles.move.attract.enable（点与点之间是否相互吸引）	boolean	true / false
particles.move.attract.rotateX	number	3000
particles.move.attract.rotateY	number	1500
interactivity.detect_on（互动，检测是window还是canvas）	string	"canvas", "window"
interactivity.events.onhover.enable（是否检测hover事件）	boolean	true / false
interactivity.events.onhover.mode
grab：鼠标移入后，线条将会连接鼠标
bubble：鼠标移入后，点将会变大
repulse：点和线条将会远离鼠标	string 
array selection	
"grab" 
"bubble" 
"repulse" 
["grab", "bubble"]

interactivity.events.onclick.enable（鼠标点击）	boolean	true / false
interactivity.events.onclick.mode
push：添加点
remove：删除点
bubble：点击鼠标后，点渐渐变大，然后渐渐变小
repulse：点击鼠标后，鼠标周围的点将会弹开	string 
array selection	
"push" 
"remove" 
"bubble" 
"repulse" 
["push", "repulse"]

interactivity.events.resize（当窗口大小改变时，是否重绘）	boolean	true / false
interactivity.events.modes.grab.distance number	100
interactivity.events.modes.grab.line_linked.opacity	number (0 to 1)	0.75
interactivity.events.modes.bubble.distance	number	100
interactivity.events.modes.bubble.size	number	40
interactivity.events.modes.bubble.duration	number 
(second)	0.4
interactivity.events.modes.repulse.distance
事件触发后，远离鼠标的距离	number	200
interactivity.events.modes.repulse.duration
事件触发后，远离鼠标时的时间	number 
(second)	1.2
interactivity.events.modes.push.particles_nb
事件触发后，颗粒增加的数量	number	4
interactivity.events.modes.remove.particles_nb
事件触发后，颗粒删除的数量	number	4
retina_detect（视网膜检测，一般为true）	boolean	true / false