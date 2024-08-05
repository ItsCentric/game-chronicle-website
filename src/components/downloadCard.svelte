<script lang="ts">
  import * as Card from "$lib/components/ui/card";

  export let viewBox = 24;
</script>

<Card.Root class="flex-1 flex flex-col justify-between">
  <Card.Header>
    <Card.Title class="flex gap-2 items-center"
      ><svg
        role="img"
        height="1.4em"
        width="1.4em"
        fill="currentColor"
        viewBox={`0 0 ${viewBox} ${viewBox}`}
        xmlns="http://www.w3.org/2000/svg"
        ><title>Apple</title><g><slot name="path"></slot></g></svg
      ><slot name="title"></slot></Card.Title
    >
    <Card.Description><slot name="description"></slot></Card.Description>
  </Card.Header>
  <Card.Content>
    <slot name="content"></slot>
  </Card.Content>
</Card.Root>
