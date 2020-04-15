---
title: Вспомогательные макросы DDX_DHtml
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
ms.openlocfilehash: f78a923a498713867c13ccc88e3e30c1f0a23885
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365869"
---
# <a name="ddx_dhtml-helper-macros"></a>Вспомогательные макросы DDX_DHtml

Макросы DDX_DHtml помощника обеспечивают легкий доступ к широко используемым свойствам элементов управления на странице HTML.

### <a name="data-exchange-macros"></a>Макрос обмена данными

|||
|-|-|
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Устанавливает или извлекает свойство Значения из выбранного элемента управления.|
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Устанавливает или извлекает текст между тегами начала и конца текущего элемента.|
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Устанавливает или извлекает HTML между тегами начала и конца текущего элемента.|
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Устанавливает или получает URL назначения или точку якоря.|
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Устанавливает или извлекает целевое окно или рамку.|
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Устанавливает или получает имя изображения или видеоклипа в документе.|
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Устанавливает или извлекает URL-адрес связанного кадра.|
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Устанавливает или извлекает URL-адрес связанного кадра.|

## <a name="requirements"></a>Требования

**Заголовок:** afxdhtml.h

## <a name="ddx_dhtml_anchor_href"></a><a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href

Устанавливает или получает URL назначения или точку якоря.

```
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_IHTMLANCHORELEMENT_HREF отправки.

## <a name="ddx_dhtml_anchor_target"></a><a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target

Устанавливает или извлекает целевое окно или рамку.

```
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_IHTMLANCHORELEMENT_TARGET отправки.

## <a name="ddx_dhtml_elementinnerhtml"></a><a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml

Устанавливает или извлекает HTML между тегами начала и конца текущего элемента.

```
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_IHTMLELEMENT_INNERHTML отправки.

## <a name="ddx_dhtml_elementinnertext"></a><a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText

Устанавливает или извлекает текст между тегами начала и конца текущего элемента.

```
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_IHTMLELEMENT_INNERTEXT отправки.

## <a name="ddx_dhtml_elementvalue"></a><a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue

Устанавливает или извлекает свойство Значения из выбранного элемента управления.

```
DDX_DHtml_ElementValue(
    CDataExchange* dx,
    LPCTSTR name,
    var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается. Посмотреть *значение* в [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).

## <a name="remarks"></a>Remarks

Этот макрос будет успешным только при запуске элементов управления, которые имеют свойство значения. Элементы управления, которые имеют свойство значения включают в себя отодевные коробки, список ящиков и комбо-боксов.

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_A_VALUE отправки.

## <a name="ddx_dhtml_frame_src"></a><a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src

Устанавливает или извлекает URL-адрес связанного кадра.

```
DDX_DHtml_Frame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_IHTMLFRAMEBASE_SRC отправки.

## <a name="ddx_dhtml_iframe_src"></a><a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src

Устанавливает или извлекает URL-адрес связанного кадра.

```
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается.

## <a name="remarks"></a>Remarks

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_IHTMLFRAMEBASE_SRC отправки.

## <a name="ddx_dhtml_img_src"></a><a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src

Получает или получает имя изображения или видеоклипа в документе.

```
DDX_DHtml_Img_Src(
    CDataExchange* dx,
    LPCTSTR name,
    CString& var)
```

#### <a name="parameters"></a>Параметры

*dx*<br/>
Указатель на объект [CDataExchange.](../../mfc/reference/cdataexchange-class.md)

*name*<br/>
Значение, указанное для параметра Идентификатора HTML-элемента.

*Var*<br/>
Значение обменивается.

## <a name="remarks"></a>Remarks

При использовании DDX_DHtml_Img_Src макроса для получения свойства src для элемента IMAGE объект изображения Internet Explorer вернет полностью сбежавший URL для источника изображения. Например, если вы используете DDX_DHtml_Img_Src макрос, чтобы установить свойство src элемента IMAGE к строке "некоторые интересные изображения", когда вы получите это свойство, Internet Explorer вернет строку "res:/d: myapplication-myapp.exe/some%20interesting%20picture".

Этот макрос вызывает функцию [CDHtmlDialog::DDX-DHtml-ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) с помощью идентификатора DISPID_IHTMLIMGELEMENT_SRC отправки.

## <a name="see-also"></a>См. также раздел

[Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)
