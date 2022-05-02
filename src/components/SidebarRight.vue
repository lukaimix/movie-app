<template>
    <div class="sidebar">
        <div class="container">
            <h2>Popular movies</h2>
            <div class="items">
                <img class="image" src="https://fr.web.img3.acsta.net/pictures/21/10/29/16/12/4876966.jpg" alt="">
                 <div>
                     <h5>The Witcher</h5>
                     <p>Action Adventure</p>
                     <p>Notes : 5.5</p>
                 </div>   
            </div>
            <div class="items">
                <img class="image" src="https://fr.web.img3.acsta.net/pictures/21/10/29/16/12/4876966.jpg" alt="">
                 <div>
                     <h5>The Witcher</h5>
                     <p>Action Adventure</p>
                     <p>Notes : 5.5</p>
                 </div>   
            </div>
            <div class="items">
                <img class="image" src="https://fr.web.img3.acsta.net/pictures/21/10/29/16/12/4876966.jpg" alt="">
                 <div>
                     <h5>The Witcher</h5>
                     <p>Action Adventure</p>
                     <p>Notes : 5.5</p>
                 </div>   
            </div>
            <button>See more</button>
        </div>
            <div class="container">
            <h2>Wish List</h2>
            <div class="items">
                <img class="image" src="https://fr.web.img3.acsta.net/pictures/21/10/29/16/12/4876966.jpg" alt="">
                 <div>
                     <h5>The Witcher</h5>
                     <p>Action Adventure</p>
                     <p>Notes : 5.5</p>
                 </div>   
            </div>
            <div class="items">
                <img class="image" src="https://fr.web.img3.acsta.net/pictures/21/10/29/16/12/4876966.jpg" alt="">
                 <div>
                     <h5>The Witcher</h5>
                     <p>Action Adventure</p>
                     <p>Notes : 5.5</p>
                 </div>   
            </div>
            <div class="items">
                <img class="image" src="https://fr.web.img3.acsta.net/pictures/21/10/29/16/12/4876966.jpg" alt="">
                 <div>
                     <h5>The Witcher</h5>
                     <p>Action Adventure</p>
                     <p>Notes : 5.5</p>
                 </div>   
            </div>
            <button>See more</button>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.sidebar {
    display: flex;
     width:100%;
     overflow: hidden;
     flex-direction: column;
     min-height: 90vh;
     gap: 0.5rem;
      .container {
         width: 100%;
         display: flex;
         flex-direction: column;
         align-items: center;
         color: #fff;
         h2 {
             margin: 1rem;
         }
         .items{
             display: flex;
             margin: 0.2rem;
             height: 70px;
             img {
                 width: 50px;
                 height: 50px;
                 margin-right: 1.2rem;
             }
         }
        button {
            background-color: #00c39a;
            color: Black;
            padding: 0.5rem;
            width: 20%;
            border-radius: 50px;
        }
      }
}
</style>