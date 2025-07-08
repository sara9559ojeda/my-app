<script>
    export let CardTitle;
    export let CardText;
    export let CardImg;
    
</script>

<div class="card h-100">
    <img src={CardImg} class="card-img-top" alt={CardTitle} />
    <div class="card-body d-flex flex-column">
        <h5 class="card-title">{CardTitle}</h5>
        <p class="card-text">{CardText}</p>
        
    </div>
</div>
