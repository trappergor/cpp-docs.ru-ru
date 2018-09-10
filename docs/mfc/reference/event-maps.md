---
title: Схемы событий | Документация Майкрософт
ms.custom: ''
ms.date: 06/20/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.mfc.macros.maps
dev_langs:
- C++
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 21b9efe8fc1ce5cb7ab90edd30b38253d44dabc0
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44106812"
---
# <a name="event-maps"></a>Схемы событий

Каждый раз, когда элемент управления хочет уведомлять его контейнера, что произошло какое-либо действие (определяется разработчиком элемента управления), (например, нажатие клавиши, щелчок мышью или изменение состояния элемента управления), он вызывает функцию обработки событий. Эта функция уведомляет контейнер элемента управления, произошедшем некоторые важные действия по обработке соответствующего события.

Библиотеки Microsoft Foundation Class предоставляет модель программирования, оптимизированный для обработки события. В этой модели «схемы событий» позволяют указать, какие функции срабатывают какие события для конкретного элемента управления. Схемы событий содержат один макрос для каждого события. Например карта событий, запускают акций щелкните событие может выглядеть следующим образом:

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

`EVENT_STOCK_CLICK` Макрос указывает, что элемент управления будет срабатывать акций выберите событие каждый раз при обнаружении мышь, нажмите кнопку. Более подробный список других событий биржевых, см. в статье [элементы управления ActiveX: события](../../mfc/mfc-activex-controls-events.md). Макросы также доступны для указания пользовательских событий.

Несмотря на то, что макросы схемы событий имеет важное значение, обычно не будет вставлена их напрямую. Дело в окне «Свойства» автоматически создает записей событий карты в исходные файлы при использовании его для сопоставления функции обработки событий с событиями. Каждый раз, когда вы хотите изменить или добавить запись схема событий, можно использовать окно свойств.

Чтобы обеспечить поддержку схемы событий, MFC предоставляет следующие макросы:

## <a name="event-map-macros"></a>Макросы схемы событий

