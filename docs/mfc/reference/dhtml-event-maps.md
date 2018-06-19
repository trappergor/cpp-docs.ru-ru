---
title: Схемы событий DHTML | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.macros.shared
dev_langs:
- C++
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 224a0c9b837763574c53e8464885f02ec5413971
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33377444"
---
# <a name="dhtml-event-maps"></a>Схемы событий DHTML
Следующие макросы можно использовать для обработки событий DHTML.  
  
## <a name="dhtml-event-map-macros"></a>Макросы схемы событий DHTML  
 Следующие макросы можно использовать для обработки событий DHTML в [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-производные классы.  
  
|||  
|-|-|  
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Отмечает начало карты событий DHTML.|  
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Отмечает начало карты событий DHTML.|  
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Объявляет DHTML-схема событий.|  
|[DHTML_EVENT](#dhtml_event)|Используется для обработки события на уровне документа для единичного элемента HTML.|  
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Используется, чтобы обрабатывать событие, инициированное элемента управления ActiveX.|  
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Используется для обработки события на уровне документа для всех элементов HTML с определенного класса CSS.|  
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Используется для обработки события на уровне элемента.|  
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|Используется для обработки **onafterupdate** события из элемента HTML.|  
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|Используется для обработки **onbeforeupdate** события из элемента HTML.|  
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|Используется для обработки **onblur** события из элемента HTML.|  
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|Используется для обработки `onchange` события из элемента HTML.|  
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|Используется для обработки **onclick** события из элемента HTML.|  
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|Используется для обработки **ondataavailable** события из элемента HTML.|  
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|Используется для обработки **ondatasetchanged** события из элемента HTML.|  
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|Используется для обработки **ondatasetcomplete** события из элемента HTML.|  
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|Используется для обработки **ondblclick** события из элемента HTML.|  
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|Используется для обработки **ondragstart** события из элемента HTML.|  
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|Используется для обработки **onerrorupdate** события из элемента HTML.|  
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|Используется для обработки **onfilterchange** события из элемента HTML.|  
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|Используется для обработки **onfocus** события из элемента HTML.|  
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|Используется для обработки `onhelp` события из элемента HTML.|  
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|Используется для обработки **onkeydown** события из элемента HTML.|  
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|Используется для обработки **onkeypress** события из элемента HTML.|  
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|Используется для обработки **onkeyup** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|Используется для обработки **onmousedown** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|Используется для обработки `onmousemove` события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|Используется для обработки **onmouseout** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|Используется для обработки **onmouseover** события из элемента HTML.|  
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|Используется для обработки **onmouseup** события из элемента HTML.|  
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|Используется для обработки **onresize** события из элемента HTML.|  
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|Используется для обработки **onrowenter** события из элемента HTML.|  
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|Используется для обработки **onrowexit** события из элемента HTML.|  
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|Используется для обработки **onselectstart** события из элемента HTML.|  
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Используется для обработки события на уровне документа для всех элементов с определенным тегом HTML.|  
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Отмечает конец DHTML-схема событий.|  
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|Отмечает конец DHTML-схема событий. |
  
## <a name="url-event-map-macros"></a>Макросы схемы событий URL-адрес  
 Следующие макросы можно использовать для обработки событий DHTML в [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производные классы.  
  
|||  
|-|-|  
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Отмечает начало многостраничные схема событий DHTML и URL-адрес.|  
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Отмечает начало внедренные карта событий DHTML.|  
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Отмечает начало карты запись событий URL-адрес.|  
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Объявляет многостраничные схема событий DHTML и URL-адрес.|  
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Отмечает конец многостраничные схема событий DHTML и URL-адрес.|  
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Отмечает конец внедренного карта событий DHTML.|  
|[END_URL_ENTRIES](#end_url_entries)|Отмечает конец карты запись событий URL-адрес.|  
|[URL_EVENT_ENTRY](#url_event_entry)|Сопоставляет ресурс URL-адрес или HTML-страницу в многостраничное диалоговое окно.|  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map"></a>  BEGIN_DHTML_EVENT_MAP  
 Отмечает начало карты событий DHTML при помещении в исходном файле для класса, обозначенную `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего DHTML-схема событий. Этот класс должен наследоваться от прямо или косвенно [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включать [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в соответствии с определением класса.  
  
### <a name="remarks"></a>Примечания  
 Добавьте в класс для предоставления сведений о DHTML-схема событий **CDHtmlDialog** может использоваться на маршруте события, создаваемые элементы HTML или элементы управления ActiveX в веб-страницы для функции обработчика в классе.  
  
 Место `BEGIN_DHTML_EVENT_MAP` макрос в файле реализации (CPP) класса, за которым следует `DHTML_EVENT` макросы для событий класса состоит в обработке (например, `DHTML_EVENT_ONMOUSEOVER` для события наведения мыши). Используйте [END_DHTML_EVENT_MAP](#end_dhtml_event_map) макрос для обозначения конца схема событий. Эти макросы реализовывать следующие функции:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="begin_dhtml_event_map_inline"></a>  BEGIN_DHTML_EVENT_MAP_INLINE  
 Отмечает начало карты событий DHTML в определении класса для `className`.  
  
```   
BEGIN_DHTML_EVENT_MAP_INLINE(className)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего DHTML-схема событий. Этот класс должен наследоваться от прямо или косвенно [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включать [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в соответствии с определением класса.  
  
### <a name="remarks"></a>Примечания  
 Добавьте в класс для предоставления сведений о DHTML-схема событий **CDHtmlDialog** может использоваться на маршруте события, создаваемые элементы HTML или элементы управления ActiveX в веб-страницы для функции обработчика в классе.  
  
 Место `BEGIN_DHTML_EVENT_MAP` макрос в файл (.h) определение класса, за которым следует `DHTML_EVENT` макросы для событий класса состоит в обработке (например, `DHTML_EVENT_ONMOUSEOVER` для события наведения мыши). Используйте [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) макрос для обозначения конца схема событий. Эти макросы реализовывать следующие функции:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  

  
##  <a name="declare_dhtml_event_map"></a>  DECLARE_DHTML_EVENT_MAP  
 Объявляет событие DHTML карты в определении класса.  
  
```   
DECLARE_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Примечания  
 Этот макрос будет использоваться в определении [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-производные классы.  
  
 Используйте [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) или [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) реализовать схему.  
  
 [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) объявляет следующую функцию:  
  
 `virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event"></a>  DHTML_EVENT  
 Обрабатывает (на уровне документа), событие, обозначенное `dispid` с HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 DISPID обрабатываемого события.  
  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники событий, или **NULL** обрабатывать события документа.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_axcontrol"></a>  DHTML_EVENT_AXCONTROL  
 Обрабатывает событие, обозначенное `dispid` , инициированные с помощью элемента управления ActiveX, определяемый `controlName`.  
  
```   
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)  
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации обрабатываемого события.  
  
 `controlName`  
 `LPCWSTR` Удерживая HTML-идентификатор элемента управления, запускающий событие.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_class"></a>  DHTML_EVENT_CLASS  
 Обрабатывает (на уровне документа), событие, обозначенное `dispid` была создана с любой HTML-элемент с помощью класса CSS, определяемый `elemName`.  
  
```   
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации обрабатываемого события.  
  
 `elemName`  
 `LPCWSTR` Удерживая класс CSS, HTML-элементов, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_element"></a>  DHTML_EVENT_ELEMENT  
 Обрабатывает (на элемент, идентифицируемый `elemName`) событие, обозначенное `dispid`.  
  
```   
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn) 
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации обрабатываемого события.  
  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
 Этот макрос используется для обработки событий nonbubbling, источник события будет ли элемент, идентифицируемый `elemName`.  
  
 Если этот макрос используется для обработки событий восходящей, определяется элемент `elemName` не может быть источником события (источник может быть любой элемент, содержащиеся в `elemName`).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onafterupdate"></a>  DHTML_EVENT_ONAFTERUPDATE  
 Обрабатывает (на уровне документа) **onafterupdate** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onbeforeupdate"></a>  DHTML_EVENT_ONBEFOREUPDATE  
 Обрабатывает (на уровне документа) **onbeforeupdate** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onblur"></a>  DHTML_EVENT_ONBLUR  
 Обрабатывает (на уровне элемента) **onblur** событий. Это событие nonbubbling.  
  
```   
DHTML_EVENT_ONBLUR(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onchange"></a>  DHTML_EVENT_ONCHANGE  
 Обрабатывает (на уровне элемента) `onchange` событий. Это событие nonbubbling.  
  
```   
DHTML_EVENT_ONCHANGE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onclick"></a>  DHTML_EVENT_ONCLICK  
 Обрабатывает (на уровне документа) **onclick** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_ondataavailable"></a>  DHTML_EVENT_ONDATAAVAILABLE  
 Обрабатывает (на уровне документа) **ondataavailable** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetchanged"></a>  DHTML_EVENT_ONDATASETCHANGED  
 Обрабатывает (на уровне документа) **ondatasetchanged** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_ondatasetcomplete"></a>  DHTML_EVENT_ONDATASETCOMPLETE  
 Обрабатывает (на уровне документа) **ondatasetcomplete** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn) 
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_ondblclick"></a>  DHTML_EVENT_ONDBLCLICK  
 Обрабатывает (на уровне документа) **ondblclick** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_ondragstart"></a>  DHTML_EVENT_ONDRAGSTART  
 Обрабатывает (на уровне документа) **ondragstart** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onerrorupdate"></a>  DHTML_EVENT_ONERRORUPDATE  
 Обрабатывает (на уровне документа) **onerrorupdate** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```   
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onfilterchange"></a>  DHTML_EVENT_ONFILTERCHANGE  
 Обрабатывает (на уровне документа) **onfilterchange** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onfocus"></a>  DHTML_EVENT_ONFOCUS  
 Обрабатывает (на уровне элемента) **onfocus** событий. Это событие nonbubbling.  
  
```  
 
DHTML_EVENT_ONFOCUS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onhelp"></a>  DHTML_EVENT_ONHELP  
 Обрабатывает (на уровне документа) `onhelp` возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONHELP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onkeydown"></a>  DHTML_EVENT_ONKEYDOWN  
 Обрабатывает (на уровне документа) **onkeydown** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onkeypress"></a>  DHTML_EVENT_ONKEYPRESS  
 Обрабатывает (на уровне документа) **onkeypress** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onkeyup"></a>  DHTML_EVENT_ONKEYUP  
 Обрабатывает (на уровне документа) **onkeyup** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONKEYUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onmousedown"></a>  DHTML_EVENT_ONMOUSEDOWN  
 Обрабатывает (на уровне документа) **onmousedown** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onmousemove"></a>  DHTML_EVENT_ONMOUSEMOVE  
 Обрабатывает (на уровне документа) `onmousemove` возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseout"></a>  DHTML_EVENT_ONMOUSEOUT  
 Обрабатывает (на уровне документа) **onmouseout** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseover"></a>  DHTML_EVENT_ONMOUSEOVER  
 Обрабатывает (на уровне документа) **onmouseover** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onmouseup"></a>  DHTML_EVENT_ONMOUSEUP  
 Обрабатывает (на уровне документа) **onmouseup** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onresize"></a>  DHTML_EVENT_ONRESIZE  
 Обрабатывает (на уровне элемента) **onresize** событий. Это событие nonbubbling.  
  
```  
 
DHTML_EVENT_ONRESIZE(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onrowenter"></a>  DHTML_EVENT_ONROWENTER  
 Обрабатывает (на уровне документа) **onrowenter** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONROWENTER(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onrowexit"></a>  DHTML_EVENT_ONROWEXIT  
 Обрабатывает (на уровне документа) **onrowexit** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_onselectstart"></a>  DHTML_EVENT_ONSELECTSTART  
 Обрабатывает (на уровне документа) **onselectstart** возникло событие HTML-элемент, идентифицируемый `elemName`.  
  
```  
 
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `elemName`  
 `LPCWSTR` Удерживая идентификатор HTML-элемента, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="dhtml_event_tag"></a>  DHTML_EVENT_TAG  
 Обрабатывает (на уровне документа), событие, обозначенное `dispid` была создана с любой HTML-элемент с HTML-тегом, обозначенную `elemName`.  
  
```   
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)   
```  
  
### <a name="parameters"></a>Параметры  
 `dispid`  
 Идентификатор диспетчеризации обрабатываемого события.  
  
 `elemName`  
 HTML-тега HTML-элементов, источники события.  
  
 `memberFxn`  
 Функция обработчика для события.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот макрос для добавления записи для [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="end_dhtml_event_map"></a>  END_DHTML_EVENT_MAP  
 Отмечает конец DHTML-схема событий.  
  
```   
END_DHTML_EVENT_MAP()   
```  
  
### <a name="remarks"></a>Примечания  
 Необходимо использовать в сочетании с [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="begin_dhtml_url_event_map"></a>  BEGIN_DHTML_URL_EVENT_MAP  
 Запускает многостраничное диалоговое окно Определение сопоставления событий DHTML и URL-адрес.  
  
```  
BEGIN_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Примечания  
 Поместите `BEGIN_DHTML_URL_EVENT_MAP` в файле реализации вашей [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производного класса. Следовать ей с [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map) и [URL-адресов,](#begin_url_entries), а затем закройте его с [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Включить [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) макрос внутри определения класса.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="begin_embed_dhtml_event_map"></a>  BEGIN_EMBED_DHTML_EVENT_MAP  
 Запускает определение внедренного карта событий DHTML многостраничное диалоговое окно.  
  
```  
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего схема событий. Этот класс должен наследоваться от прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Внедренные DHTML-схема событий должны находиться внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).  
  
 *mapName*  
 Указывает, что страница, событие которого сопоставления. Это соответствует *mapName* в [URL_EVENT_ENTRY](#url_event_entry) макрос фактически определению ресурса URL-адрес или HTML.  
  
### <a name="remarks"></a>Примечания  
 Поскольку многостраничное диалоговое окно DHTML состоит из несколько HTML-страниц, каждая из которых может создавать события DHTML, схемы внедренные событий используются для сопоставления событий с обработчиками на уровне страниц.  
  
 Схемы событий внедренные в карту событий DHTML и URL-адрес состоит из `BEGIN_EMBED_DHTML_EVENT_MAP` макрос, за которым следует [DHTML_EVENT](#dhtml_event) макросы и [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) макрос.  
  
 Каждая карта внедренные событий требуется соответствующий [записью о событии URL-адрес](#url_event_entry) для сопоставления *mapName* (указано в `BEGIN_EMBED_DHTML_EVENT_MAP`) к ресурсу URL-адрес или HTML.  
  
### <a name="example"></a>Пример  
 См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="begin_url_entries"></a>  BEGIN_URL_ENTRIES  
 Запускает Определение сопоставления URL-адрес запись событий в многостраничное диалоговое окно.  
  
```  
BEGIN_URL_ENTRIES(className)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего URL-адрес карты запись событий. Этот класс должен наследоваться от прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). URL-адрес события входа должны быть заданы внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).  
  
### <a name="remarks"></a>Примечания  
 Поскольку многостраничное диалоговое окно DHTML состоит из нескольких страниц HTML, URL-адресов, события используются для сопоставления URL-адреса или HTML-ресурсы, соответствующий [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map). Поместите `URL_EVENT_ENTRY` макросы между `BEGIN_URL_ENTRIES` и [END_URL_ENTRIES](#end_url_entries) макросы.  
  
### <a name="example"></a>Пример  
 См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="declare_dhtml_url_event_map"></a>  DECLARE_DHTML_URL_EVENT_MAP  
 Объявляет схема событий DHTML и URL-адрес в определении класса.  
  
```  
DECLARE_DHTML_URL_EVENT_MAP()  
 
```  
  
### <a name="remarks"></a>Примечания  
 Этот макрос будет использоваться в определении [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производные классы.  
  
 Сопоставление событий DHTML и URL-адрес содержит [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map) и [URL-адресов, событие](#begin_url_entries) для сопоставления DHTML-события для обработчиков на уровне страниц. Используйте [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) реализовать схему.  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="end_dhtml_url_event_map"></a>  END_DHTML_URL_EVENT_MAP  
 Отмечает конец карты событий DHTML и URL-адрес.  
  
```  
END_DHTML_URL_EVENT_MAP(className)  
 
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего схема событий. Этот класс должен наследоваться от прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Оно должно соответствовать `className` в соответствующем [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) макрос.  
  
### <a name="example"></a>Пример  
 См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="end_embed_dhtml_event_map"></a>  END_EMBED_DHTML_EVENT_MAP  
 Отмечает конец внедренного карта событий DHTML.  
  
```  
END_EMBED_DHTML_EVENT_MAP()  
 
```  
  
### <a name="example"></a>Пример  
 См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="end_url_entries"></a>  END_URL_ENTRIES  
 Отмечает конец карты запись событий URL-адрес.  
  
```  
END_URL_ENTRIES()  
 
```  
  
### <a name="example"></a>Пример  
 См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  
  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  
  
##  <a name="url_event_entry"></a>  URL_EVENT_ENTRY  
 Сопоставляет ресурс URL-адрес или HTML-страницу в многостраничное диалоговое окно.  
  
```  
URL_EVENT_ENTRY(className, url,  mapName)   
```  
  
### <a name="parameters"></a>Параметры  
 `className`  
 Имя класса, содержащего URL-адрес карты запись событий. Этот класс должен наследоваться от прямо или косвенно [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). URL-адрес события входа должны быть заданы внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).  
  
 *URL-адрес*  
 Ресурс URL-адрес или HTML-страницы.  
  
 *mapName*  
 Указывает URL-адресом страницы *URL-адрес*. Это соответствует *mapName* в [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) макрос, который сопоставляет события с этой страницы.  
  
### <a name="remarks"></a>Примечания  
 Если страница является ресурс HTML *URL-адрес* должен быть строковым представлением номер идентификатора ресурса (то есть «123», не 123 или ID_HTMLRES1).  
  
 Идентификатор страницы *mapName*, — это произвольный символов, используемых для связывания встроенные схемы событий DHTML схемы запись событий URL-адрес. Ограничен областью, на схеме событий DHTML и URL-адрес.  
  
### <a name="example"></a>Пример  
 См. пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).  

  
### <a name="requirements"></a>Требования  
  **Заголовок** afxdhtml.h  

##  <a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE
Отмечает конец DHTML-схема событий.  
   
### <a name="syntax"></a>Синтаксис    
```
END_DHTML_EVENT_MAP_INLINE( )    
```  
   
### <a name="remarks"></a>Примечания  
 Необходимо использовать в сочетании с [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxdhtml.h  
   
### <a name="see-also"></a>См. также  
 [Макросы и глобальные объекты](mfc-macros-and-globals.md)   
