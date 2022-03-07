<script>
    let result = 0;
    let startPage = 0;
    let endPage = 0;
    let days = 0;


    $: result = Math.ceil((endPage-startPage) / days)
</script>


<body> 
    <center> <h1>How many pages today?</h1></center>
    <form class = "inputForm">
            <label for="pages">What is your current page number?</label>
            <input type="number" name="pages" id="pages" class="inputField" bind:value={startPage}>
            
            <label for="target">What is your target page number?</label>
            <input type="number" name="target" id="target" class="inputField" bind:value={endPage}>
            
            <label for="days">How many days do you have left?</label>
            <input type="number" name="days" id="days" class="inputField" bind:value={days}>

                <h1 style="display: {(days !== 0 && endPage !== 0) ? 'block' : 'none'};" class="output">You should read atleast {result} pages per day</h1>
    </form>
</body>

<style>
    :root {
        --accent: #FF4C29;
        --background: #082032;
        --textColor: white;
    }
    body {
        font-family: "monospace";
        overflow: hidden;
        background-color: var(--background);
        color: var(--textColor);
        height: 100%;   
        margin: 0;
        padding: 0;
        width: 100%;
    }
    
    label {
text-overflow: initial;

    }
    .inputForm {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 5px;
        margin: 2px;
    }

    .inputField {
        height: 2rem;
        font-size: 1.5rem;
        max-width: 900px;
        width: 80%;
        text-align: center;
    }

    input:focus, .inputField[type]:focus {
        border-color: var(--accent);
        box-shadow: 0 1px 1px rgba(229, 103, 23, 0.075) inset, 0 0 8px rgba(229, 103, 23, 0.6);
        outline: 0 none;
        transition: all, 100ms;
    }

    .output {
        color: var(--accent);
    }


    /* removing the up and down arrow thing */

    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
    }
    input[type=number] {
    -moz-appearance: textfield;
    }

</style>