### <a name="event-map-declaration-and-demarcation"></a>Объявление события карты и определение границ

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|Объявляет, что карта событий будет использоваться в классе, чтобы сопоставить события к функциям обработки событий (необходимо использовать в объявлении класса).|
|[BEGIN_EVENT_MAP](#begin_event_map)|Начинается определение карта событий (необходимо использовать в реализации класса).|
|[END_EVENT_MAP](#end_event_map)|Завершает определение карта событий (необходимо использовать в реализации класса).|

### <a name="event-mapping-macros"></a>Макросы сопоставления событий

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|Указывает, какую функцию запуска событий будет срабатывать указанное событие.|
|[EVENT_CUSTOM_ID](#event_custom_id)|Указывает, какую функцию запуска событий будет срабатывать указанное событие с идентификатором указанного диспетчеризации.|

### <a name="message-mapping-macros"></a>Макросы сопоставления сообщений

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|Указывает пользовательскую команду элементом управления OLE.|
|[ON_STDOLEVERB](#on_stdoleverb)|Переопределяет сопоставление обычного глагола элемента управления OLE.|

##  <a name="declare_event_map"></a>  DECLARE_EVENT_MAP

Каждый `COleControl`-производный класс в программе может предоставить карта событий для указания событий, элемент управления будет срабатывать.

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Примечания

Используйте declare_event_map-макрос в конце объявления класса. Затем в CPP-файле, который определяет функции-члены класса, используйте begin_event_map-макрос, макрос записи для каждого события элемента управления и end_event_map-макрос для объявления в конец списка событий.

Дополнительные сведения о схемы событий см. в статье [элементы управления ActiveX: события](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="begin_event_map"></a>  BEGIN_EVENT_MAP

Начинается определение карта событий.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>Параметры

*theClass*  
Указывает, что имя класса элемента управления, событие которого сопоставления.

*baseClass*  
Указывает имя базового класса *theClass*.

### <a name="remarks"></a>Примечания

В файле реализации (CPP), который определяет функции-члены класса запуск карты событий с begin_event_map-макрос, а затем добавить макрос записи для каждого из событий и выполнить сопоставление событий с end_event_map-макрос.

Дополнительные сведения о схемы событий и begin_event_map-макрос см. в статье [элементы управления ActiveX: события](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

##  <a name="end_event_map"></a>  END_EVENT_MAP

Используйте end_event_map-макрос для завершения определения события карты.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="event_custom"></a>  EVENT_CUSTOM

Определяет запись событий карты для пользовательских событий.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>Параметры

*pszName*  
Имя события.

*pfnFire*  
Имя на запуск функции события.

*vtsParams*  
Разделенный пробелами список одной или нескольких констант, указав список параметров функции.

### <a name="remarks"></a>Примечания

*VtsParams* параметр является список с разделителями-пробелами значений из `VTS_` константы. Один или несколько из следующих значений, разделенных пробелами (не запятыми) Указывает список параметров функции. Пример:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

Указывает значение, а затем с помощью указателя на цвета список, содержащий 32-разрядное целое число, представляющее RGB `IFontDisp` интерфейс OLE-объекта шрифта.

`VTS_` Константы и их значение представлено следующим образом:

|Символ|Тип параметра|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|ВАЛЮТА|
|VTS_DATE|DATE|
|VTS_BSTR|**const** __char\*__|
|VTS_DISPATCH|LPDISPATCH|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|HANDLE|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_OPTEXCLUSIVE|OLE_OPTEXCLUSIVE|
|VTS_PICTURE|`IPictureDisp*`|
|VTS_TRISTATE|OLE_TRISTATE|
|VTS_XPOS_PIXELS|OLE_XPOS_PIXELS|
|VTS_YPOS_PIXELS|OLE_YPOS_PIXELS|
|VTS_XSIZE_PIXELS|OLE_XSIZE_PIXELS|
|VTS_YSIZE_PIXELS|OLE_YSIZE_PIXELS|
|TS_XPOS_HIMETRIC|OLE_XPOS_HIMETRIC|
|VTS_YPOS_HIMETRIC|OLE_YPOS_HIMETRIC|
|VTS_XSIZE_HIMETRIC|OLE_XSIZE_HIMETRIC|
|VTS_YSIZE_HIMETRIC|OLE_YSIZE_HIMETRIC|

> [!NOTE]
> Дополнительные variant константы определены для всех вариантов типов, за исключением VTS_FONT и VTS_PICTURE, которые обеспечивают указатель на константу данных variant. Эти константы, именуются с помощью `VTS_Pconstantname` соглашение. Например VTS_PCOLOR является указателем на vts_color-константа.

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="event_custom_id"></a>  EVENT_CUSTOM_ID

Определяет событие обработки функцией для пользовательского события, относящегося к идентификатор диспетчеризации, определяемое *dispid*.

```cpp
EVENT_CUSTOM_ID(
  pszName,
  dispid,
  pfnFire,
  vtsParams)
```

### <a name="parameters"></a>Параметры

*pszName*  
Имя события.

*Идентификатор DISPID*  
Идентификатор диспетчеризации, используемые элементом управления, при срабатывании события.

*pfnFire*  
Имя на запуск функции события.

*vtsParams*  
Переменный список параметров, передаваемые от контейнера элемента управления при возникновении этого события.

### <a name="remarks"></a>Примечания

*VtsParams* аргумент является список с разделителями-пробелами значений из `VTS_` константы. Один или несколько из следующих значений, разделенных пробелами, а не запятыми Указывает список параметров функции. Пример:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

Указывает значение, а затем с помощью указателя на цвета список, содержащий 32-разрядное целое число, представляющее RGB `IFontDisp` интерфейс OLE-объекта шрифта.

Список `VTS_` константы, см. в разделе [EVENT_CUSTOM](#event_custom).

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="on_oleverb"></a>  ON_OLEVERB

Этот макрос определяет элемент карты сообщений, которая сопоставляется с пользовательской командой функции-члена конкретного элемента управления.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*idsVerbName*<br/>
Идентификатор ресурса строки имени команды.

*memberFxn*<br/>
Функция вызывается платформой при вызове команды.

### <a name="remarks"></a>Примечания

Редактор ресурсов может использоваться для создания имен пользовательских команд, которые добавляются в таблицу строки.

Прототип функции для *memberFxn* является:

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

Значения *lpMsg*, *hWndParent*, и *lpRect* параметров берутся из соответствующих параметров `IOleObject::DoVerb` функция-член.

### <a name="requirements"></a>Требования

**Заголовок** afxole.h

## <a name="on_stdoleverb"></a>  ON_STDOLEVERB

Чтобы переопределить поведение по умолчанию из обычного глагола, используйте этот макрос.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>Параметры

*iVerb*  
Индекс обычного глагола для переопределения команды.

*memberFxn*  
Функция вызывается платформой при вызове команды.

### <a name="remarks"></a>Примечания

Индекс обычного глагола имеет вид `OLEIVERB_`, а затем действие. OLEIVERB_SHOW OLEIVERB_HIDE и OLEIVERB_UIACTIVATE приведены некоторые примеры стандартных команд.

См. в разделе [ON_OLEVERB](#on_oleverb) описание прототип функции для использования в качестве *memberFxn* параметра.


### <a name="requirements"></a>Требования

**Заголовок** afxole.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
