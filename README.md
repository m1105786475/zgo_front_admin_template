# zgo_front_admin_template
前端后台模板

## 菜单嵌套示例
修改src/router/routes.ts
```typescript
{
    path: '/menu',
    name: 'menu',
    component: () => import('/@/layout/routerView/parent.vue'),
    redirect: '/menu/menu1',
    meta: {
        title: 'message.router.menu',
        isLink: '',
        isHide: false,
        isKeepAlive: true,
        isAffix: false,
        isIframe: false,
        auth: ['admin', 'test'],
        icon: 'iconfont icon-caidan',
    },
    children: [
        {
            path: '/menu/menu1',
            name: 'menu1',
            component: () => import('/@/layout/routerView/parent.vue'),
            redirect: '/menu/menu1/menu11',
            meta: {
                title: 'message.router.menu1',
                isLink: '',
                isHide: false,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin', 'test'],
                icon: 'iconfont icon-caidan',
            },
            children: [
                {
                    path: '/menu/menu1/menu11',
                    name: 'menu11',
                    component: () => import('/@/views/menu/menu1/menu11/index.vue'),
                    meta: {
                        title: 'message.router.menu11',
                        isLink: '',
                        isHide: false,
                        isKeepAlive: true,
                        isAffix: false,
                        isIframe: false,
                        auth: ['admin', 'test'],
                        icon: 'iconfont icon-caidan',
                    },
                },
                {
                    path: '/menu/menu1/menu12',
                    name: 'menu12',
                    component: () => import('/@/layout/routerView/parent.vue'),
                    redirect: '/menu/menu1/menu12/menu121',
                    meta: {
                        title: 'message.router.menu12',
                        isLink: '',
                        isHide: false,
                        isKeepAlive: true,
                        isAffix: false,
                        isIframe: false,
                        auth: ['admin', 'test'],
                        icon: 'iconfont icon-caidan',
                    },
                    children: [
                        {
                            path: '/menu/menu1/menu12/menu121',
                            name: 'menu121',
                            component: () => import('/@/views/menu/menu1/menu12/menu121/index.vue'),
                            meta: {
                                title: 'message.router.menu121',
                                isLink: '',
                                isHide: false,
                                isKeepAlive: true,
                                isAffix: false,
                                isIframe: false,
                                auth: ['admin', 'test'],
                                icon: 'iconfont icon-caidan',
                            },
                        },
                        {
                            path: '/menu/menu1/menu12/menu122',
                            name: 'menu122',
                            component: () => import('/@/views/menu/menu1/menu12/menu122/index.vue'),
                            meta: {
                                title: 'message.router.menu122',
                                isLink: '',
                                isHide: false,
                                isKeepAlive: true,
                                isAffix: false,
                                isIframe: false,
                                auth: ['admin', 'test'],
                                icon: 'iconfont icon-caidan',
                            },
                        },
                    ],
                },
                {
                    path: '/menu/menu1/menu13',
                    name: 'menu13',
                    component: () => import('/@/views/menu/menu1/menu13/index.vue'),
                    meta: {
                        title: 'message.router.menu13',
                        isLink: '',
                        isHide: false,
                        isKeepAlive: true,
                        isAffix: false,
                        isIframe: false,
                        auth: ['admin', 'test'],
                        icon: 'iconfont icon-caidan',
                    },
                },
            ],
        },
        {
            path: '/menu/menu2',
            name: 'menu2',
            component: () => import('/@/views/menu/menu2/index.vue'),
            meta: {
                title: 'message.router.menu2',
                isLink: '',
                isHide: false,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin', 'test'],
                icon: 'iconfont icon-caidan',
            },
        },
    ],
},
```

## 外链和内嵌iframe
```typescript
{
    path: '/link',
    name: 'layoutLinkView',
    component: () => import('/@/layout/routerView/link.vue'),
    meta: {
        title: 'message.router.layoutLinkView',
        isLink: 'https://element-plus.gitee.io/#/zh-CN/component/installation',
        isHide: false,
        isKeepAlive: false,
        isAffix: false,
        isIframe: false,
        auth: ['admin'],
        icon: 'iconfont icon-caozuo-wailian',
    },
},
{
        path: '/iframes',
        name: 'layoutIfameView',
        component: () => import('/@/layout/routerView/iframes.vue'),
        meta: {
            title: 'message.router.layoutIfameView',
            isLink: 'https://wdd.js.org/jsplumb-chinese-tutorial/#/',
            isHide: false,
            isKeepAlive: false,
            isAffix: true,
            isIframe: true,
            auth: ['admin'],
            icon: 'iconfont icon-neiqianshujuchucun',
        },
},
```

