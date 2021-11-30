<!--通知组件-->
<template>
	<div class="notice-bar-container">
		<el-card shadow="hover" header="滚动通知栏：默认">
			<NoticeBar
				text="学无止境，无止境学。。。"
			/>
		</el-card>

		<el-card shadow="hover" header="滚动通知栏：设置样式" class="mt15">
			<NoticeBar
				text="学无止境，无止境学。。。"
				leftIcon="iconfont icon-tongzhi2"
				rightIcon="el-icon-arrow-right"
				background="#ecf5ff"
				color="#409eff"
			/>
		</el-card>

		<el-card shadow="hover" header="滚动通知栏：搭配 NoticeBar 和 Carousel 走马灯 组件可以实现垂直滚动的效果" class="mt15">
			<NoticeBar :scrollable="true">
				<el-carousel height="40px" direction="vertical" :autoplay="true" indicator-position="none" :interval="3000">
					<el-carousel-item v-for="v in noticeList" :key="v">{{ v }} </el-carousel-item>
				</el-carousel>
			</NoticeBar>
		</el-card>

		<el-card shadow="hover" header="滚动通知栏：参数" class="mt15">
			<el-table :data="tableData" style="width: 100%">
				<el-table-column prop="a1" label="参数"> </el-table-column>
				<el-table-column prop="a2" label="说明"> </el-table-column>
				<el-table-column prop="a3" label="类型"> </el-table-column>
				<el-table-column prop="a4" label="可选值"> </el-table-column>
				<el-table-column prop="a5" label="默认值"> </el-table-column>
			</el-table>
		</el-card>

		<el-card shadow="hover" header="图标选择器(宽度自动)：事件" class="mt15">
			<el-table :data="tableData1" style="width: 100%">
				<el-table-column prop="a1" label="事件名称"> </el-table-column>
				<el-table-column prop="a2" label="说明"> </el-table-column>
				<el-table-column prop="a3" label="类型"> </el-table-column>
				<el-table-column prop="a4" label="回调参数"> </el-table-column>
			</el-table>
		</el-card>
	</div>
</template>

<script lang="ts">
import { toRefs, reactive, defineComponent } from 'vue';
import NoticeBar from '/@/components/noticeBar/index.vue';
export default defineComponent({
	name: 'funNoticeBar',
	components: { NoticeBar },
	setup() {
		const state = reactive({
			noticeList: [
				'学无止境，无止境学。。。',
				'学无止境，无止境学。。。',
				'学无止境，无止境学。。。',
				'学无止境，无止境学。。。',
			],
			tableData: [
				{
					a1: 'mode',
					a2: '通知栏模式，用于右侧 icon 图标点击',
					a3: 'string',
					a4: 'closeable / link',
					a5: '',
				},
				{
					a1: 'text',
					a2: '通知文本内容，scrollable 为 false 时生效',
					a3: 'string',
					a4: '',
					a5: '',
				},
				{
					a1: 'color',
					a2: '通知文本颜色',
					a3: 'string',
					a4: '',
					a5: '#e6a23c',
				},
				{
					a1: 'background',
					a2: '通知背景色',
					a3: 'string',
					a4: '',
					a5: '#fdf6ec',
				},
				{
					a1: 'size',
					a2: '字体大小，单位px',
					a3: 'number / string',
					a4: '',
					a5: '14',
				},
				{
					a1: 'height',
					a2: '通知栏高度，单位px',
					a3: 'number / string',
					a4: '',
					a5: '40',
				},
				{
					a1: 'delay',
					a2: '动画延迟时间 (s)',
					a3: 'number / string',
					a4: '',
					a5: '1',
				},
				{
					a1: 'speed',
					a2: '滚动速率 (px/s)',
					a3: 'number / string',
					a4: '',
					a5: '100',
				},
				{
					a1: 'scrollable',
					a2: '是否开启垂直滚动',
					a3: 'boolean',
					a4: 'true',
					a5: 'false',
				},
				{
					a1: 'leftIcon',
					a2: '自定义左侧图标',
					a3: 'string',
					a4: '',
					a5: '',
				},
				{
					a1: 'rightIcon',
					a2: '自定义右侧图标',
					a3: 'string',
					a4: '',
					a5: '',
				},
			],
			tableData1: [
				{
					a1: 'close',
					a2: '通知栏模式（mode）closeable 时回调事件',
					a3: 'function',
					a4: '',
				},
				{
					a1: 'link',
					a2: '通知栏模式（mode）link 时回调事件',
					a3: 'function',
					a4: '',
				},
			],
		});
		return {
			...toRefs(state),
		};
	},
});
</script>
