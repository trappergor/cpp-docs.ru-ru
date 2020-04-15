---
title: Схемы событий
ms.date: 09/07/2019
helpviewer_keywords:
- event maps [MFC]
ms.assetid: 1ed53aee-bc53-43cd-834a-6fb935c0d29b
ms.openlocfilehash: c79d2fb1ac73947ddb13adcbd444ff7b5d50bdb4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365740"
---
# <a name="event-maps"></a>Схемы событий

Всякий раз, когда элемент управления желает уведомить свой контейнер о том, что произошло действие (определяемый разработчиком управления) (например, нажатие клавиши, щелчка мыши или изменение состояния элемента управления), он называет функцию стрельбы событиями. Эта функция уведомляет контейнер управления о том, что произошло некое важное действие при запуске связанного события.

Библиотека класса Фонда Майкрософт предлагает модель программирования, оптимизированную для событий стрельбы. В этой модели используются "карты событий", которые определяют, какие функции пожара, какие события для конкретного элемента управления. Карты событий содержат один макрос для каждого события. Например, карта событий, которая запускает событие акции Click, может выглядеть следующим образом:

[!code-cpp[NVC_MFCAxCtl#16](../../mfc/reference/codesnippet/cpp/event-maps_1.cpp)]

Макрос `EVENT_STOCK_CLICK` указывает на то, что элемент управления будет стрелять в событие кнопки акции каждый раз, когда он обнаруживает щелчком мыши. Более подробный список других событий фондовых акций смотрите в статье [ActiveX Controls: Events](../../mfc/mfc-activex-controls-events.md). Макросы также доступны для указания пользовательских событий.

Хотя макросы карты событий важны, вы обычно не вставляете их напрямую. Это связано с тем, что окно **Свойств** (в **классе View)** автоматически создает записи карты событий в исходных файлах, когда вы используете его для ассоциирования функций запуска событий с событиями. Каждый раз, когда вы хотите отсеить или добавить запись на карту событий, вы можете использовать окно **Properties.**

Для поддержки карт событий MFC предоставляет следующие макросы:

## <a name="event-map-macros"></a>Макросы Карты событий

### <a name="event-map-declaration-and-demarcation"></a>Декларация и демаркация карты событий

|||
|-|-|
|[DECLARE_EVENT_MAP](#declare_event_map)|Объявляет, что карта событий будет использоваться в классе для отображения событий с функциями, выжидая события (должна использоваться в объявлении класса).|
|[BEGIN_EVENT_MAP](#begin_event_map)|Начинается определение карты событий (должно использоваться в реализации класса).|
|[END_EVENT_MAP](#end_event_map)|Завершает определение карты событий (должно использоваться в реализации класса).|

### <a name="event-mapping-macros"></a>Картографические макросы событий

|||
|-|-|
|[EVENT_CUSTOM](#event_custom)|Указывает, какая функция стрельбы событиями будет стрелять по указанному событию.|
|[EVENT_CUSTOM_ID](#event_custom_id)|Указывает, какая функция стрельбы события будет стрелять указанное событие, с обозначенным идентификатором диспетчерской.|

### <a name="message-mapping-macros"></a>Картирование сообщений Макрос

|||
|-|-|
|[ON_OLEVERB](#on_oleverb)|Указывает пользовательский глагол, обрабатываемый управлением OLE.|
|[ON_STDOLEVERB](#on_stdoleverb)|Отменяет стандартное отображение глагола управления OLE.|

## <a name="declare_event_map"></a><a name="declare_event_map"></a>DECLARE_EVENT_MAP

Каждый `COleControl`класс, полученный в вашей программе, может предоставить карту событий, чтобы указать события, которые ваш элемент управления будет работать.

```cpp
DECLARE_EVENT_MAP()
```

### <a name="remarks"></a>Remarks

Используйте DECLARE_EVENT_MAP макрос в конце объявления класса. Затем в файле .cpp, определяющем функции участника для класса, используйте BEGIN_EVENT_MAP макрозаписи, макрозаписи для каждого из событий элемента управления и END_EVENT_MAP макрос а для объявления конца списка событий.

Для получения дополнительной информации о картах событий смотрите статью [ActiveX Controls: Events](../../mfc/mfc-activex-controls-events.md).

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="begin_event_map"></a><a name="begin_event_map"></a>BEGIN_EVENT_MAP

Начинается определение карты событий.

```cpp
BEGIN_EVENT_MAP(theClass,  baseClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Упогоняет название класса управления, карта событий которого это.

*базовыйКласс*<br/>
Упогоняет название базового класса *Класса*.

### <a name="remarks"></a>Remarks

В файле реализации (.cpp), определяющем функции участника для вашего класса, запустите карту событий с BEGIN_EVENT_MAP макросом, затем добавьте макрозаписи для каждого из событий и заполните карту событий END_EVENT_MAP макросом.

Для получения дополнительной информации о картах [ActiveX Controls: Events](../../mfc/mfc-activex-controls-events.md)событий и макросе BEGIN_EVENT_MAP см.

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="end_event_map"></a><a name="end_event_map"></a>END_EVENT_MAP

Используйте END_EVENT_MAP макрос, чтобы закончить определение карты событий.

```cpp
END_EVENT_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="event_custom"></a><a name="event_custom"></a>EVENT_CUSTOM

Определяет запись на карту событий для пользовательского события.

```cpp
EVENT_CUSTOM(pszName, pfnFire,  vtsParams)
```

### <a name="parameters"></a>Параметры

*pszName*<br/>
Имя события.

*pfnFire*<br/>
Название функции стрельбы события.

*vtsParams*<br/>
Разделенный пространством список одной или нескольких констант, определяющий список параметров функции.

### <a name="remarks"></a>Remarks

Параметр *vtsParams* представляет собой пространственно-отделенный список значений от `VTS_` констант. Одно или несколько из этих значений, разделенных пробелами (не запятыми), определяет список параметров функции. Пример:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

определяет список, содержащий 32-битный ряд, представляющий значение цвета RGB, а `IFontDisp` затем указатель на интерфейс объекта шрифта OLE.

Константы `VTS_` и их значения таковы:

|Символ|Тип параметра|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**Длинные**|
|VTS_R4|**FLOAT**|
|VTS_R8|**double**|
|VTS_COLOR|OLE_COLOR|
|VTS_CY|CURRENCY|
|VTS_DATE|DATE|
|VTS_BSTR|**Конст** __символ\* __|
|VTS_DISPATCH|ЛПЧЛЯп|
|VTS_FONT|`IFontDispatch*`|
|VTS_HANDLE|HANDLE|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_UNKNOWN|LPНеизвестный|
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
> Для всех типов вариантов определены дополнительные константы вариантов, за исключением VTS_FONT и VTS_PICTURE, которые обеспечивают указатель к константу данных варианта. Эти константы `VTS_Pconstantname` названы с помощью конвенции. Например, VTS_PCOLOR является указателем на константу VTS_COLOR.

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="event_custom_id"></a><a name="event_custom_id"></a>EVENT_CUSTOM_ID

Определяет функцию стрельбы события для пользовательского события, принадлежащего идентификатору отправки, указанному *dispid.*

```cpp
EVENT_CUSTOM_ID(
    pszName,
    dispid,
    pfnFire,
    vtsParams)
```

### <a name="parameters"></a>Параметры

*pszName*<br/>
Имя события.

*Dispid*<br/>
Идентификатор отправки, используемый элементом управления при запуске события.

*pfnFire*<br/>
Название функции стрельбы события.

*vtsParams*<br/>
Переменный список параметров, передаваемых в контейнер управления при сражени события.

### <a name="remarks"></a>Remarks

Аргумент *vtsParams* представляет собой разделенный пространством `VTS_` список значений из констант. Одно или несколько из этих значений, разделенных пробелами, а не запятыми, определяет список параметров функции. Пример:

[!code-cpp[NVC_MFCActiveXControl#13](../../mfc/codesnippet/cpp/event-maps_2.cpp)]

определяет список, содержащий 32-битный ряд, представляющий значение цвета RGB, а `IFontDisp` затем указатель на интерфейс объекта шрифта OLE.

Список `VTS_` констант читайте [EVENT_CUSTOM.](#event_custom)

### <a name="requirements"></a>Требования

**Заголовок** afxctl.h

## <a name="on_oleverb"></a><a name="on_oleverb"></a>ON_OLEVERB

Этот макрос определяет запись карты сообщений, которая отображает пользовательский глагол к определенной функции элемента управления.

```cpp
ON_OLEVERB(idsVerbName,  memberFxn)
```

### <a name="parameters"></a>Параметры

*idsVerbName*<br/>
Идентификатор ресурса строки имени глагола.

*memberFxn*<br/>
Функция, вызванная фреймворкой при вызове глагола.

### <a name="remarks"></a>Remarks

Редактор ресурсов может использоваться для создания пользовательских имен глаголов, которые добавляются в таблицу строк.

Прототип функции для *memberFxn:*

```cpp
BOOL memberFxn(
   LPMSG    lpMsg,
   HWND     hWndParent,
   LPCRECT  lpRect);
```

Значения параметров *lpMsg,* *hWndParent*и *lpRect* взяты из соответствующих параметров функции `IOleObject::DoVerb` члена.

### <a name="requirements"></a>Требования

**Заголовок** afxole.h

## <a name="on_stdoleverb"></a><a name="on_stdoleverb"></a>ON_STDOLEVERB

Используйте этот макрос, чтобы переопределить поведение стандартного глагола по умолчанию.

```cpp
ON_STDOLEVERB(iVerb, memberFxn)
```

### <a name="parameters"></a>Параметры

*iVerb*<br/>
Стандартный глагол для переопределяетого глагола.

*memberFxn*<br/>
Функция, вызванная фреймворкой при вызове глагола.

### <a name="remarks"></a>Remarks

Стандартный глагол индекс `OLEIVERB_`формы, а затем действие. OLEIVERB_SHOW, OLEIVERB_HIDE и OLEIVERB_UIACTIVATE являются примерами стандартных глаголов.

См [ON_OLEVERB](#on_oleverb) для описания прототипа функции, который будет использоваться в качестве параметра *memberFxn.*

### <a name="requirements"></a>Требования

**Заголовок** afxole.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
