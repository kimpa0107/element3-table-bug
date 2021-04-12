<template>
  <el-table :data="items">
    <el-table-column label="name" prop="name"></el-table-column>
    <el-table-column label="child">
      <template v-slot="{ row }">{{ row.child.id }}</template>
    </el-table-column>
  </el-table>
</template>

<script>
import { reactive } from 'vue';
export default {
  setup() {
    const items = reactive([]);

    for (let i = 0; i < 10; i++) {
      const num = i + 1;
      items.push({
        id: num,
        name: `name - ${num}`,
        child: {
          id: num * 10,
        },
      });
    }

    return { items };
  },
};
</script>

<style lang="scss" scoped>
</style>