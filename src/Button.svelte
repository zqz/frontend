<script>
  export let title;
  export let size = '';
</script>

<div class="button {size}" aria-label={title} on:click>
  <slot></slot>
</div>

<style type="text/scss">
  @import "variables.scss";

  .button {
    text-decoration: none;
    cursor: pointer;
    background-color: $button-color;
    color: white;
    padding: 4px 12px;
    border-radius: $border-radius;
    font-weight: 500;
    line-height: 1;
    height: 22px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.2);
    user-select: none;
    margin-left: 4px;

    &.large {
      padding: 8px 20px;
      height: 32px;
      flex-shrink: 0;
    }

    &:hover {
      background-color: darken($link-normal, $button-hover-darken);
      box-shadow: 0;
    }

    &:active {
      background-color: darken($link-normal, $button-active-darken);
      box-shadow: 0 2px 5px rgba(0,0,0,0.4);
    }

    &.remove {
      padding: 4px 8px;
      background-color: $button-remove-color;

      &:hover {
        background-color: darken($button-remove-color, $button-hover-darken);
      }

      &:active {
        background-color: darken($button-remove-color, $button-active-darken);
      }
    }
  }
</style>
