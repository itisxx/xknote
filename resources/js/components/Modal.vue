<template>
  <div
    :class="'modal ' + (size === 'sm' ? 'modal-sm' : '') + (size === 'llg' ? 'modal-lg' : '') + ' xknote-' + size + '-modal' + (data.show ? ' active' : '')"
  >
    <a class="modal-overlay"></a>
    <div :class="'modal-container ' +  data.content">
      <div class="modal-header">
        <div class="modal-title h5">{{ data.title }}</div>
      </div>
      <div class="modal-body">
        <div class="content">
          <slot></slot>
        </div>
      </div>
      <div class="modal-footer">
        <button class="btn btn-primary" @click="data.confirm()">确认</button>
        <button class="btn btn-link" @click="data.cancel()">取消</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "modal",
  props: ["data", "size"]
};
</script>
