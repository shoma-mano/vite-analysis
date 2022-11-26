# transFormIndexHtmlについて
ViteDevServerのinterfaceに存在する関数。
createDevHtmlTransformFn(server)で作成される
packages/vite/src/node/server/index.ts↓
https://github.com/vitejs/vite/blob/8148af7b80894d1597333be40b3ef0ec053c7652/packages/vite/src/node/server/index.ts

# createDevHtmlTransformFnの中身
この中でpreHooksとpostHooksを設定してapplyHtmlTransformsに渡される。
おそらくdevHtmlHooksは必ず設定される
https://github.com/vitejs/vite/blob/8148af7b80894d1597333be40b3ef0ec053c7652/packages/vite/src/node/server/middlewares/indexHtml.ts#L42

# adaptHtmlTransformsの中身
この中でhooksを実行してhtmlにしていく
https://github.com/vitejs/vite/blob/8148af7b80894d1597333be40b3ef0ec053c7652/packages/vite/src/node/plugins/html.ts#L937

# devHtmlHooksの中身
この関数のreturnでscriptタグが追加されている
CLIENT_PUBLIC_PATHは@vite/client(https://github.com/vitejs/vite/blob/fc007dfba2e0392bd29f7e6e2663ca910ed18a6b/packages/vite/src/node/constants.ts#L76)
https://github.com/vitejs/vite/blob/752740c499d6144a80acf0c640746052f12c915e/packages/vite/src/node/server/middlewares/indexHtml.ts#L120
