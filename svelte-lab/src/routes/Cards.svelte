<script>
    import data from '../data.json'
      
       
</script>
<div class="container">
    <div class="cards-container">
        {#each data as item}
        <div class="card">
        <span class={item.icon}></span>
            <h2>{item.title}</h2>
            <p>{item.description}</p>
        </div>
    {/each}
    </div>
</div>



<style lang="scss">
@import '../app.scss';
.cards-container{
    display: grid;
    justify-content: center;
    gap: 30px;
    width: 100%;
    grid-template-columns: repeat(3,300px);
    
}
.card{
    margin: 10px;
    height:300px;
    width: 300px;
    border:none;
    background-color: $primaryLightBlack;
    padding:25px;
    h2{
        color:$primaryWhite;
        font-size: 30px;
    }
    p{
        font-size: 14px;
        margin-top: 20px;
        color: $primaryGray;
    }
    span{
        font-size: 30px;
         color: $primaryBlue;
           margin-bottom: 10px;

    }
}
  
</style>