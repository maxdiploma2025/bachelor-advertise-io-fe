<template>
  <el-dialog
    v-model="isOpen.ImageModal"
    width="500"
    :before-close="handleClose"
    class="bg-zink-900 rounded-[12px]"
  >
    <div class="w-full flex flex-col justify-center items-center">
      <img
        :src="`https://xgsaeheapvvspgtxwsaw.supabase.co/storage/v1/object/public/images/${user.id}/${props.imageName}`"
        alt="Uploaded Image"
        class="w-[400px] h-[400px] object-cover rounded-[12px] hover:rounded-t-[12px]"
      >
      <div class="flex w-full justify-center gap-[16px] my-[10px] transition-opacity duration-200">
        <AditionalIcons :imageName="props.imageName" />
      </div>
    </div>
  </el-dialog>
</template>
<script setup lang="ts">
const { isOpen, closeModal } = useModals()
const { user } = useGeneral()

const props = defineProps<{
  imageName: string
}>()

const handleClose = () => {
  closeModal('ImageModal')
}
</script>
