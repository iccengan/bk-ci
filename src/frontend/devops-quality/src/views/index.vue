<template>
    <div class="biz-container quality-level-wrapper">
        <div class="biz-side-bar">
            <side-bar
                :nav="sideMenuNav"
                :side-menu-list="sideMenuList"
                :sub-system-name="'qualityLevel'">
            </side-bar>
        </div>
        <router-view style="width: 100%"></router-view>
    </div>
</template>

<script>
    import sideBar from '@/components/devops/side-nav'

    export default {
        components: {
            'side-bar': sideBar
        },
        data () {
            return {
                sideMenuNav: {
                    icon: 'quality',
                    title: '质量红线',
                    url: ''
                },
                sideMenuList: [
                    {
                        list: [
                            {
                                id: 'qualityOverview',
                                name: '总览',
                                icon: 'icon-overview',
                                showChildren: false
                            },
                            {
                                id: 'ruleList',
                                name: '红线规则',
                                icon: 'icon-rule',
                                showChildren: false,
                                children: [
                                    {
                                        id: 'createRule',
                                        name: '创建红线规则',
                                        icon: 'icon-rule'
                                    },
                                    {
                                        id: 'editRule',
                                        name: '编辑规则',
                                        icon: 'icon-rule'
                                    }
                                ]
                            },
                            {
                                id: 'interceptHistory',
                                name: '红线记录',
                                icon: 'icon-intercept-history',
                                showChildren: false
                            },
                            {
                                id: 'metadataList',
                                name: '指标列表',
                                icon: 'icon-rule',
                                showChildren: false,
                                children: [
                                    {
                                        id: 'createMeta',
                                        name: '创建脚本任务指标',
                                        icon: 'icon-rule'
                                    },
                                    {
                                        id: 'editMeta',
                                        name: '编辑脚本任务指标',
                                        icon: 'icon-rule'
                                    }
                                ]
                            },
                            {
                                id: 'noticeGroup',
                                name: '通知组',
                                icon: 'icon-notification',
                                showChildren: false
                            }
                        ]
                    }
                ]
            }
        }
    }
</script>

<style lang="scss">
    @import '@/scss/conf.scss';

    .quality-level-wrapper {
        min-width: 1200px;
        height: 100%;
    }
    .sub-view-port {
        height: calc(100% - 60px);
        overflow: auto;
    }
</style>
