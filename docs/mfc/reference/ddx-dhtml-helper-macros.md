---
title: DDX_DHtml вспомогательных макросов
ms.date: 11/04/2016
f1_keywords:
- AFXDHTML/DDX_DHtml_ElementValue
- AFXDHTML/DDX_DHtml_ElementInnerText
- AFXDHTML/DDX_DHtml_ElementInnerHtml
- AFXDHTML/DDX_DHtml_Anchor_Href
- AFXDHTML/DDX_DHtml_Anchor_Target
- AFXDHTML/DDX_DHtml_Img_Src
- AFXDHTML/DDX_DHtml_Frame_Src
- AFXDHTML/DDX_DHtml_IFrame_Src
helpviewer_keywords:
- macros [MFC], exchanging data with HMTL pages
- DDX macros [MFC]
- HTML pages [MFC], helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros [MFC], DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
ms.openlocfilehash: 90c80dbc5c8b6788f3afad3cf77d796139fbd946
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866661"
---
# <a name="ddx_dhtml-helper-macros"></a>DDX_DHtml вспомогательных макросов

Вспомогательные макросы DDX_DHtml позволяют легко получать доступ к часто используемым свойствам элементов управления на HTML-странице.

### <a name="data-exchange-macros"></a>Макросы обмена данными

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Задает или получает свойство Value из выбранного элемента управления.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Задает или получает текст между открывающим и закрывающим тегами текущего элемента.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Задает или получает HTML-код между открывающим и закрывающим тегами текущего элемента.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Задает или получает URL-адрес назначения или точку привязки.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Задает или получает целевое окно или фрейм.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Задает или получает имя изображения или видеоклип в документе.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Задает или получает URL-адрес связанного фрейма.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Задает или получает URL-адрес связанного фрейма.|

## <a name="requirements"></a>Требования

**Заголовок:** афксдхтмл. h

## <a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href

Задает или получает URL-адрес назначения или точку привязки.

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_IHTMLANCHORELEMENT_HREF.

## <a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target

Задает или получает целевое окно или фрейм.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_IHTMLANCHORELEMENT_TARGET.

## <a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml

Задает или получает HTML-код между открывающим и закрывающим тегами текущего элемента.

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_IHTMLELEMENT_INNERHTML.

## <a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText

Задает или получает текст между открывающим и закрывающим тегами текущего элемента.

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_IHTMLELEMENT_INNERTEXT.

## <a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue

Задает или получает свойство Value из выбранного элемента управления.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена. См. раздел *value* в [CDHtmlDialog::D DX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).

## <a name="remarks"></a>Remarks

Этот макрос будет выполнен только при выполнении в элементах управления, имеющих свойство Value. Элементы управления, имеющие свойство Value, включают поля редактирования, списки и поля со списком.

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_A_VALUE.

## <a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src

Задает или получает URL-адрес связанного фрейма.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_IHTMLFRAMEBASE_SRC.

## <a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src

Задает или получает URL-адрес связанного фрейма.

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_IHTMLFRAMEBASE_SRC.

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

Возвращает или получает имя изображения или видеоклип в документе.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*DX*<br/>
Указатель на объект [кдатаексчанже](../../mfc/reference/cdataexchange-class.md) .

*name*<br/>
Значение, указанное для параметра идентификатора HTML-элемента управления.

*var*<br/>
Значение для обмена.

## <a name="remarks"></a>Remarks

При использовании макроса DDX_DHtml_Img_Src для получения свойства src для элемента IMAGE объект Image Internet Explorer возвращает полностью экранированный URL-адрес источника изображения. Например, если вы используете макрос DDX_DHtml_Img_Src, чтобы задать для свойства src элемента IMAGE строку "несколько интересных изображений", Internet Explorer вернет строку "Res:» узла//d: \ MyApplication \ MyApp. exe/a %2 0 интересное %2 0 Picture".

Этот макрос вызывает функцию [DX_DHtml_ElementText CDHtmlDialog::D](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) , используя идентификатор диспетчеризации DISPID_IHTMLIMGELEMENT_SRC.

## <a name="see-also"></a>См. также раздел

[Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)
