---
title: "Макросы вспомогательный DDX_DHtml | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- DDX_DHtml
dev_langs:
- C++
helpviewer_keywords:
- macros, exchanging data with HMTL pages
- DDX macros
- HTML pages, helper macros
- DDX (dialog data exchange), DHtml helper macros
- macros, DDX_DHtml helpers
ms.assetid: c46302d2-ea43-4fea-bfc2-6f590d99f267
caps.latest.revision: 14
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: d3c5136b52206a1ec67e1e1fc78ec291a2954faf
ms.lasthandoff: 02/24/2017

---
# <a name="ddxdhtml-helper-macros"></a>DDX_DHtml вспомогательных макросов
Макросы вспомогательный DDX_DHtml обеспечивают простой доступ к часто используемые свойства элементов управления на странице HTML.  
  
### <a name="data-exchange-macros"></a>Макросы данных Exchange  
  
|||  
|-|-|  
|[DDX_DHtml_ElementValue](#ddx_dhtml_elementvalue)|Задает или получает значение свойства выбранного элемента управления.|  
|[DDX_DHtml_ElementInnerText](#ddx_dhtml_elementinnertext)|Задает или получает текст между тегами начала и окончания для текущего элемента.|  
|[DDX_DHtml_ElementInnerHtml](#ddx_dhtml_elementinnerhtml)|Устанавливает или извлекает HTML между открывающий и закрывающий теги текущего элемента.|  
|[DDX_DHtml_Anchor_Href](#ddx_dhtml_anchor_href)|Задает или получает конечная точка URL-адрес или привязки.|  
|[DDX_DHtml_Anchor_Target](#ddx_dhtml_anchor_target)|Задает или получает целевое окно или фрейм.|  
|[DDX_DHtml_Img_Src](#ddx_dhtml_img_src)|Задает или получает имя изображения или видеоклипа в документ.|  
|[DDX_DHtml_Frame_Src](#ddx_dhtml_frame_src)|Задает или получает URL-адрес связанного фрейма.|  
|[DDX_DHtml_IFrame_Src](#ddx_dhtml_iframe_src)|Задает или получает URL-адрес связанного фрейма.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdhtml.h  

## <a name="a-nameddxdhtmlanchorhrefa-ddxdhtmlanchorhref"></a><a name="ddx_dhtml_anchor_href"></a>DDX_DHtml_Anchor_Href
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_HREF с помощью функции отправки идентификатора.

## <a name="a-nameddxdhtmlanchortargeta--ddxdhtmlanchortarget"></a><a name="ddx_dhtml_anchor_target"></a>DDX_DHtml_Anchor_Target
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLANCHORELEMENT_TARGET с помощью функции отправки идентификатора.  

## <a name="a-nameddxdhtmlelementinnerhtmla--ddxdhtmlelementinnerhtml"></a><a name="ddx_dhtml_elementinnerhtml"></a>DDX_DHtml_ElementInnerHtml
 Устанавливает или извлекает HTML между открывающий и закрывающий теги текущего элемента.  
  
  
  
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERHTML с помощью функции отправки идентификатора.  
  

## <a name="a-nameddxdhtmlelementinnertexta--ddxdhtmlelementinnertext"></a><a name="ddx_dhtml_elementinnertext"></a>DDX_DHtml_ElementInnerText
Задает или получает текст между тегами начала и окончания для текущего элемента.  
  
  
  
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLELEMENT_INNERTEXT с помощью функции отправки идентификатора. 

## <a name="a-nameddxdhtmlelementvaluea-ddxdhtmlelementvalue"></a><a name="ddx_dhtml_elementvalue"></a>DDX_DHtml_ElementValue  
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене. В разделе *значение* в [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext).  
  
## <a name="remarks"></a>Примечания  
 Этот макрос выполняется успешно только при запуске на элементы управления, имеющие свойство Value. Элементы управления, имеющие свойство Value включать поля ввода, списки и поля со списком.  
  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_A_VALUE с помощью функции отправки идентификатора.  

## <a name="a-nameddxdhtmlframesrca-ddxdhtmlframesrc"></a><a name="ddx_dhtml_frame_src"></a>DDX_DHtml_Frame_Src
Задает или получает URL-адрес связанного фрейма.  
  
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC с помощью функции отправки идентификатора.  

## <a name="a-nameddxdhtmliframesrca-ddxdhtmliframesrc"></a><a name="ddx_dhtml_iframe_src"></a>DDX_DHtml_IFrame_Src
Задает или получает URL-адрес связанного фрейма.  
  
  
  
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLFRAMEBASE_SRC с помощью функции отправки идентификатора. 

## <a name="a-nameddxdhtmlimgsrcaddxdhtmlimgsrc"></a><a name="ddx_dhtml_img_src"></a>DDX_DHtml_Img_Src
Возвращает или получает имя изображения или видеоклипа в документ.  
  
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
 Значение, указанное для параметра ID HTML-элемент управления.  
  
 `var`  
 Значение при обмене.  
  
## <a name="remarks"></a>Примечания  
 При использовании `DDX_DHtml_Img_Src` макрос, чтобы извлечь свойство src для элемента ИЗОБРАЖЕНИЯ объекта образа Internet Explorer вернет полностью escape-URL-адрес источника изображения. Например, если вы используете `DDX_DHtml_Img_Src` макрос установить свойство src ИЗОБРАЖЕНИЯ элемента в строку «некоторые интересные изображение» при получении этого свойства, Internet Explorer будет возвращать строку «res://d:\myapplication\myapp.exe/some%20interesting%20picture».  
  
 Этот макрос вызывает [CDHtmlDialog::DDX_DHtml_ElementText](../../mfc/reference/cdhtmldialog-class.md#ddx_dhtml_elementtext) DISPID_IHTMLIMGELEMENT_SRC с помощью функции отправки идентификатора.  

  
## <a name="see-also"></a>См. также  
 [Класс CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

