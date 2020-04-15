---
title: Схемы событий DHTML
ms.date: 11/04/2016
f1_keywords:
- vc.macros.shared
helpviewer_keywords:
- event map macros [MFC]
- DHTML [MFC], event map macros
- macros [MFC], DHTML event map
- DHTML events [MFC], event map
- DHTML events [MFC]
ms.assetid: 9a2c8ae7-7216-4a5e-bc60-6b98695be0c6
ms.openlocfilehash: 30c755b2901374cffab3ce91d0683811ef6624b6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365810"
---
# <a name="dhtml-event-maps"></a>Схемы событий DHTML

Следующие макросы могут быть использованы для обработки событий DHTML.

## <a name="dhtml-event-map-macros"></a>DHTML Событие Карта Макрос

Следующие макросы могут использоваться для обработки событий DHTML в классах [CDHtmlDialog.](../../mfc/reference/cdhtmldialog-class.md)

|||
|-|-|
|[BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map)|Отмечает начало карты событий DHTML.|
|[BEGIN_DHTML_EVENT_MAP_INLINE](#begin_dhtml_event_map_inline)|Отмечает начало карты событий DHTML.|
|[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map)|Объявляет карту событий DHTML.|
|[DHTML_EVENT](#dhtml_event)|Используется для обработки события на уровне документа для одного элемента HTML.|
|[DHTML_EVENT_AXCONTROL](#dhtml_event_axcontrol)|Используется для обработки события, выпущенного системой управления ActiveX.|
|[DHTML_EVENT_CLASS](#dhtml_event_class)|Используется для обработки события на уровне документа для всех элементов HTML с определенным классом CSS.|
|[DHTML_EVENT_ELEMENT](#dhtml_event_element)|Используется для обработки события на уровне элемента.|
|[DHTML_EVENT_ONAFTERUPDATE](#dhtml_event_onafterupdate)|Используется для `onafterupdate` обработки события из html элемента.|
|[DHTML_EVENT_ONBEFOREUPDATE](#dhtml_event_onbeforeupdate)|Используется для `onbeforeupdate` обработки события из html элемента.|
|[DHTML_EVENT_ONBLUR](#dhtml_event_onblur)|Используется для `onblur` обработки события из html элемента.|
|[DHTML_EVENT_ONCHANGE](#dhtml_event_onchange)|Используется для `onchange` обработки события из html элемента.|
|[DHTML_EVENT_ONCLICK](#dhtml_event_onclick)|Используется для `onclick` обработки события из html элемента.|
|[DHTML_EVENT_ONDATAAVAILABLE](#dhtml_event_ondataavailable)|Используется для `ondataavailable` обработки события из html элемента.|
|[DHTML_EVENT_ONDATASETCHANGED](#dhtml_event_ondatasetchanged)|Используется для `ondatasetchanged` обработки события из html элемента.|
|[DHTML_EVENT_ONDATASETCOMPLETE](#dhtml_event_ondatasetcomplete)|Используется для `ondatasetcomplete` обработки события из html элемента.|
|[DHTML_EVENT_ONDBLCLICK](#dhtml_event_ondblclick)|Используется для `ondblclick` обработки события из html элемента.|
|[DHTML_EVENT_ONDRAGSTART](#dhtml_event_ondragstart)|Используется для `ondragstart` обработки события из html элемента.|
|[DHTML_EVENT_ONERRORUPDATE](#dhtml_event_onerrorupdate)|Используется для `onerrorupdate` обработки события из html элемента.|
|[DHTML_EVENT_ONFILTERCHANGE](#dhtml_event_onfilterchange)|Используется для `onfilterchange` обработки события из html элемента.|
|[DHTML_EVENT_ONFOCUS](#dhtml_event_onfocus)|Используется для `onfocus` обработки события из html элемента.|
|[DHTML_EVENT_ONHELP](#dhtml_event_onhelp)|Используется для `onhelp` обработки события из html элемента.|
|[DHTML_EVENT_ONKEYDOWN](#dhtml_event_onkeydown)|Используется для `onkeydown` обработки события из html элемента.|
|[DHTML_EVENT_ONKEYPRESS](#dhtml_event_onkeypress)|Используется для `onkeypress` обработки события из html элемента.|
|[DHTML_EVENT_ONKEYUP](#dhtml_event_onkeyup)|Используется для `onkeyup` обработки события из html элемента.|
|[DHTML_EVENT_ONMOUSEDOWN](#dhtml_event_onmousedown)|Используется для `onmousedown` обработки события из html элемента.|
|[DHTML_EVENT_ONMOUSEMOVE](#dhtml_event_onmousemove)|Используется для `onmousemove` обработки события из html элемента.|
|[DHTML_EVENT_ONMOUSEOUT](#dhtml_event_onmouseout)|Используется для `onmouseout` обработки события из html элемента.|
|[DHTML_EVENT_ONMOUSEOVER](#dhtml_event_onmouseover)|Используется для `onmouseover` обработки события из html элемента.|
|[DHTML_EVENT_ONMOUSEUP](#dhtml_event_onmouseup)|Используется для `onmouseup` обработки события из html элемента.|
|[DHTML_EVENT_ONRESIZE](#dhtml_event_onresize)|Используется для `onresize` обработки события из html элемента.|
|[DHTML_EVENT_ONROWENTER](#dhtml_event_onrowenter)|Используется для `onrowenter` обработки события из html элемента.|
|[DHTML_EVENT_ONROWEXIT](#dhtml_event_onrowexit)|Используется для `onrowexit` обработки события из html элемента.|
|[DHTML_EVENT_ONSELECTSTART](#dhtml_event_onselectstart)|Используется для `onselectstart` обработки события из html элемента.|
|[DHTML_EVENT_TAG](#dhtml_event_tag)|Используется для обработки события на уровне документа для всех элементов с определенным тегом HTML.|
|[END_DHTML_EVENT_MAP](#end_dhtml_event_map)|Отметка окончания карты событий DHTML.|
|[END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline)|Отметка окончания карты событий DHTML. |

## <a name="url-event-map-macros"></a>URL Карта событий Макрос

Следующие макросы могут использоваться для обработки событий DHTML в классах [CMultiPageDHtmlDialog.](../../mfc/reference/cmultipagedhtmldialog-class.md)

|||
|-|-|
|[BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map)|Отмечает начало многостраничной карты событий DHTML и URL-адреса.|
|[BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map)|Отмечает начало встроенной карты событий DHTML.|
|[BEGIN_URL_ENTRIES](#begin_url_entries)|Отметка начала карты входа события URL-адреса.|
|[DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map)|Объявляет многостраничную карту событий DHTML и URL.|
|[END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map)|Отметка конец многостраничной карты событий DHTML и URL.|
|[END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map)|Отметка конца встроенной карты событий DHTML.|
|[END_URL_ENTRIES](#end_url_entries)|Отметка конца карты входа события URL-адреса.|
|[URL_EVENT_ENTRY](#url_event_entry)|Отображает URL или HTML-ресурс на страницу в многостраничном диалоге.|

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="begin_dhtml_event_map"></a><a name="begin_dhtml_event_map"></a>BEGIN_DHTML_EVENT_MAP

Отметка начала карты событий DHTML при размещении в `className`исходном файле для класса, идентифицированного .

```cpp
BEGIN_DHTML_EVENT_MAP(className)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, содержащее карту событий DHTML. Этот класс должен прямо или косвенно вытекать из [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включать [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в свое определение класса.

### <a name="remarks"></a>Remarks

Добавьте карту событий DHTML в свой `CDHtmlDialog` класс, чтобы предоставить информацию, которая может быть использована для маршрутизатора событий, выпущенных html-элементами или элементами управления ActiveX на веб-странице, для обработчика функций в вашем классе.

Поместите BEGIN_DHTML_EVENT_MAP макрос в файл реализации класса (.cpp), а затем DHTML_EVENT макросов для событий, которые должен обрабатывать класс (например, DHTML_EVENT_ONMOUSEOVER для событий mouseover). Используйте [END_DHTML_EVENT_MAP](#end_dhtml_event_map) макрос, чтобы отметить конец карты событий. Эти макросы реализуют следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="begin_dhtml_event_map_inline"></a><a name="begin_dhtml_event_map_inline"></a>BEGIN_DHTML_EVENT_MAP_INLINE

Отмечает начало карты событий DHTML в определении класса для *className.*

```cpp
BEGIN_DHTML_EVENT_MAP_INLINE(className)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, содержащее карту событий DHTML. Этот класс должен прямо или косвенно вытекать из [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md) и включать [DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) макрос в свое определение класса.

### <a name="remarks"></a>Remarks

Добавьте карту событий DHTML в свой `CDHtmlDialog` класс, чтобы предоставить информацию, которая может быть использована для маршрутизатора событий, выпущенных html-элементами или элементами управления ActiveX на веб-странице, для обработчика функций в вашем классе.

Поместите BEGIN_DHTML_EVENT_MAP макрос в файл определения класса (.h), а затем DHTML_EVENT макросов для событий, которые должен обрабатывать класс (например, DHTML_EVENT_ONMOUSEOVER для событий mouseover). Используйте [END_DHTML_EVENT_MAP_INLINE](#end_dhtml_event_map_inline) макрос, чтобы отметить конец карты событий. Эти макросы реализуют следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap();`

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="declare_dhtml_event_map"></a><a name="declare_dhtml_event_map"></a>DECLARE_DHTML_EVENT_MAP

Объявляет карту событий DHTML в определении класса.

```cpp
DECLARE_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Remarks

Этот макрос должен использоваться в определении классов [CDHtmlDialog.](../../mfc/reference/cdhtmldialog-class.md)

Для реализации карты используйте [BEGIN_DHTML_EVENT_MAP](#begin_dhtml_event_map) или [BEGIN_DHTML_EVENT_MAP_INLINE.](#begin_dhtml_event_map_inline)

[DECLARE_DHTML_EVENT_MAP](#declare_dhtml_event_map) объявляет следующую функцию:

`virtual const DHtmlEventMapEntry* GetDHtmlEventMap( );`

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event"></a><a name="dhtml_event"></a>DHTML_EVENT

Ручки (на уровне документа) событие, идентифицированное *dispid,* возникшее по HTML элементу, идентифицированному *elemName.*

```cpp
DHTML_EVENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
DISPID события, которые будут обработаны.

*elemName*<br/>
LPCWSTR, владеющий идентификатором HTML-элемента, вымещающих событие, или NULL для обработки событий документов.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_axcontrol"></a><a name="dhtml_event_axcontrol"></a>DHTML_EVENT_AXCONTROL

Ручки событие, идентифицированное *dispid,* выпущенным диспетчером ActiveX, идентифицированным *controlName.*

```cpp
DHTML_EVENT_AXCONTROL(dispid, controlName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Идентификатор отправки события, который необходимо обработать.

*контрольНое*<br/>
LPCWSTR, держащий HTML ID элемента управления, запуская событие.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_class"></a><a name="dhtml_event_class"></a>DHTML_EVENT_CLASS

Ручки (на уровне документа) событие, идентифицированное *dispid,* возникшее любым элементом HTML с классом CSS, идентифицированным *elemName.*

```cpp
DHTML_EVENT_CLASS(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Идентификатор отправки события, который необходимо обработать.

*elemName*<br/>
LPCWSTR, владеющий классом HTML-элементов CSS, источников события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_element"></a><a name="dhtml_event_element"></a>DHTML_EVENT_ELEMENT

Ручки (на элементе, идентифицированном *elemName*) событие, идентифицированное *dispid*.

```cpp
DHTML_EVENT_ELEMENT(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Идентификатор отправки события, который необходимо обработать.

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

Если этот макрос используется для обработки событий nonbubbling, источником события будет элемент, идентифицированный *elemName*.

Если этот макрос используется для обработки восходящей событий, элемент, идентифицированный *elemName,* не может быть источником события (источником может быть любой элемент, содержащийся *в elemName).*

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onafterupdate"></a><a name="dhtml_event_onafterupdate"></a>DHTML_EVENT_ONAFTERUPDATE

Ручки (на уровне документа) `onafterupdate` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONAFTERUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onbeforeupdate"></a><a name="dhtml_event_onbeforeupdate"></a>DHTML_EVENT_ONBEFOREUPDATE

Ручки (на уровне документа) `onbeforeupdate` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONBEFOREUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onblur"></a><a name="dhtml_event_onblur"></a>DHTML_EVENT_ONBLUR

Ручки (на уровне элемента) `onblur` события. Это небаблинговое событие.

```cpp
DHTML_EVENT_ONBLUR(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onchange"></a><a name="dhtml_event_onchange"></a>DHTML_EVENT_ONCHANGE

Ручки (на уровне элемента) `onchange` события. Это небаблинговое событие.

```cpp
DHTML_EVENT_ONCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onclick"></a><a name="dhtml_event_onclick"></a>DHTML_EVENT_ONCLICK

Ручки (на уровне документа) `onclick` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_ondataavailable"></a><a name="dhtml_event_ondataavailable"></a>DHTML_EVENT_ONDATAAVAILABLE

Ручки (на уровне документа) `ondataavailable` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONDATAAVAILABLE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_ondatasetchanged"></a><a name="dhtml_event_ondatasetchanged"></a>DHTML_EVENT_ONDATASETCHANGED

Ручки (на уровне документа) `ondatasetchanged` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONDATASETCHANGED(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_ondatasetcomplete"></a><a name="dhtml_event_ondatasetcomplete"></a>DHTML_EVENT_ONDATASETCOMPLETE

Ручки (на уровне документа) `ondatasetcomplete` события возникли из `elemName`HTML элемент, определенный .

```cpp
DHTML_EVENT_ONDATASETCOMPLETE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_ondblclick"></a><a name="dhtml_event_ondblclick"></a>DHTML_EVENT_ONDBLCLICK

Ручки (на уровне документа) `ondblclick` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONDBLCLICK(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_ondragstart"></a><a name="dhtml_event_ondragstart"></a>DHTML_EVENT_ONDRAGSTART

Ручки (на уровне документа) `ondragstart` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONDRAGSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onerrorupdate"></a><a name="dhtml_event_onerrorupdate"></a>DHTML_EVENT_ONERRORUPDATE

Ручки (на уровне документа) `onerrorupdate` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONERRORUPDATE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onfilterchange"></a><a name="dhtml_event_onfilterchange"></a>DHTML_EVENT_ONFILTERCHANGE

Ручки (на уровне документа) `onfilterchange` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONFILTERCHANGE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onfocus"></a><a name="dhtml_event_onfocus"></a>DHTML_EVENT_ONFOCUS

Ручки (на уровне элемента) `onfocus` события. Это небаблинговое событие.

```cpp
DHTML_EVENT_ONFOCUS(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onhelp"></a><a name="dhtml_event_onhelp"></a>DHTML_EVENT_ONHELP

Ручки (на уровне документа) `onhelp` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONHELP(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onkeydown"></a><a name="dhtml_event_onkeydown"></a>DHTML_EVENT_ONKEYDOWN

Ручки (на уровне документа) `onkeydown` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONKEYDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onkeypress"></a><a name="dhtml_event_onkeypress"></a>DHTML_EVENT_ONKEYPRESS

Ручки (на уровне документа) `onkeypress` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONKEYPRESS(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onkeyup"></a><a name="dhtml_event_onkeyup"></a>DHTML_EVENT_ONKEYUP

Ручки (на уровне документа) `onkeyup` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONKEYUP(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onmousedown"></a><a name="dhtml_event_onmousedown"></a>DHTML_EVENT_ONMOUSEDOWN

Ручки (на уровне документа) `onmousedown` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONMOUSEDOWN(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onmousemove"></a><a name="dhtml_event_onmousemove"></a>DHTML_EVENT_ONMOUSEMOVE

Ручки (на уровне документа) `onmousemove` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONMOUSEMOVE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onmouseout"></a><a name="dhtml_event_onmouseout"></a>DHTML_EVENT_ONMOUSEOUT

Ручки (на уровне документа) `onmouseout` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONMOUSEOUT(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onmouseover"></a><a name="dhtml_event_onmouseover"></a>DHTML_EVENT_ONMOUSEOVER

Ручки (на уровне документа) `onmouseover` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONMOUSEOVER(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onmouseup"></a><a name="dhtml_event_onmouseup"></a>DHTML_EVENT_ONMOUSEUP

Ручки (на уровне документа) `onmouseup` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONMOUSEUP(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onresize"></a><a name="dhtml_event_onresize"></a>DHTML_EVENT_ONRESIZE

Ручки (на уровне элемента) `onresize` события. Это небаблинговое событие.

```cpp
DHTML_EVENT_ONRESIZE(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onrowenter"></a><a name="dhtml_event_onrowenter"></a>DHTML_EVENT_ONROWENTER

Ручки (на уровне документа) `onrowenter` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONROWENTER(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onrowexit"></a><a name="dhtml_event_onrowexit"></a>DHTML_EVENT_ONROWEXIT

Ручки (на уровне документа) `onrowexit` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONROWEXIT(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_onselectstart"></a><a name="dhtml_event_onselectstart"></a>DHTML_EVENT_ONSELECTSTART

Ручки (на уровне документа) `onselectstart` события возникли html элемент, *определенный elemName*.

```cpp
DHTML_EVENT_ONSELECTSTART(elemName, memberFxn)
```

### <a name="parameters"></a>Параметры

*elemName*<br/>
LPCWSTR, держащий идентификатор HTML элемента, источник события.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="dhtml_event_tag"></a><a name="dhtml_event_tag"></a>DHTML_EVENT_TAG

Ручки (на уровне документа) событие, идентифицированное `dispid` по любому элементу HTML с тегом HTML, идентифицированным *elemName.*

```cpp
DHTML_EVENT_TAG(dispid, elemName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*Dispid*<br/>
Идентификатор отправки события, который необходимо обработать.

*elemName*<br/>
HTML-тег HTML элементов, выдавленных событием.

*memberFxn*<br/>
Функция обработчика для события.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы добавить запись на [карту событий DHTML](#begin_dhtml_event_map_inline) в вашем классе.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="end_dhtml_event_map"></a><a name="end_dhtml_event_map"></a>END_DHTML_EVENT_MAP

Отметка окончания карты событий DHTML.

```cpp
END_DHTML_EVENT_MAP()
```

### <a name="remarks"></a>Remarks

Следует использовать в сочетании с [BEGIN_DHTML_EVENT_MAP.](#begin_dhtml_event_map)

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="begin_dhtml_url_event_map"></a><a name="begin_dhtml_url_event_map"></a>BEGIN_DHTML_URL_EVENT_MAP

Запускает определение карты событий DHTML и URL в многостраничном диалоге.

```cpp
BEGIN_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Remarks

Поместите BEGIN_DHTML_URL_EVENT_MAP в файл реализации вашего класса [CMultiPageDHtmlDialog.](../../mfc/reference/cmultipagedhtmldialog-class.md) Следуйте ему со [встроенными картами событий DHTML](#begin_embed_dhtml_event_map) и [ЗАПИСЯМи URL,](#begin_url_entries)а затем закройте его [END_DHTML_URL_EVENT_MAP](#end_dhtml_url_event_map). Включите [DECLARE_DHTML_URL_EVENT_MAP](#declare_dhtml_url_event_map) макрос в определение класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDocView#196](../../mfc/codesnippet/cpp/dhtml-event-maps_1.cpp)]

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="begin_embed_dhtml_event_map"></a><a name="begin_embed_dhtml_event_map"></a>BEGIN_EMBED_DHTML_EVENT_MAP

Запускает определение встроенной карты событий DHTML в многостраничном диалоге.

```cpp
BEGIN_EMBED_DHTML_EVENT_MAP(className, mapName)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, содержащего карту событий. Этот класс должен получить прямо или косвенно от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Встроенная карта событий DHTML должна находиться внутри [карты событий DHTML и URL).](#begin_dhtml_url_event_map)

*картаИмя*<br/>
Уотечьна страница, на карте событий которой это. Это соответствует *mapName* в [URL_EVENT_ENTRY](#url_event_entry) макрос, фактически определяющий URL или HTML ресурс.

### <a name="remarks"></a>Remarks

Поскольку многостраничный диалог DHTML состоит из нескольких HTML-страниц, каждая из которых может вызывать события DHTML, встроенные карты событий используются для картирования событий обработчикам на каждой странице.

Встроенные карты событий в карту событий DHTML и URL состоят из BEGIN_EMBED_DHTML_EVENT_MAP макроса, за которым следуют [DHTML_EVENT](#dhtml_event) макросы и [END_EMBED_DHTML_EVENT_MAP](#end_embed_dhtml_event_map) макрос.

Каждая встроенная карта событий требует соответствующего [входа события URL для](#url_event_entry) карты *mapName* (указано в BEGIN_EMBED_DHTML_EVENT_MAP) на ресурс URL или HTML.

### <a name="example"></a>Пример

Смотрите пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="begin_url_entries"></a><a name="begin_url_entries"></a>BEGIN_URL_ENTRIES

Запускает определение карты входа события URL-адреса в многостраничном диалоге.

```cpp
BEGIN_URL_ENTRIES(className)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, содержащее карту входа события URL-адреса. Этот класс должен получить прямо или косвенно от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Карта входа события URL должна находиться внутри [карты событий DHTML и URL).](#begin_dhtml_url_event_map)

### <a name="remarks"></a>Remarks

Поскольку многостраничный диалог DHTML состоит из нескольких HTML-страниц, записи событий URL используются для отображения URL-адресов или HTML-ресурсов на [соответствующие встроенные карты событий DHTML.](#begin_embed_dhtml_event_map) Поместите URL_EVENT_ENTRY макросы между BEGIN_URL_ENTRIES и [END_URL_ENTRIES](#end_url_entries) макросами.

### <a name="example"></a>Пример

Смотрите пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="declare_dhtml_url_event_map"></a><a name="declare_dhtml_url_event_map"></a>DECLARE_DHTML_URL_EVENT_MAP

Объявляет карту событий DHTML и URL в определении класса.

```cpp
DECLARE_DHTML_URL_EVENT_MAP()
```

### <a name="remarks"></a>Remarks

Этот макрос должен использоваться в определении классов [CMultiPageDHtmlDialog.](../../mfc/reference/cmultipagedhtmldialog-class.md)

Карта событий DHTML и URL содержит [встроенные карты событий DHTML](#begin_embed_dhtml_event_map) и [записи событий URL для](#begin_url_entries) картирования событий DHTML обработчикам на одной странице. Используйте [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) для реализации карты.

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="end_dhtml_url_event_map"></a><a name="end_dhtml_url_event_map"></a>END_DHTML_URL_EVENT_MAP

Отметка конца карты событий DHTML и URL.

```cpp
END_DHTML_URL_EVENT_MAP(className)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, содержащего карту событий. Этот класс должен получить прямо или косвенно от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Это должно соответствовать *className* в соответствующем [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map) макросе.

### <a name="example"></a>Пример

Смотрите пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="end_embed_dhtml_event_map"></a><a name="end_embed_dhtml_event_map"></a>END_EMBED_DHTML_EVENT_MAP

Отметка конца встроенной карты событий DHTML.

```cpp
END_EMBED_DHTML_EVENT_MAP()
```

### <a name="example"></a>Пример

Смотрите пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="end_url_entries"></a><a name="end_url_entries"></a>END_URL_ENTRIES

Отметка конца карты входа события URL-адреса.

```cpp
END_URL_ENTRIES()
```

### <a name="example"></a>Пример

Смотрите пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="url_event_entry"></a><a name="url_event_entry"></a>URL_EVENT_ENTRY

Отображает URL или HTML-ресурс на страницу в многостраничном диалоге.

```cpp
URL_EVENT_ENTRY(className, url,  mapName)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
Название класса, содержащее карту входа события URL-адреса. Этот класс должен получить прямо или косвенно от [CMultiPageDHtmlDialog](../../mfc/reference/cmultipagedhtmldialog-class.md). Карта входа события URL должна находиться внутри [карты событий DHTML и URL).](#begin_dhtml_url_event_map)

*url*<br/>
URL или HTML-ресурс для страницы.

*картаИмя*<br/>
Укажите страницу, *URL-адресом*которой является URL. Это соответствует *mapName* в [BEGIN_EMBED_DHTML_EVENT_MAP](#begin_embed_dhtml_event_map) макросе, который отображает события с этой страницы.

### <a name="remarks"></a>Remarks

Если страница является ресурсом HTML, *URL* должен быть строкой представления идентификационного номера ресурса (т.е. "123", а не 123 или ID_HTMLRES1).

Идентификатор страницы, *mapName*, является произвольным символом, используемым для связи встроенных карт событий DHTML с картами входа в события URL. Она ограничена по охвату картой событий DHTML и URL.

### <a name="example"></a>Пример

Смотрите пример в [BEGIN_DHTML_URL_EVENT_MAP](#begin_dhtml_url_event_map).

### <a name="requirements"></a>Требования

  **Заголовок** afxdhtml.h

## <a name="end_dhtml_event_map_inline"></a><a name="end_dhtml_event_map_inline"></a>END_DHTML_EVENT_MAP_INLINE

Отметка окончания карты событий DHTML.

### <a name="syntax"></a>Синтаксис

```cpp
END_DHTML_EVENT_MAP_INLINE( )
```

### <a name="remarks"></a>Remarks

Следует использовать в сочетании с [BEGIN_DHTML_EVENT_MAP_INLINE.](#begin_dhtml_event_map_inline)

### <a name="requirements"></a>Требования

**Заголовок:** afxdhtml.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)
