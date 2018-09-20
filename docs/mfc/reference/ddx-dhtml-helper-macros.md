---
title: Вспомогательные макросы DDX_DHtml | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
dev_langs:
- C++
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7a4dbf1b085ca5ffddd87396fc367bf19f2ad02e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383065"
---
# <a name="ddxdhtml-helper-macros"></a>Вспомогательные макросы DDX_DHtml

Вспомогательные макросы DDX_DHtml обеспечивают простой доступ к часто используемые свойства элементов управления на HTML-страницы.

### <a name="data-exchange-macros"></a>Макросы для обмена данными

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Задает или получает значение свойства выбранного элемента управления.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Задает или получает текст между тегами начала и окончания текущего элемента.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Устанавливает или извлекает HTML между открывающий и закрывающий теги текущего элемента.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Задает или получает назначения URL-адрес или точку привязки.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Задает или получает целевое окно или фрейм.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Задает или получает имя изображения или видеоклипа в документ.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Задает или получает URL-адрес связанного кадра.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Задает или получает URL-адрес связанного кадра.|

## <a name="requirements"></a>Требования

**Заголовок:** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href

Задает или получает назначения URL-адрес или точку привязки.



```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене.

## <a name="remarks"></a>Примечания

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLANCHORELEMENT_HREF идентификатор диспетчера.

## <a name="ddx_dhtml_anchor_target"></a>  DDX_DHtml_Anchor_Target

Задает или получает целевое окно или фрейм.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене.

## <a name="remarks"></a>Примечания

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLANCHORELEMENT_TARGET идентификатор диспетчера.

## <a name="ddx_dhtml_elementinnerhtml"></a>  DDX_DHtml_ElementInnerHtml

Устанавливает или извлекает HTML между открывающий и закрывающий теги текущего элемента.



```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене.

## <a name="remarks"></a>Примечания

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLELEMENT_INNERHTML идентификатор диспетчера.


## <a name="ddx_dhtml_elementinnertext"></a>  DDX_DHtml_ElementInnerText

Задает или получает текст между тегами начала и окончания текущего элемента.



```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене.

## <a name="remarks"></a>Примечания

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLELEMENT_INNERTEXT идентификатор диспетчера.

## <a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue

Задает или получает значение свойства выбранного элемента управления.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене. См. в разделе *значение* в [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).

## <a name="remarks"></a>Примечания

Этот макрос выполняется успешно только в том случае, при запуске на элементы управления, имеющие свойство Value. Элементы управления, в которых для свойства значение включают поля ввода, списки и поля со списком.

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_A_VALUE идентификатор диспетчера.

## <a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src

Задает или получает URL-адрес связанного кадра.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене.

## <a name="remarks"></a>Примечания

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLFRAMEBASE_SRC идентификатор диспетчера.

## <a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src

Задает или получает URL-адрес связанного кадра.



```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене.

## <a name="remarks"></a>Примечания

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLFRAMEBASE_SRC идентификатор диспетчера.

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

Возвращает или получает имя изображения или видеоклипа в документ.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.

*name*<br/>
Значение, указанное для параметра ID элемента управления HTML.

*var*<br/>
Значение, при обмене.

## <a name="remarks"></a>Примечания

При использовании макроса DDX_DHtml_Img_Src требуется извлечь свойство src для элемента ИЗОБРАЖЕНИЯ, объект изображения Internet Explorer будет возвращать полностью escape-URL-адрес источника изображения. Например при использовании макроса DDX_DHtml_Img_Src задать свойство src элемент ИЗОБРАЖЕНИЯ к строке «некоторые интересные картины», при извлечении свойства, Internet Explorer возвращает строку «res://d:\myapplication\myapp.exe/some% 20interesting 20picture %.»

Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLIMGELEMENT_SRC идентификатор диспетчера.


## <a name="see-also"></a>См. также

[Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)
