<script>
  import SignComponent from './SignComponent.svelte';
     
</script>

  <body>
    <h2 style="text-align: center;">Sign IN-UP</h2>

    <div class="wrapper">
      <SignComponent></SignComponent>
    </div>


    <!-- <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/examples/jquery.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/gun.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/sea.js"></script>
    <script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/lib/webrtc.js"></script> -->
    <script>
        /* replace this line */
        import GUN from "https://cdn.skypack.dev/gun";
        gun = GUN(); 
        const GUN = require('gun/gun');
    </script>
  </body>

  <style>
      .wrapper{
	  position: fixed;
      /* background-color: darkcyan; */
	  top: 50%;
	  left: 50%;
	  transform: translate(-50%, -50%);
	}
  </style>