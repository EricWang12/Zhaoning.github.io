<style>
  .me-visual {
    position: relative;
    width: 99%;
    height: 400px;
    margin: 0 auto;
    border: 1px solid #ccc;
    overflow: hidden;
    background: #ffffff;
  }
  .me-visual iframe,
  .me-visual .me-visual__fallback {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    border: none;
    display: block;
  }
  .me-visual .me-visual__fallback {
    object-fit: cover;
  }
  /* When the Luma embed fails, hide it so the photo underneath shows through. */
  .me-visual.is-fallback iframe {
    display: none;
  }
</style>

<div class="me-visual" id="me-visual">
  <img class="me-visual__fallback" src="/assets/images/gallery/fall_road.jpeg" alt="Zhaoning Wang — fall colors in North Michigan" />
  <iframe id="luma-embed" title="luma embed" allowfullscreen src="https://lumalabs.ai/embed/f916d080-3676-4f79-9f36-954074f43b31?mode=sparkles&background=%23ffffff&color=%23000000&showTitle=false&loadBg=true&logoPosition=top-right&infoPosition=top-left&cinematicVideo=undefined&showMenu=false"></iframe>
</div>

<script>
  (function () {
    var box = document.getElementById('me-visual');
    var frame = document.getElementById('luma-embed');
    if (!box || !frame) { return; }
    var loaded = false;
    function showFallback() {
      if (!loaded) { box.classList.add('is-fallback'); }
    }
    frame.addEventListener('load', function () { loaded = true; });
    frame.addEventListener('error', showFallback);
    // A reachable Luma embed fires `load` within a second or two. If the
    // service is blocked, down, or the embed id is bad, it never does — so
    // after 10s we assume failure and reveal the fallback photo.
    window.setTimeout(showFallback, 10000);
  })();
</script>
