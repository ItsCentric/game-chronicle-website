<script lang="ts">
  import * as DropdownMenu from "$lib/components/ui/dropdown-menu";
  import { ChevronDown } from "lucide-svelte";
  import Button from "./ui/button/button.svelte";

  export let optionsMap: Record<string, string>;
  let isOpen = false;
</script>

<DropdownMenu.Root onOpenChange={(newValue) => (isOpen = newValue)}>
  <DropdownMenu.Trigger asChild let:builder>
    <Button builders={[builder]} {...$$restProps}>
      <slot></slot>
      <ChevronDown
        size="1.4em"
        class={`ml-1 transition-transform duration-200 ${isOpen ? "rotate-180" : ""}`}
      />
    </Button>
  </DropdownMenu.Trigger>
  <DropdownMenu.Content>
    {#each Object.entries(optionsMap) as [label, link]}
      <DropdownMenu.Item href={link}>
        {label}
      </DropdownMenu.Item>
    {/each}
  </DropdownMenu.Content>
</DropdownMenu.Root>
