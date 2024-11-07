<script>
  import Avatars from "$lib/components/avatars/avatar.svelte";

  import Table from "$lib/components/table/table.svelte";

  import Banner from "$lib/components/banner/banner.svelte";
</script>

<Avatars
  avatarContent="image"
  avatarContentSource="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSnDZcO8iYBNpfQdlviO9b3KNs8FhXsGG22Fg&s"
  avatarContentBorderRadius="50%"
  statusToggle={true}
  notificationToggle={true}
  onclick={() => alert("Hello")}
/>

<Table level={1} atk={47} critDmg={10.8} />

<Banner />
