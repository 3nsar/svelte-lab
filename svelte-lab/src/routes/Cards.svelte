<script>
    import data from '../data.json'
      import 'font-awesome/css/font-awesome.min.css';
       
</script>

<div class="cards-container">
    {#each data as item}
    <div class="card">
        <i>{item.icon}</i>
        <h2>{item.title}</h2>
        <p>{item.description}</p>
    </div>
  {/each}
</div>



<style lang="scss">
@import '../app.scss';
.card{
    height:270px;
    width: 270px;
    border:2px solid red;
    padding:5px;
    h2{
        color:$primaryWhite;
        font-size: 30px;
    }
    p{
        font-size: 14px;
        
        color: $primaryGray;
    }
}
  
</style>