## 路由参数
普通路由传参示例
- src/views/params/common/index.vue
- src/views/params/common/details.vue
- src/views/params/dynamic/index.vue
- src/views/params/dynamic/details.vue

```typescript
{
    path: '/params',
    name: 'paramsIndex',
    component: () => import('/@/layout/routerView/parent.vue'),
    redirect: '/params/common',
    meta: {
        title: 'message.router.paramsIndex',
        isLink: '',
        isHide: false,
        isKeepAlive: true,
        isAffix: false,
        isIframe: false,
        auth: ['admin'],
        icon: 'iconfont icon-zhongduancanshu',
    },
    children: [
        {
            path: '/params/common',
            name: 'paramsCommon',
            component: () => import('/@/views/params/common/index.vue'),
            meta: {
                title: 'message.router.paramsCommon',
                isLink: '',
                isHide: false,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin'],
                icon: 'iconfont icon-putong',
            },
        },
        {
            path: '/params/common/details',
            name: 'paramsCommonDetails',
            component: () => import('/@/views/params/common/details.vue'),
            meta: {
                title: 'message.router.paramsCommonDetails',
                isLink: '',
                isHide: true,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin'],
                icon: 'el-icon-s-order',
            },
        },
        {
            path: '/params/dynamic',
            name: 'paramsDynamic',
            component: () => import('/@/views/params/dynamic/index.vue'),
            meta: {
                title: 'message.router.paramsDynamic',
                isLink: '',
                isHide: false,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin'],
                icon: 'iconfont icon-dongtai',
            },
        },
        {
            path: '/params/dynamic/details/:t/:id',
            name: 'paramsDynamicDetails',
            component: () => import('/@/views/params/dynamic/details.vue'),
            meta: {
                title: 'message.router.paramsDynamicDetails',
                isLink: '',
                isHide: true,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin'],
                icon: 'el-icon-s-order',
            },
        },
    ],
    },
```

## 权限管理
```typescript
{
    path: '/limits',
    name: 'limits',
    component: () => import('/@/layout/routerView/parent.vue'),
    redirect: '/limits/frontEnd',
    meta: {
        title: 'message.router.limits',
        isLink: '',
        isHide: false,
        isKeepAlive: true,
        isAffix: false,
        isIframe: false,
        auth: ['admin', 'test'],
        icon: 'iconfont icon-quanxian',
    },
    children: [
        {
            path: '/limits/frontEnd',
            name: 'limitsFrontEnd',
            component: () => import('/@/layout/routerView/parent.vue'),
            redirect: '/limits/frontEnd/page',
            meta: {
                title: 'message.router.limitsFrontEnd',
                isLink: '',
                isHide: false,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin', 'test'],
            },
            children: [
                {
                    path: '/limits/frontEnd/page',
                    name: 'limitsFrontEndPage',
                    component: () => import('/@/views/limits/frontEnd/page/index.vue'),
                    meta: {
                        title: 'message.router.limitsFrontEndPage',
                        isLink: '',
                        isHide: false,
                        isKeepAlive: true,
                        isAffix: false,
                        isIframe: false,
                        auth: ['admin', 'test'],
                    },
                },
                {
                    path: '/limits/frontEnd/btn',
                    name: 'limitsFrontEndBtn',
                    component: () => import('/@/views/limits/frontEnd/btn/index.vue'),
                    meta: {
                        title: 'message.router.limitsFrontEndBtn',
                        isLink: '',
                        isHide: false,
                        isKeepAlive: true,
                        isAffix: false,
                        isIframe: false,
                        auth: ['admin', 'test'],
                    },
                },
            ],
        },
        {
            path: '/limits/backEnd',
            name: 'limitsBackEnd',
            component: () => import('/@/layout/routerView/parent.vue'),
            meta: {
                title: 'message.router.limitsBackEnd',
                isLink: '',
                isHide: false,
                isKeepAlive: true,
                isAffix: false,
                isIframe: false,
                auth: ['admin', 'test'],
            },
            children: [
                {
                    path: '/limits/backEnd/page',
                    name: 'limitsBackEndEndPage',
                    component: () => import('/@/views/limits/backEnd/page/index.vue'),
                    meta: {
                        title: 'message.router.limitsBackEndEndPage',
                        isLink: '',
                        isHide: false,
                        isKeepAlive: true,
                        isAffix: false,
                        isIframe: false,
                        auth: ['admin', 'test'],
                    },
                },
            ],
        },
    ],
},
```