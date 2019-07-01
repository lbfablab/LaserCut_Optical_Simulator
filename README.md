# LaserCut_Optical_Simulator
Optical path and focus simulator through mirros and lens

## blaba

https://www.glowscript.org/#/user/ao/folder/MyPrograms/program/Miroir3


<iframe src="miroir3.html" width="320" height="340"></iframe>
   
   
   
   
<div id="glowscript" class="glowscript">
<meta http-equiv="Content-Type" content="text/html; charset=utf-8">
<link type="text/css" href="https://s3.amazonaws.com/glowscript/css/redmond/2.1/jquery-ui.custom.css" rel="stylesheet" />
<link href="https://fonts.googleapis.com/css?family=Inconsolata" rel="stylesheet" type="text/css" />
<link type="text/css" href="https://s3.amazonaws.com/glowscript/css/ide.css" rel="stylesheet" />
<script type="text/javascript" src="https://s3.amazonaws.com/glowscript/lib/jquery/2.1/jquery.min.js"></script>
<script type="text/javascript" src="https://s3.amazonaws.com/glowscript/lib/jquery/2.1/jquery-ui.custom.min.js"></script>
<script type="text/javascript" src="https://s3.amazonaws.com/glowscript/package/glow.2.8.min.js"></script>
<script type="text/javascript" src="https://s3.amazonaws.com/glowscript/package/RSrun.2.8.min.js"></script>
<script type="text/javascript"><!--//--><![CDATA[//><!--

