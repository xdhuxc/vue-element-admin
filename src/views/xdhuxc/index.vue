<template>
  <div>
    <el-form>
      <el-form-item
        v-for="(command, commandIndex) in commands"
        :key="'command' + commandIndex"
      >
        <span>
          <el-input v-model="commands[commandIndex]" :clearable="true" style="width: 199px" />
          <!--<el-input v-model="command.value" :clearable="true" style="width: 199px"></el-input>-->
          <el-button
            v-if="commands.length !== 1"
            type="danger"
            size="mini"
            icon="el-icon-delete"
            circle
            @click.prevent="removeCommand(commandIndex)"
          />
          <el-button
            v-if="commandIndex === commands.length - 1"
            type="primary"
            size="mini"
            icon="el-icon-plus"
            circle
            @click.prevent="addCommand()"
          />
        </span>
      </el-form-item>
    </el-form>
    <el-button @click="onSubmit"> Submit </el-button>
  </div>

</template>

<script>
export default {
  data() {
    return {
      commands: ['']
    }
  },
  mounted() {},
  methods: {
    addCommand() {
      this.commands.push('')
    },
    removeCommand(index) {
      this.commands.splice(index, 1)
    },
    onSubmit() {
      console.log(this.commands)
    }
  }
}
</script>

<style scoped>

</style>
