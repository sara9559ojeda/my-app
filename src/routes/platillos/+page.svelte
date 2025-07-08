
<script>
    import Card from "../../components/Card.svelte";
    const Cards = [
  {
    CardTitle: "Bandeja Paisa",
    CardText: "Un clásico colombiano con carne molida, chicharrón, frijoles y más.",
    CardImg: "/images/plato1.jpg"
  },
  {
    CardTitle: "Ajiaco Santafereño",
    CardText: "Sopa tradicional de Bogotá con papa criolla, pollo y mazorca.",
    CardImg: "/images/plato2.jpg"
  },
  {
    CardTitle: "Arepa Rellena",
    CardText: "Deliciosa arepa rellena de queso, pollo desmechado o carne.",
    CardImg: "/images/plato3.jpg"
  },
   {
    CardTitle: "Tamales Tolimenses",
    CardText: "Hechos con maíz, carne de cerdo, pollo y envueltos en hoja de plátano.",
    CardImg: "/images/plato7.jpg"
  },
  {
    CardTitle: "Postre de Tres Leches",
    CardText: "Esponjoso pastel bañado en tres tipos de leche, coronado con crema.",
    CardImg: "/images/plato5.jpg"
  },
  {
    CardTitle: "Empanadas",
    CardText: "Crujientes por fuera, rellenas de carne o pollo por dentro.",
    CardImg: "/images/plato6.jpg"
  },
    ];
</script>
<div class="container mt-5">
    <h2 class="mb-4 text-center">Nuestros mejores platos</h2>
    <div class="row g4">
        {#each Cards as C}
            <div class="col-md-4 mb-4">
                <Card 
                    CardTitle={C.CardTitle} 
                    CardText={C.CardText} 
                    CardImg={C.CardImg} 
                    CardLink={C.CardLink}
                />
            </div>
        {/each}
    </div>
</div>