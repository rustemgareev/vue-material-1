<script>
export default {
  name: 'mdc-toolbar-section',
  props: {
    tag: {
      type: String,
      required: false,
      default: 'section'
    },
    align: {
      type: String,
      required: false,
      default: '',
      validator: function (value) {
        return ['start', 'end', ''].indexOf(value) >= 0
      }
    }
  },
  render (createElement) {
    let data = {
      class: {
        'mdc-toolbar__section': true,
        'mdc-toolbar__section--align-start': this.align === 'start',
        'mdc-toolbar__section--align-end': this.align === 'end'
      }
    }

    return createElement(this.tag, data, this.$slots.default)
  }
}
</script>
