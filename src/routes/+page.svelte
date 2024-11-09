<script>
  import Avatars from "$lib/components/avatars/avatar.svelte";

  import Table from "$lib/components/table/table.svelte";

  import Dialog from "$lib/components/dialog/dialog.svelte";

  import Card from "$lib/components/cards/card.svelte";

  import Accordion from "$lib/components/accordion/accordion.svelte";
</script>

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
  accordionSkillSource="Blazing Brilliance"
  accordionImageSource="https://i.pinimg.com/736x/9a/97/4f/9a974f42aff13171296fbc5ed59ece40.jpg"
  accordionSkillDescriptionSource="Changli performs up to 4 consecutive attacks, dealing Fusion DMG. After releasing Basic Attack 4, enter True Sight, lasting for 12s."
  accordionToggle={true}
  accordionImageWidth="100%"
  accordionImageHeight="100%"
/>
