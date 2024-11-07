<script lang="ts">
  interface avatarInterface {
    // Config
    avatarContent: "image" | "icon" | "initial";
    avatarContentSource: string;

    statusToggle?: boolean;
    status?: "active" | "doNotDistrub" | "away" | "offline";

    notificationToggle?: boolean;
    notification?: string | number;

    // Style
    avatarContentColor?: string;
    avatarContentBorder?: string;
    avatarContentBorderRadius?: string;
    avatarContentTextColor?: string;

    statusColor?: string;

    notificationColor?: string;
    notificationTextColor?: string;

    // Function
    onclick?: () => void | any;
    ondblclick?: () => void | any;
    oncontextmenu?: () => void | any;
    onmouseenter?: () => void | any;
    onmouseleave?: () => void | any;
    onmousedown?: () => void | any;
    onmouseup?: () => void | any;
    onmousemove?: () => void | any;
    onmouseover?: () => void | any;
    onmouseout?: () => void | any;

    onfocus?: () => void | any;
    onblur?: () => void | any;

    ondrag?: () => void | any;
    ondragstart?: () => void | any;
    ondragend?: () => void | any;
    ondragenter?: () => void | any;
    ondragleave?: () => void | any;
    ondragover?: () => void | any;
    ondrop?: () => void | any;
  }

  let {
    //Config
    avatarContent = "initial",
    avatarContentSource = "M",

    statusToggle = false,
    status = "active",

    notificationToggle = false,
    notification = 1,

    // Style
    avatarContentColor = "white",
    avatarContentBorder = "1px solid #d9d9d9",
    avatarContentBorderRadius = "50%",
    avatarContentTextColor = "#1E1E1E",

    statusColor = "#7BE23A",

    notificationColor = "#0D99FF",
    notificationTextColor = "#FFFFFF",

    // Function
    onclick = () => {},
    ondblclick = () => {},
    oncontextmenu = () => {},
    onmouseenter = () => {},
    onmouseleave = () => {},
    onmousedown = () => {},
    onmouseup = () => {},
    onmousemove = () => {},
    onmouseover = () => {},
    onmouseout = () => {},

    onfocus = () => {},
    onblur = () => {},

    ondrag = () => {},
    ondragstart = () => {},
    ondragend = () => {},
    ondragenter = () => {},
    ondragleave = () => {},
    ondragover = () => {},
    ondrop = () => {},
  }: avatarInterface = $props();
</script>

<main>
  <button
    class="avatar"
    {onclick}
    {ondblclick}
    {oncontextmenu}
    {onmouseenter}
    {onmouseleave}
    {onmousedown}
    {onmouseup}
    {onmousemove}
    {onmouseover}
    {onmouseout}
    {onfocus}
    {onblur}
    {ondrag}
    {ondragstart}
    {ondragend}
    {ondragenter}
    {ondragleave}
    {ondragover}
    {ondrop}
  >
    <div class="avatar-content">
      {#if avatarContent === "image"}
        <img
          class="avatar-content-source"
          style="
            border: {avatarContentBorder};
            border-radius: {avatarContentBorderRadius};
            background-color: {avatarContentColor};
            "
          src={avatarContentSource}
          alt={avatarContentSource}
        />
      {:else if avatarContent === "icon"}
        <img
          class="avatar-content-source"
          style="
            border: {avatarContentBorder};
            border-radius: {avatarContentBorderRadius};
            background-color: {avatarContentColor};
            "
          src={avatarContentSource}
          alt={avatarContentSource}
        />
      {:else}
        <div
          class="avatar-content-source"
          style="
            border: {avatarContentBorder};
            border-radius: {avatarContentBorderRadius};
            background-color: {avatarContentColor};
            color: {avatarContentTextColor}
            "
        >
          {avatarContentSource.charAt(0)}
        </div>
      {/if}
    </div>

    {#if statusToggle === true}
      <div
        class="avatar-status"
        style="
          background-color: {statusColor};
          border-radius: {avatarContentBorderRadius};"
      ></div>
    {/if}

    {#if notificationToggle === true}
      <div
        class="avatar-notification"
        style="
          background-color: {notificationColor};
          border-radius: {avatarContentBorderRadius};
          color: {notificationTextColor};   
        "
      >
        {notification}
      </div>
    {/if}
  </button>
</main>

<style>
  main {
    display: block;

    & .avatar {
      background-color: transparent;
      border: none;

      position: relative;

      & .avatar-content-source {
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        padding: 0.7rem;
        width: 5rem;
        aspect-ratio: 1/1;
        box-shadow: 0.125rem 0.25rem 0.375rem rgba(0, 0, 0, 0.2);
        transition:
          transform 0.3s ease,
          box-shadow 0.3s ease;
      }

      & .avatar-content-source:hover {
        transform: translateY(-0.3125rem);
        box-shadow: 0.25rem 0.5rem 0.75rem rgba(0, 0, 0, 0.3);
      }

      & .avatar-status {
        position: absolute;
        z-index: 1;
        width: 1.75rem;
        height: 1.75rem;
        bottom: 0;
        left: 4.5rem;
      }

      & .avatar-notification {
        position: absolute;
        z-index: 2;
        width: 2.75rem;
        height: 2.75rem;
        display: flex;
        align-items: center;
        justify-content: center;
        top: -0.5rem;
        left: 4.5rem;
      }
    }
  }
</style>
