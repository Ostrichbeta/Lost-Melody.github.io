<script lang="ts">
    import Icon from "@iconify/svelte";
    import type { ColorSchema } from "./model/colorSchema";
    import ColorSelector from "./ColorSelector.svelte";

    export var schema: ColorSchema;
</script>

<div class="w-full p-2 gap-2 flex flex-col rounded-md variant-soft">
    <div class="w-full gap-2 flex items-center">
        <Icon icon="mdi:content-save-cog" class="p-2 w-10 h-10" />
        <span class="grow shrink"> 方案名稱代碼 </span>
        <input
            type="text"
            bind:value={schema.schemaName}
            class="w-[30%] p-2 bg-transparent rounded-md hover:variant-ghost"
        />
        <span class="w-6" />
    </div>
    <div class="w-full gap-2 flex items-center">
        <Icon icon="mdi:rename-box" class="p-2 w-10 h-10" />
        <span class="grow shrink"> 方案顯示名稱 </span>
        <input type="text" bind:value={schema.name} class="w-[30%] p-2 bg-transparent rounded-md hover:variant-ghost" />
        <span class="w-6" />
    </div>
    <div class="w-full gap-2 flex items-center">
        <Icon icon="mdi:account-box" class="p-2 w-10 h-10" />
        <span class="grow shrink"> 方案作者信息 </span>
        <input
            type="text"
            bind:value={schema.author}
            class="w-[30%] p-2 bg-transparent rounded-md hover:variant-ghost"
        />
        <span class="w-6" />
    </div>
    <div class="w-full gap-2 flex items-center">
        <Icon icon="mdi:rounded-corner" class="p-2 w-10 h-10" />
        <span class="grow shrink"> 按鍵圓角 </span>
        <input type="range" min="0" max="32" bind:value={schema.corner_radius} class="w-[30%]" />
        <span class="w-6 code"> {schema.corner_radius} </span>
    </div>
    <ColorSelector title="鍵盤背景" bind:color={schema.back_color} />
    <ColorSelector title="按鍵背景" bind:color={schema.button_back_color} />
    <ColorSelector title="按鍵按下背景" bind:color={schema.button_pressed_back_color} />
    <ColorSelector title="按鍵氣泡背景" bind:color={schema.button_bubble_back_color} />
    <ColorSelector title="按鍵文字" bind:color={schema.button_front_color} />
    <ColorSelector title="按鍵按下文字" bind:color={schema.button_pressed_front_color} />
    <ColorSelector title="按鍵劃動文字" bind:color={schema.button_swipe_front_color} />
    <ColorSelector title="按鍵按下劃動文字" bind:color={schema.button_swipe_pressed_front_color} />
    <div class="w-full gap-2 flex items-center">
        <Icon icon="mdi:format-size" class="p-2 w-10 h-10" />
        <span class="grow shrink"> 鍵面字體大小 </span>
        <input type="range" min="0" max="32" bind:value={schema.font_size} class="w-[30%]" />
        <span class="w-6 code"> {schema.font_size} </span>
    </div>
    <div class="w-full gap-2 flex items-center">
        <Icon icon="mdi:format-size" class="p-2 w-10 h-10" />
        <span class="grow shrink"> 劃動字體大小 </span>
        <input type="range" min="0" max="24" bind:value={schema.swipe_font_size} class="w-[30%]" />
        <span class="w-6 code"> {schema.swipe_font_size} </span>
    </div>
    <ColorSelector title="按鍵邊框" bind:color={schema.border_color} />
    <ColorSelector title="按鍵下邊框" bind:color={schema.lower_edge_color} />
    <ColorSelector title="按鍵陰影" bind:color={schema.shadow_color} />
    <div class="w-full gap-2 flex items-center">
        <Icon icon="mdi:format-size" class="p-2 w-10 h-10" />
        <span class="grow shrink"> 按鍵陰影大小 </span>
        <input type="range" min="0" max="8" bind:value={schema.shadow_size} class="w-[30%]" />
        <span class="w-6 code"> {schema.shadow_size} </span>
    </div>
    <ColorSelector title="預編輯區文字" bind:color={schema.text_color} />
    <ColorSelector title="首選文字" bind:color={schema.hilited_candidate_text_color} />
    <ColorSelector title="首選註釋" bind:color={schema.hilited_comment_text_color} />
    <ColorSelector title="首選背景" bind:color={schema.hilited_candidate_back_color} />
    <ColorSelector title="首選序號" bind:color={schema.hilited_candidate_label_color} />
    <ColorSelector title="次選文字" bind:color={schema.candidate_text_color} />
    <ColorSelector title="次選註釋" bind:color={schema.comment_text_color} />
    <ColorSelector title="次選序號" bind:color={schema.label_color} />
    <ColorSelector title="長按首選背景" bind:color={schema.hilited_callout_back_color} />
    <ColorSelector title="長按首選文字" bind:color={schema.hilited_callout_foreground_color} />
</div>
