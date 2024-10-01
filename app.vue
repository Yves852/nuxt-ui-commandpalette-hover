<template>
  <UContainer class="min-h-screen flex items-center">
    <UCard
      class="flex-1"
      :ui="{
        background: 'bg-gray-50 dark:bg-gray-800/50',
        ring: 'ring-1 ring-gray-300 dark:ring-gray-700',
        divide: 'divide-y divide-gray-300 dark:divide-gray-700',
        header: { base: 'font-bold' },
      }"
    >
      <template #header> Welcome to the playground! </template>

      <UCommandPalette
        v-model="selected"
        :groups="groups"
        :autoselect="false"
      />
      <pre>{{ selected }}</pre>
    </UCard>
  </UContainer>
</template>

<script setup>
const selected = ref({});
const groups = computed(() => [
  {
    key: 'results',
    label: 'Results',
    commands: [],
  },
  {
    key: 'links',
    label: 'Links',
    commands: [
      {
        label: 'Link 1',
        icon: 'i-heroicons-user-group',
        to: '/foo',
      },
      {
        label: 'Link 2',
        icon: 'i-heroicons-clock',
        to: '/bar',
      },
      {
        label: 'Link 3',
        icon: 'i-heroicons-newspaper',
        to: '/baz',
      },
      {
        label: 'Link 4',
        icon: 'i-mdi-car',
        to: '/foo/bar',
      },
    ],
  },
]);
</script>

<style>
body {
  @apply antialiased font-sans text-gray-700 dark:text-gray-200 bg-white dark:bg-gray-900;
}
</style>
