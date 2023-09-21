<script>
    function handleKeyPress(e){
        switch(e.key){
            case 'Enter':
                console.log('asdfasdfsdfa')
            break;
            default: 
            break;

        }
    }
    let value = ''
    

</script>
<header>
    <div class="logo"><img src="ghostlogo.png" alt=""><span>It's a Website.</span></div>
    <h1>Digital Collections</h1>
    <div class="utilities">
        <ul class="mini">
            <li><a class="llines" href="/">Help</a></li>
            <li><a class="llines" href="/">Rights & Reproductions</a></li>
<li><a class="llines" href="/">Log In / Sign Up</a></li>
        </ul>
        <span class="search"><input type="text" placeholder="Search the Digital Collections..." bind:value /></span>
    </div>
</header>
<svelte:body on:keypress={(e) => handleKeyPress(e)} />
<style>
    
    header {
        display: flex;
        align-items: center;
    }
    h1 {

        flex: 2;
    }
    .logo span, h1 , .mini a {
        color:  #18b6f6;
        transition: 300ms;
    }
    .logo span {
        filter: blur(1px);
    }
    header:hover h1, header:hover .logo  span {
        filter: blur(0);
    }
    .logo {
        flex-basis: 400px;
    }
    .utilities {
        flex: 1 0 auto;
    }
    .logo {
        transition: 300ms;
        padding: 16px; 
        display: flex;
        justify-content: flex-start;
        align-items: center;
        background-color: #151934cc; 
        backdrop-filter: saturate(3) blur(10px);
        clip-path:polygon(0 0, 59% 0, 100% 100%, 0% 100%); 
    }
    .logo, .logo img {
        height: 60px;
    }
    .logo img {
        margin: 16px; 
    }
    .logo span {
        font-size: 30px;
    }
    .utilities {
        height: 92px;
        padding-inline: 16px;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        align-items: flex-end;
    }
        .search, .mini {
            margin: 0;
            width: 100%;
            display: flex;
            
        justify-content: flex-end;
        align-items: center;
            list-style-type: none;
            font-size: 0.77rem;
            font-family: styrene;
        }
        .mini a {
            text-decoration: none;

        }
        .mini li:nth-child(2) {
            border-inline: 1px solid rgb(var(--fg-color-1));
        }
        .mini li {
           padding-inline: 8px;
        }
        .search input {
            padding: 5px;
            width: min(100%, 350px);
        }
   </style>
