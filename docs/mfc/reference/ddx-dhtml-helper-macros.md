---
title: Макросы вспомогательный DDX_DHtml | Документы Microsoft
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
ms.openlocfilehash: cb2e9d2494463b502fda85c03fa1b861e1182cfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372079"
---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml вспомогательных макросов
Макросы вспомогательный DDX_DHtml обеспечения быстрого доступа к часто используемые свойства элементов управления в HTML-страницы.  
  
### <a name="data-exchange-macros"></a>Макросы данных Exchange  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Задает или получает значение свойства выбранного элемента управления.|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Задает или получает текст между открывающий и закрывающий теги текущего элемента.|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Задает или получает HTML-код между тегами начала и окончания текущего элемента.|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Задает или получает конечная точка URL-адрес или привязки.|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Задает или получает целевое окно или фрейм.|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Задает или получает имя изображения или видеоклипа в документе.|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Задает или получает URL-адрес связанном с ним кадре.|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Задает или получает URL-адрес связанном с ним кадре.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdhtml.h  

## <a name="ddx_dhtml_anchor_href"></a> DDX_DHtml_Anchor_Href
Задает или получает конечная точка URL-адрес или привязки.  
  
  
  
```  
DDX_DHtml_Anchor_Href(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLANCHORELEMENT_HREF отправки идентификатора.

## <a name="ddx_dhtml_anchor_target"></a>  DDX_DHtml_Anchor_Target
 Задает или получает целевое окно или фрейм.  
    
```  
DDX_DHtml_Anchor_Target(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLANCHORELEMENT_TARGET отправки идентификатора.  

## <a name="ddx_dhtml_elementinnerhtml"></a>  DDX_DHtml_ElementInnerHtml
 Задает или получает HTML-код между тегами начала и окончания текущего элемента.  
  
  
  
```  
DDX_DHtml_ElementInnerHtml(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLELEMENT_INNERHTML отправки идентификатора.  
  

## <a name="ddx_dhtml_elementinnertext"></a>  DDX_DHtml_ElementInnerText
Задает или получает текст между открывающий и закрывающий теги текущего элемента.  
  
  
  
```  
DDX_DHtml_ElementInnerText(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLELEMENT_INNERTEXT отправки идентификатора. 

## <a name="ddx_dhtml_elementvalue"></a> DDX_DHtml_ElementValue  
Задает или получает значение свойства выбранного элемента управления.  
 
```  
DDX_DHtml_ElementValue(
    CDataExchange* dx,  
    LPCTSTR name,
    var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене. В разделе *значение* в [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).  
  
## <a name="remarks"></a>Примечания  
 Этот макрос успешно завершится только при запуске на элементы управления, имеющие значение для свойства. Элементы управления, имеющие значение для свойства включают поля ввода, списки и поля со списком.  
  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_A_VALUE отправки идентификатора.  

## <a name="ddx_dhtml_frame_src"></a> DDX_DHtml_Frame_Src
Задает или получает URL-адрес связанном с ним кадре.  
  
```  
DDX_DHtml_Frame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLFRAMEBASE_SRC отправки идентификатора.  

## <a name="ddx_dhtml_iframe_src"></a> DDX_DHtml_IFrame_Src
Задает или получает URL-адрес связанном с ним кадре.  
  
  
  
```  
DDX_DHtml_IFrame_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLFRAMEBASE_SRC отправки идентификатора. 

## <a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
Возвращает или получает имя изображения или видеоклипа в документе.  
  
```  
DDX_DHtml_Img_Src(
    CDataExchange* dx,  
    LPCTSTR name,  
    CString& var)  
```  
  
#### <a name="parameters"></a>Параметры  
 `dx`  
 Указатель на [CDataExchange](../../mfc/reference/cdataexchange-class.md) объекта.  
  
 `name`  
 Значение, указанное для параметра ID в HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 При использовании `DDX_DHtml_Img_Src` макрос для извлечения свойства src для элемента образ, образ объекта Internet Explorer вернет полностью escape-URL-адрес источника изображения. Например, если вы используете `DDX_DHtml_Img_Src` макрос, чтобы задать свойство src ИЗОБРАЖЕНИЯ элемента к строке «некоторые интересные изображение» при получении этого свойства, возвращает строку «res://d:\myapplication\myapp.exe/some% Internet Explorer 20picture % 20interesting.»  
  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) функцию с помощью DISPID_IHTMLIMGELEMENT_SRC отправки идентификатора.  

  
## <a name="see-also"></a>См. также  
 [Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)
