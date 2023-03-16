<script>
  let timerDuration = parseInt(window.location.hash.substring(1));

  const startTime = Date.now();

  let remaining = Math.max((startTime + timerDuration) - Date.now(), 0)

  console.log(remaining);

  function update() {
    requestAnimationFrame(() => {
      remaining = Math.max((startTime + timerDuration) - Date.now(), 0);
      
      update()
    })
  }

  update()
</script>

{Math.floor((remaining / 1000) / 60).toString() + ":" + Math.floor((remaining / 1000) % 60).toString().padStart(2, "0")}