<script>
  import svelteLogo from "./assets/svelte.svg";
  import viteLogo from "/vite.svg";
  import Counter from "./lib/Counter.svelte";

  import ImageCard from "./lib/ImageCard.svelte";
  import sketchjpg from "./assets/sketch.jpg";
  import bookjpg from "./assets/gabrielmarquezbook.jpg";
  import totebag from "./assets/IMG_6385.jpg";

  let cardData = [
    {
      image: sketchjpg,
      description:
        "I carry a sketchbook wherever I go, I also have an art account on instagram! @artezmin",
    },
    {
      image: bookjpg,
      description:
        "Currently reading 100 years of Solitude, but in the original Spanish!",
    },
    {
      image: totebag,
      description:
        "I love design and have been trying to get back into sewing, here's a tote bag I made!",
    },
  ];

  let name = "Yazmin";
  let favoriteNumber = 12;
  let bio =
    "I am a CS student at Arizona State University in Tempe, Arizona. My family is originally from Mexico, so my native language is Spanish! I am interested in Humanities related subjects such as art and history, in combination with a passion for technology.";
  let hobbies = ["Art", "Reading", "Fashion"];
</script>

<main>
  <div class="about-me">
    <h1>About Me</h1>
    <p><em>Hello! I am {name}</em></p>
    <br />
    <p>{bio}</p>

    <h2>My Interests and Hobbies!</h2>
    <div class="hobbies">
      {#each hobbies as hobby}
        <div class="hobby">{hobby}</div>
      {/each}
    </div>

    <div class="card-container">
      {#each cardData as { image, title, description }}
        <ImageCard {image} {title} {description} />
      {/each}
    </div>
  </div>
</main>

<style>
  h1 {
    color: pink;
    font-family: Arial, sans-serif;
  }
  .about-me {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
    text-align: center;
  }
  .hobbies {
    display: flex;
    justify-content: center;
    gap: 15px;
    flex-wrap: wrap;
  }
  .hobby {
    background-color: rgb(219, 102, 160);
    color: white;
    padding: 10px 15px;
    border-radius: 5px;
  }

  .card-container {
    display: flex;
    flex-wrap: row;
  }
</style>
