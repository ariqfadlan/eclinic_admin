<template>
  <div class="row">
    <div class="col-md-12">
      <div class="form-group">
        <input
          v-model="query.search"
          @keypress.enter="onFilter"
          type="text"
          class="form-control"
          placeholder="Cari dokter..."
        />
        <small class="form-text text-muted">
          * Pencarian berdasarkan nomer dokter,
          nama, telepon, nomer poli atau nama poli
        </small>
      </div>
      <div class="form-group">
        <input
          type="checkbox"
          @change="onFilter"
          v-model="query.is_draft"
        >
        <label
          class="form-check-label"
        >
          Draft
        </label>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DoctorFilter',
  data () {
    return {
      query: {
        search: '',
        is_draft: false
      }
    }
  },
  methods: {
    onFilter () {
      this.$emit('onFilter', this.query)
    }
  }
}
</script>
