---
title: Схемы событий DHTML | Документация Майкрософт
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
ms.openlocfilehash: 5942a41272671a391cb600ef959d2c69b0bab3e3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46419039"
---
# <a name="dhtml-event-maps"></a>Схемы событий DHTML

Следующие макросы можно использовать для обработки событий DHTML.

## <a name="dhtml-event-map-macros"></a>Макросы схемы событий DHTML

Следующие макросы можно использовать для обработки событий DHTML в [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-производные классы.

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Помечает начало схемы событий DHTML.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Помечает начало схемы событий DHTML.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Объявляет DHTML-схема событий.|
|[DHTML_EVENT](#dhtml_event)|Используется для обработки события на уровне документа для единичного элемента HTML.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Используется для обработки события, инициированные средой элемент управления ActiveX.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Используется для обработки события на уровне документа для всех элементов HTML с помощью определенного класса CSS.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Используется для обработки события на уровне элемента.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|Используется для обработки `onafterupdate` события из HTML-элемент.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|Используется для обработки `onbeforeupdate` события из HTML-элемент.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|Используется для обработки `onblur` события из HTML-элемент.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|Используется для обработки `onchange` события из HTML-элемент.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|Используется для обработки `onclick` события из HTML-элемент.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|Используется для обработки `ondataavailable` события из HTML-элемент.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|Используется для обработки `ondatasetchanged` события из HTML-элемент.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|Используется для обработки `ondatasetcomplete` события из HTML-элемент.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|Используется для обработки `ondblclick` события из HTML-элемент.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|Используется для обработки `ondragstart` события из HTML-элемент.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|Используется для обработки `onerrorupdate` события из HTML-элемент.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|Используется для обработки `onfilterchange` события из HTML-элемент.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|Используется для обработки `onfocus` события из HTML-элемент.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|Используется для обработки `onhelp` события из HTML-элемент.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|Используется для обработки `onkeydown` события из HTML-элемент.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|Используется для обработки `onkeypress` события из HTML-элемент.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|Используется для обработки `onkeyup` события из HTML-элемент.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|Используется для обработки `onmousedown` события из HTML-элемент.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|Используется для обработки `onmousemove` события из HTML-элемент.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|Используется для обработки `onmouseout` события из HTML-элемент.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|Используется для обработки `onmouseover` события из HTML-элемент.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|Используется для обработки `onmouseup` события из HTML-элемент.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|Используется для обработки `onresize` события из HTML-элемент.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|Используется для обработки `onrowenter` события из HTML-элемент.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|Используется для обработки `onrowexit` события из HTML-элемент.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|Используется для обработки `onselectstart` события из HTML-элемент.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Используется для обработки события на уровне документа для всех элементов с определенным тегом HTML.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Помечает конец DHTML-схема событий.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|Помечает конец DHTML-схема событий. |

## <a name="url-event-map-macros"></a>Макросы схемы событий URL-адрес

Следующие макросы можно использовать для обработки событий DHTML в [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производные классы.

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Помечает начало многостраничной схемы событий DHTML и URL-адрес.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Помечает начало embedded карта событий DHTML.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Отмечает начало карты запись событий URL-адрес.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Объявляет многостраничной карты событий DHTML и URL-адрес.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Помечает конец многостраничной карты событий DHTML и URL-адрес.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Помечает конец внедренного карта событий DHTML.|
|[END_URL_ENTRIES](#end_url_entries)|Помечает конец карты запись событий URL-адрес.|
|[URL_EVENT_ENTRY](#url_event_entry)|Сопоставляет ресурс URL-адрес или HTML-страницу в многостраничное диалоговое окно.|

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="begin_dhtml_event_map"></a>  BEGIN_DHTML_EVENT_MAP

Отмечает начало карты событий DHTML при помещении в исходном файле для класса, идентифицируемый `className`.

```
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего DHTML-схема событий. Этот класс должен прямо или косвенно наследующие от [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включают [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в соответствии с определением класса.

### <a name="remarks"></a>Примечания

Добавьте в класс для предоставления сведений о DHTML-схема событий `CDHtmlDialog` , может использоваться для маршрута события, инициируемые HTML-элементов и элементов управления ActiveX в веб-страницы функций обработчика в классе.

Поместите begin_dhtml_event_map-макрос в классе реализации (CPP) файла, а затем DHTML_EVENT макросы для событий, которые классу — обработка (например, DHTML_EVENT_ONMOUSEOVER для события наведения мыши). Используйте [END_DHTML_EVENT_MAP](#end_dhtml_event_map) макрос для обозначения конца набора карты событий. Эти макросы реализовать следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="begin_dhtml_event_map_inline"></a>  BEGIN_DHTML_EVENT_MAP_INLINE

Помечает начало DHTML-схема событий внутри определения класса для *className*.

```
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего DHTML-схема событий. Этот класс должен прямо или косвенно наследующие от [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включают [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в соответствии с определением класса.

### <a name="remarks"></a>Примечания

Добавьте в класс для предоставления сведений о DHTML-схема событий `CDHtmlDialog` , может использоваться для маршрута события, инициируемые HTML-элементов и элементов управления ActiveX в веб-страницы функций обработчика в классе.

Begin_dhtml_event_map-макрос поместите в класс определения (.h) с последующими макросами DHTML_EVENT отслеживаемых классу — обработка событий (например, DHTML_EVENT_ONMOUSEOVER для события наведения мыши). Используйте [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) макрос для обозначения конца набора карты событий. Эти макросы реализовать следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h


##  <a name="declare_dhtml_event_map"></a>  DECLARE_DHTML_EVENT_MAP

Объявляет DHTML-схема событий в определении класса.

```
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Примечания

Этот макрос будет использоваться в определении [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)-производные классы.

Используйте [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) или [BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline) для реализации карты.

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) объявляет следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event"></a>  DHTML_EVENT

Обрабатывает (на уровне документа) событие, обозначенное *dispid* с HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
DISPID обрабатываемого события.

*elemName*<br/>
LPCWSTR, содержащий идентификатор HTML-элемента, источники событий, или значение NULL, чтобы обрабатывать события документа.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_axcontrol"></a>  DHTML_EVENT_AXCONTROL

Обрабатывает событие, обозначенное *dispid* , инициированные средой управления ActiveX, идентифицируемого *ИмяЭлементаУправления*.

```
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
Идентификатор диспетчеризации событий для обработки.

*ИмяЭлементаУправления*<br/>
LPCWSTR, содержащий HTML-идентификатор элемента управления, запускающий событие.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_class"></a>  DHTML_EVENT_CLASS

Обрабатывает (на уровне документа) событие, обозначенное *dispid* исходящих от любой элемент HTML с классом CSS, идентифицируемый *elemName*.

```
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
Идентификатор диспетчеризации событий для обработки.

*elemName*<br/>
LPCWSTR, содержащий класс CSS, HTML-элементов, источников событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_element"></a>  DHTML_EVENT_ELEMENT

Обрабатывает (с элементом, определяемым *elemName*) событие, обозначенное *dispid*.

```
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
Идентификатор диспетчеризации событий для обработки.

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

Если этот макрос используется для обработки событий nonbubbling, источник события будет элементом, определяемым *elemName*.

Если этот макрос используется для обработки события восходящей маршрутизации, элемент, определяемый *elemName* не может быть источником события (источник может быть любой элемент, включенный в *elemName*).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onafterupdate"></a>  DHTML_EVENT_ONAFTERUPDATE

Обрабатывает (на уровне документа) `onafterupdate` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onbeforeupdate"></a>  DHTML_EVENT_ONBEFOREUPDATE

Обрабатывает (на уровне документа) `onbeforeupdate` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onblur"></a>  DHTML_EVENT_ONBLUR

Обрабатывает (на уровне элемента) `onblur` событий. Это событие nonbubbling.

```
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onchange"></a>  DHTML_EVENT_ONCHANGE

Обрабатывает (на уровне элемента) `onchange` событий. Это событие nonbubbling.

```
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onclick"></a>  DHTML_EVENT_ONCLICK

Обрабатывает (на уровне документа) `onclick` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_ondataavailable"></a>  DHTML_EVENT_ONDATAAVAILABLE

Обрабатывает (на уровне документа) `ondataavailable` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_ondatasetchanged"></a>  DHTML_EVENT_ONDATASETCHANGED

Обрабатывает (на уровне документа) `ondatasetchanged` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_ondatasetcomplete"></a>  DHTML_EVENT_ONDATASETCOMPLETE

Обрабатывает (на уровне документа) `ondatasetcomplete` событий, исходящих от HTML-элемент, идентифицируемый `elemName`.

```
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_ondblclick"></a>  DHTML_EVENT_ONDBLCLICK

Обрабатывает (на уровне документа) `ondblclick` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_ondragstart"></a>  DHTML_EVENT_ONDRAGSTART

Обрабатывает (на уровне документа) `ondragstart` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onerrorupdate"></a>  DHTML_EVENT_ONERRORUPDATE

Обрабатывает (на уровне документа) `onerrorupdate` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onfilterchange"></a>  DHTML_EVENT_ONFILTERCHANGE

Обрабатывает (на уровне документа) `onfilterchange` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onfocus"></a>  DHTML_EVENT_ONFOCUS

Обрабатывает (на уровне элемента) `onfocus` событий. Это событие nonbubbling.

```

DHTML_EVENT_ONFOCUS(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onhelp"></a>  DHTML_EVENT_ONHELP

Обрабатывает (на уровне документа) `onhelp` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONHELP(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onkeydown"></a>  DHTML_EVENT_ONKEYDOWN

Обрабатывает (на уровне документа) `onkeydown` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onkeypress"></a>  DHTML_EVENT_ONKEYPRESS

Обрабатывает (на уровне документа) `onkeypress` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onkeyup"></a>  DHTML_EVENT_ONKEYUP

Обрабатывает (на уровне документа) `onkeyup` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONKEYUP(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onmousedown"></a>  DHTML_EVENT_ONMOUSEDOWN

Обрабатывает (на уровне документа) `onmousedown` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onmousemove"></a>  DHTML_EVENT_ONMOUSEMOVE

Обрабатывает (на уровне документа) `onmousemove` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onmouseout"></a>  DHTML_EVENT_ONMOUSEOUT

Обрабатывает (на уровне документа) `onmouseout` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onmouseover"></a>  DHTML_EVENT_ONMOUSEOVER

Обрабатывает (на уровне документа) `onmouseover` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onmouseup"></a>  DHTML_EVENT_ONMOUSEUP

Обрабатывает (на уровне документа) `onmouseup` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onresize"></a>  DHTML_EVENT_ONRESIZE

Обрабатывает (на уровне элемента) `onresize` событий. Это событие nonbubbling.

```

DHTML_EVENT_ONRESIZE(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onrowenter"></a>  DHTML_EVENT_ONROWENTER

Обрабатывает (на уровне документа) `onrowenter` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONROWENTER(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onrowexit"></a>  DHTML_EVENT_ONROWEXIT

Обрабатывает (на уровне документа) `onrowexit` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONROWEXIT(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_onselectstart"></a>  DHTML_EVENT_ONSELECTSTART

Обрабатывает (на уровне документа) `onselectstart` событий, исходящих от HTML-элемент, идентифицируемый *elemName*.

```

DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)

```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR содержит идентификатор элемента HTML, источники событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="dhtml_event_tag"></a>  DHTML_EVENT_TAG

Обрабатывает (на уровне документа) событие, обозначенное `dispid` исходящих от любой HTML-элемент с HTML-тег, идентифицируемый *elemName*.

```
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Идентификатор DISPID*<br/>
Идентификатор диспетчеризации событий для обработки.

*elemName*<br/>
Тег HTML, HTML-элементов, источников событий.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Примечания

Используйте этот макрос, чтобы добавить запись [DHTML-схема событий](#begin_dhtml_event_map_inline) в классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="end_dhtml_event_map"></a>  END_DHTML_EVENT_MAP

Помечает конец DHTML-схема событий.

```
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Примечания

Необходимо использовать в сочетании с [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="begin_dhtml_url_event_map"></a>  BEGIN_DHTML_URL_EVENT_MAP

Начинается определение схемы событий DHTML и URL-адрес в многостраничное диалоговое окно.

```
BEGIN_DHTML_URL_EVENT_MAP()

```

### <a name="remarks"></a>Примечания

Поместите BEGIN_DHTML_URL_EVENT_MAP в файле реализации вашей [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производного класса. Следовать ей с [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map) и [URL-адресов,](#begin_url_entries), а затем закройте его с [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Включить [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) макрос внутри определения класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="begin_embed_dhtml_event_map"></a>  BEGIN_EMBED_DHTML_EVENT_MAP

Начинается определение внедренного карта событий DHTML многостраничное диалоговое окно.

```
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)

```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карты событий. Этот класс должен прямо или косвенно наследующие от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Внедренные DHTML-схема событий должны находиться внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).

*mapName*<br/>
Указывает, что страница, событие которого сопоставления. Это соответствует *mapName* в [URL_EVENT_ENTRY](#url_event_entry) макрос, фактически определения ресурса URL-адрес или HTML.

### <a name="remarks"></a>Примечания

Поскольку многостраничное диалоговое окно DHTML состоит из нескольких страниц HTML, каждый из которых может создавать события DHTML, схемы embedded событий используются для сопоставления событий к обработчикам отдельно на странице.

Схемы событий Embedded на карте событий DHTML и URL-адрес будет состоять из begin_embed_dhtml_event_map-макрос, за которым следует [DHTML_EVENT](#dhtml_event) макросы и [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) макрос.

Каждая карта embedded событий требует соответствующего [URL-адрес записи события](#url_event_entry) для сопоставления *mapName* (заданный в BEGIN_EMBED_DHTML_EVENT_MAP) к ресурсу URL-адрес или HTML.

### <a name="example"></a>Пример

Ознакомьтесь с примером в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="begin_url_entries"></a>  BEGIN_URL_ENTRIES

Начинается определение сопоставления URL-адрес записи событий в многостраничное диалоговое окно.

```
BEGIN_URL_ENTRIES(className)

```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту запись событий URL-адрес. Этот класс должен прямо или косвенно наследующие от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Схема запись событий URL-адрес должны находиться внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).

### <a name="remarks"></a>Примечания

Так как многостраничное диалоговое окно DHTML состоит из нескольких страниц HTML, URL-адрес записи событий используются для сопоставления URL-адреса или HTML-ресурсы с соответствующими [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map). Поместите макросы URL_EVENT_ENTRY между BEGIN_URL_ENTRIES и [END_URL_ENTRIES](#end_url_entries) макросы.

### <a name="example"></a>Пример

Ознакомьтесь с примером в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="declare_dhtml_url_event_map"></a>  DECLARE_DHTML_URL_EVENT_MAP

Объявляет карты событий DHTML и URL-адрес в определение класса.

```
DECLARE_DHTML_URL_EVENT_MAP()

```

### <a name="remarks"></a>Примечания

Этот макрос будет использоваться в определении [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md)-производные классы.

Сопоставление событий DHTML и URL-адрес содержит [встроенные схемы событий DHTML](#begin_embed_dhtml_event_map) и [URL-адрес записи событий](#begin_url_entries) для сопоставления событий DHTML обработчикам отдельно на странице. Используйте [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) для реализации карты.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="end_dhtml_url_event_map"></a>  END_DHTML_URL_EVENT_MAP

Помечает конец карты событий DHTML и URL-адрес.

```
END_DHTML_URL_EVENT_MAP(className)

```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карты событий. Этот класс должен прямо или косвенно наследующие от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Оно должно соответствовать *className* в соответствующем [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) макрос.

### <a name="example"></a>Пример

Ознакомьтесь с примером в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="end_embed_dhtml_event_map"></a>  END_EMBED_DHTML_EVENT_MAP

Помечает конец внедренного карта событий DHTML.

```
END_EMBED_DHTML_EVENT_MAP()

```

### <a name="example"></a>Пример

Ознакомьтесь с примером в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="end_url_entries"></a>  END_URL_ENTRIES

Помечает конец карты запись событий URL-адрес.

```
END_URL_ENTRIES()

```

### <a name="example"></a>Пример

Ознакомьтесь с примером в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="url_event_entry"></a>  URL_EVENT_ENTRY

Сопоставляет ресурс URL-адрес или HTML-страницу в многостраничное диалоговое окно.

```
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>Параметры

*className*<br/>
Имя класса, содержащего карту запись событий URL-адрес. Этот класс должен прямо или косвенно наследующие от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Схема запись событий URL-адрес должны находиться внутри [схема событий DHTML и URL-адрес](#begin_dhtml_url_event_map)).

*URL-адрес*<br/>
Ресурс URL-адрес или HTML-страницы.

*mapName*<br/>
Указывает URL-адресом страницы *URL-адрес*. Это соответствует *mapName* в [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) макрос, который сопоставляет события с этой страницы.

### <a name="remarks"></a>Примечания

Если страница является ресурс HTML *URL-адрес* должен быть строковым представлением ресурса Идентификационный номер (то есть «123», не 123 или ID_HTMLRES1).

Идентификатор страницы *mapName*, внедряется произвольного символа используется для связывания схемы событий DHTML для схемы запись событий URL-адрес. Она ограничена областью, на схеме событий DHTML и URL-адрес.

### <a name="example"></a>Пример

Ознакомьтесь с примером в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).


### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

##  <a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE

Помечает конец DHTML-схема событий.

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
