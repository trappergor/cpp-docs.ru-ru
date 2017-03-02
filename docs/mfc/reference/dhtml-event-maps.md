---
title: "Схемы событий DHTML | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.macros.shared
dev_langs:
- C++
helpviewer_keywords:
- event map macros
- DHTML, event map macros
- macros, DHTML event map
- DHTML events, event map
- DHTML events
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 8be59b52e06241651a2f605ab949efffd0e010d3
ms.lasthandoff: 02/24/2017

---
# <a name="dhtml-event-maps"></a>Схемы событий DHTML
Следующие макросы можно использовать для обработки событий DHTML.  
  
## <a name="dhtml-event-map-macros"></a>Макросы схемы событий DHTML  
 Следующие макросы можно использовать для обработки событий DHTML в [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-производные классы.  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Отмечает начало DHTML-схема событий.|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Отмечает начало DHTML-схема событий.|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Объявляет DHTML-схема событий.|  
|[DHTML_EVENT](#dhtml_event)|Используется для обработки события на уровне документа для одного элемента HTML.|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Используется для обработки события, инициируемые элемента управления ActiveX.|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Используется для обработки события на уровне документа для всех элементов HTML с определенного класса CSS.|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Используется для обработки событий на уровне элемента.|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|Используется для обработки **onafterupdate** событий из элемента HTML.|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|Используется для обработки **onbeforeupdate** событий из элемента HTML.|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|Используется для обработки **onblur** события из элемента HTML.|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|Используется для обработки `onchange` события из элемента HTML.|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|Используется для обработки **onclick** события из элемента HTML.|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|Используется для обработки **ondataavailable** событий из элемента HTML.|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|Используется для обработки **ondatasetchanged** событий из элемента HTML.|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|Используется для обработки **ondatasetcomplete** событий из элемента HTML.|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|Используется для обработки **ondblclick** события из элемента HTML.|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|Используется для обработки **ondragstart** событий из элемента HTML.|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|Используется для обработки **onerrorupdate** событий из элемента HTML.|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|Используется для обработки **onfilterchange** событий из элемента HTML.|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|Используется для обработки **onfocus** события из элемента HTML.|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|Используется для обработки `onhelp` события из элемента HTML.|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|Используется для обработки **onkeydown** события из элемента HTML.|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|Используется для обработки **onkeypress** события из элемента HTML.|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|Используется для обработки **onkeyup** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|Используется для обработки **onmousedown** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|Используется для обработки `onmousemove` события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|Используется для обработки **onmouseout** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|Используется для обработки **onmouseover** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|Используется для обработки **onmouseup** событий из элемента HTML.|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|Используется для обработки **onresize** события из элемента HTML.|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|Используется для обработки **onrowenter** событий из элемента HTML.|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|Используется для обработки **onrowexit** событий из элемента HTML.|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|Используется для обработки **onselectstart** событий из элемента HTML.|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Используется для обработки события на уровне документа для всех элементов с определенным тегом HTML.|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Отмечает конец DHTML-схема событий.|  
  
## <a name="url-event-map-macros"></a>Макросы схемы событий URL-адрес  
 Следующие макросы можно использовать для обработки событий DHTML в [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производные классы.  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Отмечает начало многостраничные схемы событий DHTML и URL-адрес.|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Отмечает начало embedded DHTML-схема событий.|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Отмечает начало сопоставления записи событий URL-адрес.|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Объявляет многостраничные схема событий DHTML и URL-адрес.|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Отмечает конец многостраничные схема событий DHTML и URL-адрес.|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Отмечает конец embedded DHTML-схема событий.|  
|[END_URL_ENTRIES](#end_url_entries)|Отмечает конец карты запись событий URL-адрес.|  
|[URL_EVENT_ENTRY](#url_event_entry)|Сопоставляет ресурса URL-адреса или HTML-страницу в многостраничное диалоговое окно.|  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapa--begindhtmleventmap"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP  
 Отмечает начало DHTML-схема событий при помещении в исходный файл для класса, идентифицируемый `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего DHTML-схема событий. Этот класс должен наследовать прямо или косвенно [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включить [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в соответствии с определением класса.  
  
### <a name="remarks"></a>Примечания  
 Добавьте в класс для предоставления сведений о DHTML-схема событий **CDHtmlDialog** может использоваться для маршрутизации событий, произошедших в HTML-элементов или элементов управления ActiveX в веб-страницы для функции обработчика в классе.  
  
 Место `BEGIN_DHTML_EVENT_MAP` макрос в файл класса реализации (CPP), за которым следует `DHTML_EVENT` макросы для событий классу — обработка (например, `DHTML_EVENT_ONMOUSEOVER` для события наведения мыши). Используйте [END_DHTML_EVENT_MAP](#end_dhtml_event_map) макрос для обозначения конца карты событий. Эти макросы реализовать следующие функции:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namebegindhtmleventmapinlinea--begindhtmleventmapinline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE  
 Отмечает начало DHTML-схема событий в определении класса для `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего DHTML-схема событий. Этот класс должен наследовать прямо или косвенно [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включить [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в соответствии с определением класса.  
  
### <a name="remarks"></a>Примечания  
 Добавьте в класс для предоставления сведений о DHTML-схема событий **CDHtmlDialog** может использоваться для маршрутизации событий, произошедших в HTML-элементов или элементов управления ActiveX в веб-страницы для функции обработчика в классе.  
  
 Место `BEGIN_DHTML_EVENT_MAP` макрос в файл (.h) определение класса, за которым следует `DHTML_EVENT` макросы для событий классу — обработка (например, `DHTML_EVENT_ONMOUSEOVER` для события наведения мыши). Используйте [END_DHTML_EVENT_MAP_INLINE](http://msdn.microsoft.com/library/0cfec092-20ee-49f3-bc38-56d6a5572db2) макрос для обозначения конца карты событий. Эти макросы реализовать следующие функции:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  

  
##  <a name="a-namedeclaredhtmleventmapa--declaredhtmleventmap"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP  
 Объявляет DHTML-схема событий в определении класса.  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Примечания  
 Этот макрос будет использоваться в определении [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-производные классы.  
  
 Используйте [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) или [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) реализовать карты.  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) объявляет следующие функции:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventa--dhtmlevent"></a><a name="dhtml_event"></a>DHTML_EVENT  
 Обрабатывает (на уровне документа) событие, обозначенное `dispid` с HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор DISPID события для обработки.  
  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники событий, или **NULL** для обработки события документа.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventaxcontrola--dhtmleventaxcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL  
 Обрабатывает событие, обозначенное `dispid` создается с помощью элемента управления ActiveX, определяемый `controlName`.  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации событий для обработки.  
  
 `controlName`  
 `LPCWSTR` С HTML-идентификатор элемента управления, запускающий событие.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventclassa--dhtmleventclass"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS  
 Обрабатывает (на уровне документа) событие, обозначенное `dispid` была создана с любой HTML-элемент с классом CSS, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации событий для обработки.  
  
 `elemName`  
 `LPCWSTR` Удерживая класс CSS, HTML-элементов в список источников событий.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventelementa--dhtmleventelement"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT  
 Обрабатывает (на элемент, идентифицируемый `elemName`) событие, обозначенное `dispid`.  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации событий для обработки.  
  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
 Если этот макрос используется для обработки событий, nonbubbling, источник события будет элемент, идентифицируемый `elemName`.  
  
 Если этот макрос используется для обработки события восходящей маршрутизации, элемент определяется `elemName` не может быть источником события (источник может быть любой элемент, включенный в `elemName`).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonafterupdatea--dhtmleventonafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE  
 Обрабатывает (на уровне документа) **onafterupdate** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonbeforeupdatea--dhtmleventonbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE  
 Обрабатывает (на уровне документа) **onbeforeupdate** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonblura--dhtmleventonblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR  
 Обрабатывает (на уровне элемента) **onblur** события. Это событие nonbubbling.  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonchangea--dhtmleventonchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE  
 Обрабатывает (на уровне элемента) `onchange` события. Это событие nonbubbling.  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonclicka--dhtmleventonclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK  
 Обрабатывает (на уровне документа) **onclick** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventondataavailablea--dhtmleventondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE  
 Обрабатывает (на уровне документа) **ondataavailable** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetchangeda--dhtmleventondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED  
 Обрабатывает (на уровне документа) **ondatasetchanged** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventondatasetcompletea--dhtmleventondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE  
 Обрабатывает (на уровне документа) **ondatasetcomplete** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventondblclicka--dhtmleventondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK  
 Обрабатывает (на уровне документа) **ondblclick** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventondragstarta--dhtmleventondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART  
 Обрабатывает (на уровне документа) **ondragstart** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonerrorupdatea--dhtmleventonerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE  
 Обрабатывает (на уровне документа) **onerrorupdate** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfilterchangea--dhtmleventonfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE  
 Обрабатывает (на уровне документа) **onfilterchange** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonfocusa--dhtmleventonfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS  
 Обрабатывает (на уровне элемента) **onfocus** события. Это событие nonbubbling.  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonhelpa--dhtmleventonhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP  
 Обрабатывает (на уровне документа) `onhelp` произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeydowna--dhtmleventonkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN  
 Обрабатывает (на уровне документа) **onkeydown** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeypressa--dhtmleventonkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS  
 Обрабатывает (на уровне документа) **onkeypress** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonkeyupa--dhtmleventonkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP  
 Обрабатывает (на уровне документа) **onkeyup** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousedowna--dhtmleventonmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN  
 Обрабатывает (на уровне документа) **onmousedown** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmousemovea--dhtmleventonmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE  
 Обрабатывает (на уровне документа) `onmousemove` произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseouta--dhtmleventonmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT  
 Обрабатывает (на уровне документа) **onmouseout** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseovera--dhtmleventonmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER  
 Обрабатывает (на уровне документа) **onmouseover** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonmouseupa--dhtmleventonmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP  
 Обрабатывает (на уровне документа) **onmouseup** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonresizea--dhtmleventonresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE  
 Обрабатывает (на уровне элемента) **onresize** события. Это событие nonbubbling.  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowentera--dhtmleventonrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER  
 Обрабатывает (на уровне документа) **onrowenter** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonrowexita--dhtmleventonrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT  
 Обрабатывает (на уровне документа) **onrowexit** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventonselectstarta--dhtmleventonselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART  
 Обрабатывает (на уровне документа) **onselectstart** произошло исключение, элемент HTML, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` С ID элемента HTML, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedhtmleventtaga--dhtmleventtag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG  
 Обрабатывает (на уровне документа) событие, обозначенное `dispid` была создана с любой HTML-элемент с помощью HTML-тега, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации событий для обработки.  
  
 `elemName`  
 HTML-тега HTML-элементов в список источников событий.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Использовать этот макрос, чтобы добавить запись в [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-nameenddhtmleventmapa--enddhtmleventmap"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP  
 Отмечает конец DHTML-схема событий.  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо использовать в сочетании с [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namebegindhtmlurleventmapa--begindhtmlurleventmap"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP  
 Многостраничное диалоговое окно начинается определение сопоставления событий DHTML и URL-адрес.  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Примечания  
 Поместите `BEGIN_DHTML_URL_EVENT_MAP` в файле реализации вашего [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производного класса. Выполните его с [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map) и [URL-адресов,](#begin_url_entries), а затем закройте его с [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Включить [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) макрос в определение класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView&#196;](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namebeginembeddhtmleventmapa--beginembeddhtmleventmap"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP  
 Начинается определение внедренного DHTML-схема событий многостраничное диалоговое окно.  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего карты событий. Этот класс должен наследовать прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Внедренные DHTML-схема событий должно быть внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).  
  
 *mapName*  
 Указывает, что страница, событие которого сопоставления. Это соответствует *mapName* в [URL_EVENT_ENTRY](#url_event_entry) макрос, на самом деле определения ресурса или URL-адрес в формате HTML.  
  
### <a name="remarks"></a>Примечания  
 Поскольку многостраничное диалоговое окно DHTML состоит из нескольких страниц HTML, каждый из которых может создавать события DHTML, схемы embedded событий используются для сопоставления событий с обработчиков на уровне страниц.  
  
 Схемы событий внедренные в карте событий DHTML и URL-адрес состоит из `BEGIN_EMBED_DHTML_EVENT_MAP` макрос, за которым следует [DHTML_EVENT](dhtml-event-maps.md#dhtml_event) макросы и [END_EMBED_DHTML_EVENT_MAP](dhtml-event-maps.md#end_embed_dhtml_event_map) макрос.  
  
 Каждая карта embedded событий требует соответствующего [URL-адрес события](#url_event_entry) для сопоставления *mapName* (указанного в `BEGIN_EMBED_DHTML_EVENT_MAP`) к ресурсу URL-адрес или HTML.  
  
### <a name="example"></a>Пример  
 Пример см. в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namebeginurlentriesa--beginurlentries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES  
 Определение сопоставления URL-адрес записи событий запускается в многостраничное диалоговое окно.  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего URL-адрес карты запись событий. Этот класс должен наследовать прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Схема событий ввода URL-адрес должен быть внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).  
  
### <a name="remarks"></a>Примечания  
 Поскольку многостраничное диалоговое окно DHTML состоит из нескольких страниц HTML, URL-адресов, события используются для сопоставления URL-адреса или HTML-ресурсы с соответствующими [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map). Поместите `URL_EVENT_ENTRY` макросы между `BEGIN_URL_ENTRIES` и [END_URL_ENTRIES](#end_url_entries) макросы.  
  
### <a name="example"></a>Пример  
 Пример см. в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-namedeclaredhtmlurleventmapa--declaredhtmlurleventmap"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP  
 Объявляет схема событий DHTML и URL-адрес в определении класса.  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Примечания  
 Этот макрос будет использоваться в определении [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производные классы.  
  
 Сопоставление событий DHTML и URL-адрес содержит [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map) и [URL-адресов, событие](#begin_url_entries) для сопоставления обработчиков на постраничной основе DHTML-события. Используйте [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) реализовать карты.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-nameenddhtmlurleventmapa--enddhtmlurleventmap"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP  
 Отмечает конец карты событий DHTML и URL-адрес.  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего карты событий. Этот класс должен наследовать прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Это должно соответствовать `className` в соответствующем [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) макрос.  
  
### <a name="example"></a>Пример  
 Пример см. в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-nameendembeddhtmleventmapa--endembeddhtmleventmap"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP  
 Отмечает конец embedded DHTML-схема событий.  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>Пример  
 Пример см. в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-nameendurlentriesa--endurlentries"></a><a name="end_url_entries"></a>END_URL_ENTRIES  
 Отмечает конец карты запись событий URL-адрес.  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>Пример  
 Пример см. в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="a-nameurlevententrya--urlevententry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY  
 Сопоставляет ресурса URL-адреса или HTML-страницу в многостраничное диалоговое окно.  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего URL-адрес карты запись событий. Этот класс должен наследовать прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Схема событий ввода URL-адрес должен быть внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).  
  
 *URL-адрес*  
 Ресурс URL-адреса или HTML-страницы.  
  
 *mapName*  
 Указывает URL-адресом страницы *URL-адрес*. Это соответствует *mapName* в [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) макрос, который сопоставляет события с этой страницы.  
  
### <a name="remarks"></a>Примечания  
 Если страница HTML ресурс, *URL-адрес* должен быть строковым представлением номер идентификатора ресурса (то есть «123», не 123 или ID_HTMLRES1).  
  
 Идентификатор страницы *mapName*, — это произвольный символ, используемый для связи встроенные схемы событий DHTML для схемы запись событий URL-адрес. Она ограничена областью, на схеме событий DHTML и URL-адрес.  
  
### <a name="example"></a>Пример  
 Пример см. в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  

  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
    
## <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)