// START JAVASCRIPT
;(function() {"use strict";

var regeneratorRuntime = typeof srequire === 'function' ? srequire("streamline-runtime/lib/callbacks/regenerator") : Streamline.srequire("streamline-runtime/lib/callbacks/regenerator");

var _streamline = typeof srequire === 'function' ? srequire("streamline-runtime/lib/callbacks/runtime") : Streamline.srequire("streamline-runtime/lib/callbacks/runtime");

var _filename = "unknown";

var main = _streamline.async(regeneratorRuntime.mark(function _$$main$$(_2) {
    var deg2rad, version, box, sphere, simple_sphere, cylinder, pyramid, cone, helix, ellipsoid, ring, arrow, compound, display, vector, print, type, scene, RS_ls, s, L, xaxis, xlbl, yaxis, ylbl, zaxis, r, M1, M1p, RS_unpack, alphaY1, alphaZ1, ray, ur1, rayp, dt, t, __name__, strings;

    return regeneratorRuntime.wrap(function _$$main$$$(_context) {
        while (1) {
            switch (_context.prev = _context.next) {
                case 0:
                    deg2rad = function deg2rad(x) {
                        var RS_ls;
                        "45";
                        return x["/"](180)["*"](pi);
                    };

                    version = RS_list_decorate(["2.8", "glowscript"]);
                    Array.prototype['+'] = function (r) {
                        return this.concat(r);
                    };
                    Array.prototype['*'] = function (r) {
                        return __array_times_number(this, r);
                    };
                    __name__ = '__main__';

                    window.__GSlang = "vpython";
                    box = vp_box;
                    sphere = vp_sphere;
                    simple_sphere = vp_simple_sphere;
                    cylinder = vp_cylinder;
                    pyramid = vp_pyramid;
                    cone = vp_cone;
                    helix = vp_helix;
                    ellipsoid = vp_ellipsoid;
                    ring = vp_ring;
                    arrow = vp_arrow;
                    compound = vp_compound;
                    display = canvas;
                    vector = vec;
                    print = GSprint;
                    type = pytype;
                    scene = canvas();
                    strings = RS_modules.pythonize.strings;


                    strings();
                    "3";
                    s = "<b>Repère<\/b>\n";
                    "4";
                    s = s["+="]("Et transparence\n");
                    "5";
                    s = s["+="]("Here are the <a href='http://www.glowscript.org/docs/GlowScriptDocs/technical.html' target='_blank'>technical details</a> of the depth-peeling algorithm.");
                    "6";
                    scene.title = s;
                    "8";
                    scene.background = color.white;
                    "9";
                    scene.width = 1200;
                    "10";
                    scene.height = 600;
                    "13";
                    L = 50;
                    "14";
                    scene.range = 2["*"](L);
                    "15";
                    scene.forward = vec(1["-u"](), .4["-u"](), .4["-u"]());
                    "16";
                    scene.forward = vec(.3["-u"](), 1, .6["-u"]());
                    "18";
                    scene.up = vec(0, 0, 1);
                    "20";
                    scene.background = vector(.7, .7, .72);
                    "26";
                    scene.caption = "Right button drag or Ctrl-drag to rotate \"camera\" to view scene.\nMiddle button or Alt-drag to drag up or down or scroll wheel to zoom in or out.\n  On a two-button mouse, middle is left + right.\nTouch screen: pinch/extend to zoom, swipe or two-finger rotate.";
                    "30";
                    xaxis = RS_interpolate_kwargs.call(this, cylinder, [RS_desugar_kwargs({ color: vector(1, 0, 0), pos: vector(0, 0, 0), axis: vector(10, 0, 0), radius: .25 })]);
                    "31";
                    xlbl = RS_interpolate_kwargs.call(this, label, [RS_desugar_kwargs({ pos: vector(12, 0, 0), text: "X", color: color.red, opacity: 0, height: 25, box: 1 })]);
                    "33";
                    yaxis = RS_interpolate_kwargs.call(this, cylinder, [RS_desugar_kwargs({ color: color.green, pos: vector(0, 0, 0), axis: vector(0, 10, 0), radius: .25 })]);
                    "34";
                    ylbl = RS_interpolate_kwargs.call(this, label, [RS_desugar_kwargs({ pos: vector(0, 12, 0), text: "Y", color: color.green, opacity: 0, height: 25, box: 1 })]);
                    "36";
                    zaxis = RS_interpolate_kwargs.call(this, cylinder, [RS_desugar_kwargs({ color: color.blue, pos: vector(0, 0, 0), axis: vector(0, 0, 10), radius: .25 })]);
                    "37";
                    xlbl = RS_interpolate_kwargs.call(this, label, [RS_desugar_kwargs({ pos: vector(0, 0, 12), text: "Z", color: color.blue, opacity: 0, height: 25, box: 1 })]);
                    "41";
                    r = RS_interpolate_kwargs.call(this, arrow, [RS_desugar_kwargs({ pos: vector(0, 0, 0), axis: vector(5["-u"](), 10, 5), color: color.white, shaftwidth: .5 })]);
                    "44";
                    ;
                    if (!deg2rad.__argnames__) Object.defineProperties(deg2rad, {
                        __argnames__: { value: ["x"] }
                    });

                    "61";
                    M1 = RS_interpolate_kwargs.call(this, box, [RS_desugar_kwargs({ pos: vec(0, 20, 0), axis: vec(1, 0, 0), up: vec(0, 0, 1), size: vec(1, 4, 4), opacity: .5, color: color.gray(.5) })]);
                    "63";
                    M1p = RS_interpolate_kwargs.call(this, box, [RS_desugar_kwargs({ pos: M1.pos, axis: M1.axis, up: M1.up, size: M1.size, opacity: .5, color: color.green })]);
                    "64";
                    RS_unpack = [10, 20["-u"]()];
                    alphaY1 = RS_unpack[0];
                    alphaZ1 = RS_unpack[1];
                    "65";
                    RS_interpolate_kwargs.call(M1p, M1p.rotate, [RS_desugar_kwargs({ angle: deg2rad(alphaY1), axis: vec(0, 1, 0), origin: M1p.pos })]);
                    "66";
                    RS_interpolate_kwargs.call(M1p, M1p.rotate, [RS_desugar_kwargs({ angle: deg2rad(alphaZ1), axis: vec(0, 0, 1), origin: M1p.pos })]);
                    "70";
                    RS_interpolate_kwargs.call(M1, M1.rotate, [RS_desugar_kwargs({ angle: deg2rad(45["-u"]()), axis: vec(0, 0, 1), origin: M1.pos })]);
                    "71";
                    RS_interpolate_kwargs.call(M1p, M1p.rotate, [RS_desugar_kwargs({ angle: deg2rad(45["-u"]()), axis: vec(0, 0, 1), origin: M1.pos })]);
                    "72";
                    scene.title = scene.title["+="](str(M1.axis)["+"]("\n")["+"](str(M1p.axis)));
                    "79";
                    ray = RS_interpolate_kwargs.call(this, sphere, [RS_desugar_kwargs({ pos: vector(20, 20.5, 0), radius: .25, color: color.red, make_trail: true, trail_radius: .1, pps: 10 })]);
                    "81";
                    ray.init = ray.pos;
                    "82";
                    ray.mass = 1;
                    "83";
                    ur1 = vec(20["-u"](), 0, 0);
                    "84";
                    ray.p = ur1["*"](ray.mass);
                    "86";
                    rayp = RS_interpolate_kwargs.call(this, sphere, [RS_desugar_kwargs({ pos: vector(20, 20.5, 0), radius: .25, color: color.blue, make_trail: true, trail_radius: .1, pps: 10 })]);
                    "88";
                    rayp.init = rayp.pos;
                    "89";
                    rayp.mass = 1;
                    "91";
                    rayp.p = ur1["*"](rayp.mass);
                    "95";
                    dt = .001;
                    "96";
                    t = 0;
                    "97";

                case 110:
                    if (!true) {
                            _context.next = 120;
                            break;
                        }

                    "99";
                    _context.next = 114;
                    return _streamline.await(_filename, 153, null, rate, 1, null, false, [1e3, true]);

                case 114:
                    "101";
                    if (dot(M1.axis, ray.pos["-"](M1.pos))[">"](0)) {
                            "103";
                            ray.pos = ray.pos["+"](ray.p["/"](ray.mass)["*"](dt));
                            "104";
                        } else {
                            "105";
                        }
                    "106";
                    if (dot(M1p.axis, rayp.pos["-"](M1p.pos))[">"](0)) {
                            "107";
                            rayp.pos = rayp.pos["+"](rayp.p["/"](rayp.mass)["*"](dt));
                            "108";
                        } else {
                            "109";
                        }
                    _context.next = 110;
                    break;

                case 120:
                case "end":
                    return _context.stop();
            }
        }
    }, _$$main$$, this);
}), 0, 1);

var RS_modules = {};
RS_modules.pythonize = {};

(function () {
    var strings = function strings() {
        var string_funcs, exclude, name;
        string_funcs = set("capitalize strip lstrip rstrip islower isupper isspace lower upper swapcase center count endswith startswith find rfind index rindex format join ljust rjust partition rpartition replace split rsplit splitlines zfill".split(" "));
        if (!arguments.length) {
                exclude = function () {
                    var s = RS_set();
                    s.jsset.add("split");
                    s.jsset.add("replace");
                    return s;
                }();
            } else if (arguments[0]) {
                exclude = Array.prototype.slice.call(arguments);
            } else {
                exclude = null;
            }
        if (exclude) {
                string_funcs = string_funcs.difference(set(exclude));
            }
        var RS_Iter0 = RS_Iterable(string_funcs);
        for (var RS_Index0 = 0; RS_Index0["<"](RS_Iter0.length); RS_Index0++) {
            name = RS_Iter0[RS_Index0];
            (RS_expr_temp = String.prototype)[typeof name === "number" && name["<"](0) ? RS_expr_temp.length["+"](name) : name] = (RS_expr_temp = RS_str.prototype)[typeof name === "number" && name["<"](0) ? RS_expr_temp.length["+"](name) : name];
        }
    };

    ;

    RS_modules.pythonize.strings = strings;
})();
;
if (!main.__argnames__) Object.defineProperties(main, {
    __argnames__: { value: ["_"] }
});
;$(function(){ window.__context = { glowscript_container: $("#glowscript").removeAttr("id") }; main(function(err) {;}) })})()
// END JAVASCRIPT

//--><!]]></script>
</div>
