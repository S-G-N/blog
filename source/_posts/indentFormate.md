---
title: indentFormate
date: 2018-05-03 14:05:52
tags:
---
```bash
let typeEnum = {
    TYPE_STRING: 'string',
    TYPE_INT: 'number',
    TYPE_OBJECT: 'object',
    TYPE_BOOLEAN: 'boolean'
}
export function format(json) {
    var jsonObj = null
    jsonObj = JSON.parse(json)
    return formatJson(jsonObj, 1)
}
function formatJson(jsonObj, tabIndex) {
    var innerhtml = ''
    var idx = 0
    var isArray = jsonObj instanceof Array
    var length = 0

    if (jsonObj != null) {
        length = Object.keys(jsonObj).length
    }
    for (var obj in jsonObj) {
        var isD = idx + 1 !== length
        var preInnerHtml = ''
        if (typeof jsonObj[obj] === 'object') {
            if (isArray) {
                preInnerHtml = getObjectArrayDiv(formatJson(jsonObj[obj], tabIndex + 1), isD)
            } else {
                preInnerHtml = getObjectDiv(obj, formatJson(jsonObj[obj], tabIndex + 1), isD)
            }
        } else {
            if (isArray) {
                preInnerHtml = getArrayDiv(jsonObj[obj], isD)
            } else {
                preInnerHtml = getDiv(obj, jsonObj[obj], isD)
            }
        }
        innerhtml += preInnerHtml
        idx++
    }
    // console.log(getPanel(innerhtml, tabIndex, isArray, length))
    return getPanel(innerhtml, tabIndex, isArray, length)
}
function getDiv(key, value, isD) {
    return '<div>' + getTitleSpan(key) + ':' + getValueSpan(value) + (isD ? ',' : '') + '</div>'
}
function getObjectDiv(key, value, isD) {
    return '<div>' + getTitleSpan(key) + ':' + value + (isD ? ',' : '') + '</div>'
}
function getObjectArrayDiv(value, isD) {
    return '<div>' + value + (isD ? ',' : '') + '</div>'
}
function getArrayDiv(value, isD) {
    return '<div>' + getValueSpan(value) + (isD ? ',' : '') + '</div>'
}
function getTitleSpan(value) {
    return `<span class='key'>${value}</span>`
}
function getValueSpan(value) {
    var type = typeof value
    switch (type) {
    case typeEnum.TYPE_STRING:
        return `<span class='value_string'>${value}</span>`
    case typeEnum.TYPE_INT:
        return `<span class='value_int'>${value}</span>`
    case typeEnum.TYPE_BOOLEAN:
        return `<span class='value_bool'>${value}</span>`
    }
    return 'error'
}
function getPanel(innerHtml, tabIndex, isArray, index) {
    if (isArray) {
        return `<span class=''><i class='panel-suo'>-</i>[</span><div class='tab_${tabIndex}'>${innerHtml}</div><label class='tips'>Array <span class='tips_math'>${index}<span></label><span>]</span>`
    } else {
        return `<span class=''><i class='panel-suo'>-</i>{</span><div class='tab_${tabIndex}'>${innerHtml}</div><label class='tips'></label><span>}</span>`
    }
}
export function getPath(str) {
    var newStr = ''
    if (str[0] >= 'A' && str[0] <= 'Z') {
        return str
    }
    for (var i = 0; i < str.length; i++) {
        if (str[i] >= 'A' && str[i] <= 'Z') {
            newStr = newStr + '/' + str[i].toLowerCase()
        } else {
            newStr += str[i]
        }
    }
    console.log(newStr)
    return newStr
}
```