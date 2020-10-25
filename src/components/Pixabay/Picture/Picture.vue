<template>
	<div class="Picture">
		<a @click="openModal">
			<img class="image is-128x128 preview-image" v-bind:src="picture.previewURL">
		</a>
		<PictureModal @close="closeModal" @capture="captureContent" v-if="modal">
			<img class="image modal-image" v-bind:src="picture.largeImageURL">
		</PictureModal>
	</div>
</template>

<script>
import html2canvas from "html2canvas";
import PictureModal from '@/components/Pixabay/Picture/PictureModal';
export default {
	name: 'Picture',
	components: {
		PictureModal
	},
	data() {
		return {
			modal: false,
		}
	},
	props: {
		picture: Object
	},
	methods: {
		openModal() {
			this.modal = true
		},
		closeModal() {
			this.modal = false
		},
		captureContent() {
			html2canvas(document.querySelector(".capture"), {
				useCORS: true,
			}).then(canvas => {
				//アンカータグを作成
				var a = document.createElement('a');
				//canvasをJPEG変換し、そのBase64文字列をhrefへセット
				a.href = canvas.toDataURL('image/jpeg', 1);
				//ダウンロード時のファイル名を指定
				a.download = 'download.jpg';
				//クリックイベントを発生させる
				a.click();
			});
		}
	}
}
</script>

<style lang="scss" scoped>
.preview-image {
	object-fit: cover;
}
.modal-image {
	max-width: 600px;
	width: 100%;
	max-height: 600px;
	object-fit: cover;
}

</style>
