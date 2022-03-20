<script>
    import { TextField, MaterialApp, Button} from 'svelte-materialify';
</script>

<body>
<div class="wrapper">
    <form id="sign">
        <MaterialApp>
        <TextField id="alias" placeholder="username" outlined>username</TextField>
        <TextField id="pass" type="password" placeholder="passphrase" outlined></TextField>
        <Button id="in" type="submit" value="sign in" size="default" class="green white-text">sign in</Button>
        <Button id="up" type="submit" value="sign up" size="default" class="blue white-text">sign up</Button>
        <Button id="up" type="submit" value="return" size="lar  ge" class="orange white-text">To Menu</Button>
        </MaterialApp>
      </form>
    
      <ul></ul>
    
      <form id="said">
        <MaterialApp>
            <TextField id="say" outlined></TextField>
            <TextField id="speak" type="submit" value="speak" outlined></TextField>
        </MaterialApp>
    
     </form>
</div>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/examples/jquery.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/gun.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/sea.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/gun/lib/webrtc.js"></script>
<script>
    /* replace this line */
    var gun = Gun(['http://localhost:8765/gun', 'https://gun-manhattan.herokuapp.com/gun']);
</script>
</body>


