<script>
  import Avatars from "$lib/components/avatars/avatar.svelte";

  import Table from "$lib/components/table/table.svelte";

  import Dialog from "$lib/components/dialog/dialog.svelte";

  import Card from "$lib/components/cards/card.svelte";

  import Accordion from "$lib/components/accordion/accordion.svelte";

  import Carousel from "$lib/components/carousel/carousel.svelte";

  import Resonator from "$lib/components/cards/resonator.svelte";

  import NavigationBar from "$lib/components/navigationBar/navigationBar.svelte";
</script>


<NavigationBar 
  navBarLogoTextSource = "Mari_Gold"
  navBarLogoSource="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
  navBarMenuSource="Dashboard" 
  navBarMenuToggle={true}
  navBarSearchSource = "🔍 What's on your mind?"
  NavBarMenuIconToggle={true}
  NavBarMenuIconSource="https://cdn-icons-png.flaticon.com/512/147/147144.png"
/>

<Avatars
  avatarContent="image"
  avatarContentSource="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSnDZcO8iYBNpfQdlviO9b3KNs8FhXsGG22Fg&s"
  avatarContentBorderRadius="50%"
  statusToggle={true}
  notificationToggle={true}
  onclick={() => alert("Hello")}
/>

<Table
  tableDataSource={[
    { level: 1, atk: 47, critDmg: "10.8%" },
    { level: 20, atk: 122, critDmg: "19.1%" },
    { level: 40, atk: 232, critDmg: "27.5%" },
    { level: 60, atk: 457, critDmg: "47.5%" },
  ]}
/>

<Dialog />

<Card
  cardHeaderSource="Blackshore: To the shore’s end"
  cardImageSource="https://s1.zerochan.net/Frieren.600.4172163.jpg"
  cardContentSource="This is how description of the content looks like. Latest characters, weapons and storyline, bla bla bla.."
/>

<Accordion
  accordionHeaderSource="Header"
  accordionMoreContent="More Content"
  accordionSkillSource="Blazing Brilliance"
  accordionImageSource="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
  accordionSkillDescriptionSource="Changli performs up to 4 consecutive attacks, dealing Fusion DMG. After releasing Basic Attack 4, enter True Sight, lasting for 12s."
  accordionToggle={true}
  accordionImageWidth="100%"
  accordionImageHeight="100%"
/>

<Carousel
  carouselDataSource={[
    "https://steamuserimages-a.akamaihd.net/ugc/2486634816019385799/42EAD597D63146529E43BAE1425E25FA5E39A9D3/?imw=637&imh=358&ima=fit&impolicy=Letterbox&imcolor=%23000000&letterbox=true",
    "https://static.animecorner.me/2024/09/1726468888-2731cfe1c0a510ad6809ed6cb3af3bcd.png",
    "https://i.ytimg.com/vi/A2x5q69sZNw/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDl2AQfF3dzcAR-7L5YqhpGJpQW8w",
  ]}
  carouselDataTextSource=""
  carouselDataHeaderSource=""
  active={0}
  itemLength={2}
/>

<Resonator
  cardTitle="Latest Resonator"
  resonatorStarsRating="★★★★★"
  resonatorStarsSource="5"
  resonatorNameSource="Zhe’zhi"
  resonatorImageSource="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQy9a0SUW3YBu4dEsHm_oiRfYnbFktsmgjpZw&s"
  resonatorElementSource="Glacio"
  resonatorWeaponSource="Rectifier"
  resonatorElementIconSource="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQy9a0SUW3YBu4dEsHm_oiRfYnbFktsmgjpZw&s"
  resonatorWeaponIconSource="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQy9a0SUW3YBu4dEsHm_oiRfYnbFktsmgjpZw&s"
  imageWidth="25rem"
  imageHeight="25rem"
/>
