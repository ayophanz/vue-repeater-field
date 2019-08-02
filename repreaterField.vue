<script>
Vue.component('repeater-input', {
  template: `
            <div>
            <div v-for="(field, key) in fields" style="margin-bottom:4px;" class="input-group input-group">
                  <input type="text" v-model="field.value" class="form-control">
                  <span class="input-group-append">
                    <button type="button" @click="RemoveField(key)" class="btn btn-outline-danger btn-flat"><i class="fas fa-times-circle"></i></button>
                  </span>
                </div>
            <button type="button" @click="AddField" class="btn btn-primary btn-flat"><i class="fas fa-plus-circle"></i> Add</button>
            </div>
            `,
  props: ['dataValue'],          
  data() {
    return {
        fields: Vue.util.extend([{}], this.dataValue)
    }
  },
  methods: {
    AddField() {
      this.$emit('dataFeature', this.fields);
      this.fields.push({ value: '' });
    },
    RemoveField(key) {
      this.fields.splice(key, 1);
    },
    resetField() {
      this.fields = [{}];
    }
  },
  created() {
    this.$on('reset', this.resetField); 
  }
});
</script>
