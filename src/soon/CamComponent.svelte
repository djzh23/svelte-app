<script>
    import {  Button } from 'svelte-materialify';
    let videoSource = null;
    let loading = false;
    const obtenerVideoCamara = async () => {
      try {
        loading = true;
        const stream = await navigator.mediaDevices.getUserMedia({
          video: true,
        });
        videoSource.srcObject = stream;
        videoSource.play();
        loading = false;
      } catch (error) {
        console.log(error);
      }
    };
  </script>
  
  <div class="wrapper">
    {#if loading}
      <h1>CARGANDO</h1>
    {/if}
    <!-- svelte-ignore a11y-media-has-caption -->
    <video bind:this={videoSource}/>
    <div style="text-align: center;">
    <Button  class="grey black-text" on:click={obtenerVideoCamara}><a>OpenCam</a></Button>
    </div>
  </div>


  <style>
      .wrapper{
	  position: fixed;
	  top: 51.1%;
	  left: 50%;
	  transform: translate(-50%, -50%);
	}

  </style>