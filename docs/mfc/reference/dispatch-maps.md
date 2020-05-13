---
title: Схемы подготовки к отправке
ms.date: 06/20/2018
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 59dd8c7a7b0b930ffdb68fd96410fd73aeb02e81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365756"
---
# <a name="dispatch-maps"></a>Схемы подготовки к отправке

КОМПАНИЯ OLE Automation предоставляет способы вызова методов и доступа к свойствам в разных приложениях. Механизм, предоставляемый Библиотекой класса Microsoft Foundation для отправки этих запросов, представляет собой «карту отправки», которая определяет внутренние и внешние названия объектов функций и свойств, а также типы данных самих свойств и аргументов функции.

|План-карта макрос|Описание|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Объявляет, что карта отправки будет использоваться для разоблачения методов и свойств класса (должна использоваться в декларации класса).|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Начинается определение диспетчерской карты.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Завершает определение диспетчерской карты.|
|[DISP_FUNCTION](#disp_function)|Используется в диспетчерской карте для определения функции автоматизации OLE.|
|[DISP_PROPERTY](#disp_property)|Определяет свойство автоматизации OLE.|
|[DISP_PROPERTY_EX](#disp_property_ex)|Определяет свойство автоматизации OLE и называет функции Get and Set.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Определяет свойство автоматизации OLE с уведомлением.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Определяет свойство автоматизации OLE, которое принимает параметры и называет функции Get and Set.|
|[DISP_DEFVALUE](#disp_defvalue)|Делает существующее свойство значением объекта по умолчанию.|

## <a name="declare_dispatch_map"></a><a name="declare_dispatch_map"></a>DECLARE_DISPATCH_MAP

Если `CCmdTarget`класс, полученный в вашей программе, поддерживает OL Automation, этот класс должен предоставить карту отправки, чтобы раскрыть свои методы и свойства.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Remarks

Используйте DECLARE_DISPATCH_MAP макрос в конце объявления класса. Затем, в . Файл CPP, определяющий функции элемента для класса, использует BEGIN_DISPATCH_MAP макрос. Затем включите макрозаписи для каждого из открытых методов и свойств вашего класса (DISP_FUNCTION, DISP_PROPERTY и так далее). Наконец, используйте END_DISPATCH_MAP макрос.

> [!NOTE]
> Если вы объявляете членов после DECLARE_DISPATCH_MAP, вы должны указать новый тип доступа **(государственный,** **частный**или **защищенный)** для них.

Мастер приложений и мастера кода помогают создавать классы автоматизации и поддерживать карты отправки. Для получения дополнительной информации [Automation Servers](../../mfc/automation-servers.md)о картах отправки см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="begin_dispatch_map"></a><a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP

Объявляет определение вашей диспетчерской карты.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Упогоняет название класса, которому принадлежит эта карта отправки.

*базовыйКласс*<br/>
Упогоняет название базового класса *Class*.

### <a name="remarks"></a>Remarks

В файле реализации (.cpp), определяющем функции участника для вашего класса, запустите карту отправки с BEGIN_DISPATCH_MAP макросом, добавьте макрозаписи для каждой из ваших функций и свойств отправки и заполните карту отправки с END_DISPATCH_MAP макросом.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="end_dispatch_map"></a><a name="end_dispatch_map"></a>END_DISPATCH_MAP

Завершает определение карты отправки.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Remarks

Он должен использоваться в сочетании с BEGIN_DISPATCH_MAP.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_function"></a><a name="disp_function"></a>DISP_FUNCTION

Определяет функцию автоматизации OLE на карте отправки.

```cpp
DISP_FUNCTION(
    theClass,
    pszName,
    pfnMember,
    vtRetVal,
    vtsParams)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее название функции.

*pfnMember*<br/>
Название функции участника.

*vtRetVal*<br/>
Значение, определяющее тип возврата функции.

*vtsParams*<br/>
Разделенный пространством список одной или нескольких констант, определяющий список параметров функции.

### <a name="remarks"></a>Remarks

Аргумент *vtRetVal* имеет тип VARTYPE. Следующие возможные значения для этого `VARENUM` аргумента взяты из перечисления:

|Символ|Возвращаемый тип|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**Длинные**|
|VT_R4|**FLOAT**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|ЛПЧЛЯп|
|VT_ERROR|SCODE|
|VT_BOOL.|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPНеизвестный|

Аргумент *vtsParams* представляет собой разделенный пространством `VTS_*` список значений из констант. Одно или несколько из этих значений, разделенных пробелами (не запятыми), определяет список параметров функции. Например,

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

определяет список, содержащий короткий ряд, а затем указатель на короткий ряд.

Константы `VTS_` и их значения таковы:

|Символ|Тип параметра|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**Длинные**|
|VTS_R4|**FLOAT**|
|VTS_R8|**double**|
|VTS_CY|`const CY` или `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|ЛПЧЛЯп|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` или `VARIANT&`|
|VTS_UNKNOWN|LPНеизвестный|
|VTS_PI2|__Короткие\*__|
|VTS_PI4|__Длинные\*__|
|VTS_PR4|__FLOAT\*__|
|VTS_PR8|__double\*__|
|VTS_PCY|`CY*`|
|VTS_PDATE|`DATE*`|
|VTS_PBSTR|`BSTR*`|
|VTS_PDISPATCH|`LPDISPATCH*`|
|VTS_PSCODE|`SCODE*`|
|VTS_PBOOL|`BOOL*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_PUNKNOWN|`LPUNKNOWN*`|
|VTS_NONE|Без параметров|

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property"></a><a name="disp_property"></a>DISP_PROPERTY

Определяет свойство автоматизации OLE на карте отправки.

```cpp
DISP_PROPERTY(
    theClass,
    pszName,
    memberName,
    vtPropType)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее название объекта.

*Membername*<br/>
Имя переменной участника, в которой хранится свойство.

*vtPropType*<br/>
Значение, определяющее тип свойства.

### <a name="remarks"></a>Remarks

Аргумент *vtPropType* имеет тип **VARTYPE.** Возможные значения для этого аргумента взяты из перечисления VARENUM:

|Символ|Тип свойства|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**Длинные**|
|VT_R4|**FLOAT**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|ЛПЧЛЯп|
|VT_ERROR|SCODE|
|VT_BOOL.|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPНеизвестный|

При изменении свойства внешний клиент изменяет значение переменной участника, указанной *memberName;* никаких уведомлений об изменении.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_ex"></a><a name="disp_property_ex"></a>DISP_PROPERTY_EX

Определяет свойство автоматизации OLE и называет функции, используемые для получения, и устанавливает значение свойства на карте отправки.

```cpp
DISP_PROPERTY_EX(
    theClass,
    pszName,
    memberGet,
    memberSet,
    vtPropType)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее название объекта.

*memberGet*<br/>
Название функции участника, используемой для получения свойства.

*memberSet*<br/>
Название функции участника, используемой для установки свойства.

*vtPropType*<br/>
Значение, определяющее тип свойства.

### <a name="remarks"></a>Remarks

Функции *memberGet* и *memberSet* имеют подписи, определяемые аргументом *vtPropType.* Функция *memberGet* не требует никаких аргументов и возвращает значение типа, указанного *vtPropType.* Функция *memberSet* принимает аргумент типа, указанного *vtPropType* и ничего не возвращает.

Аргумент *vtPropType* имеет тип VARTYPE. Возможные значения для этого аргумента взяты из перечисления VARENUM. Список этих значений можно узнать *vtRetVal* в [DISP_FUNCTION](#disp_function)см. Обратите внимание, что VT_EMPTY, перечисленные в DISP_FUNCTION замечаниях, не допускается как тип данных свойств.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_notify"></a><a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY

Определяет свойство автоматизации OLE с уведомлением на карте отправки.

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    szExternalName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*szExternalName*<br/>
Внешнее название объекта.

*Membername*<br/>
Имя переменной участника, в которой хранится свойство.

*pfnAfterSet*<br/>
Название функции уведомления для *szExternalName*.

*vtPropType*<br/>
Значение, определяющее тип свойства.

### <a name="remarks"></a>Remarks

В отличие от свойств, определенных DISP_PROPERTY, свойство, определяемое DISP_PROPERTY_NOTIFY автоматически вызовет функцию, указанную *pfnAfterSet* при изменении свойства.

Аргумент *vtPropType* имеет тип VARTYPE. Возможные значения для этого аргумента взяты из перечисления VARENUM:

|Символ|Тип свойства|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**Длинные**|
|VT_R4|**FLOAT**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|ЛПЧЛЯп|
|VT_ERROR|SCODE|
|VT_BOOL.|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPНеизвестный|

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_param"></a><a name="disp_property_param"></a>DISP_PROPERTY_PARAM

Определяет свойство, доступ `Get` к `Set` нему с отдельными функциями и функциями-членами.

```cpp
DISP_PROPERTY_PARAM(
    theClass,
    pszExternalName,
    pfnGet,
    pfnSet,
    vtPropType,
    vtsParams)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszExternalName*<br/>
Внешнее название объекта.

*pfnGet*<br/>
Название функции участника, используемой для получения свойства.

*pfnSet*<br/>
Название функции участника, используемой для установки свойства.

*vtPropType*<br/>
Значение, определяющее тип свойства.

*vtsParams*<br/>
Строка пространственно-разделенных `VTS_*` типов параметров варианта, по одному для каждого параметра.

### <a name="remarks"></a>Remarks

В отличие от DISP_PROPERTY_EX макроса, этот макрос позволяет указать список параметров для свойства. Это полезно для реализации свойств, которые индексируются или параметрифицируются.

### <a name="example"></a>Пример

Рассмотрим следующую декларацию функций пользователя get и set, которые позволяют пользователю запрашивать определенную строку и столбец при доступе к свойству:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

Они соответствуют следующим макросу DISP_PROPERTY_PARAM на карте диспетчерской диспетчерской системы управления:

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

В качестве еще одного примера рассмотрим следующие функции получения и набора членов:

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

Они соответствуют следующим макросу DISP_PROPERTY_PARAM на карте диспетчерской диспетчерской системы управления:

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_defvalue"></a><a name="disp_defvalue"></a>DISP_DEFVALUE

Делает существующее свойство значением объекта по умолчанию.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее название свойства, представляющего "стоимость" объекта.

### <a name="remarks"></a>Remarks

Использование значения по умолчанию может упростить программирование объекта автоматизации для приложений Visual Basic.

Значение «значения по умолчанию» объекта — это свойство, которое извлекается или устанавливается, когда ссылка на объект не указывает свойство или функцию члена.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
