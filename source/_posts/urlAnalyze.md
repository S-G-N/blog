---
title: urlAnalyze
date: 2018-05-03 13:53:16
tags:
---
import * as Log from 'modules/dflog'
export default function () {
    Log.logd(window.location.search)
    var ptag = GetQueryString('ptag')
    var uid = GetQueryString('uid')
    Log.logd(ptag)
    var arr = []
    arr = ptag.split('.')
    Log.logd(arr)
    return {
        param: arr, // [rootid,categoryid,mainid,subid]
        ptag: ptag,
        uid: uid
    }
}
function GetQueryString(name) {
    var reg = new RegExp('(^|&)' + name + '=([^&]*)(&|$)', 'i')
    var r = window.location.search.substr(1).match(reg) // 获取url中"?"符后的字符串并正则匹配
    var context = ''
    if (r != null) {
        context = r[2]
    }
    reg = null
    r = null
    return context === null || context === '' || context === 'undefined' ? '' : context
}
