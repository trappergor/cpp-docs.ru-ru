---
title: Схемы подготовки к отправке
ms.date: 06/20/2018
f1_keywords:
- vc.mfc.macros.maps
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: 5ebedaa02a03bcc7802110977b96659dae45f174
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585085"
---
# <a name="dispatch-maps"></a>Схемы подготовки к отправке

OLE-автоматизации предоставляет способы для вызова методов и для доступа к свойствам в приложениях. Этот механизм, предоставляемый библиотеки Microsoft Foundation Class для диспетчеризации эти запросы – «диспетчерскую карту,» внутренние и внешние имена функций объектов и свойств, а также типы данных, непосредственно в свойствах и представляет собой аргументы функции.

|Макроса карты распределения|Описание|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Объявляет, что схема подготовки к отправке будет использоваться для предоставления класса методы и свойства, (необходимо использовать в объявлении класса).|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Начинается определение схема подготовки к отправке.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Завершает определение схема подготовки к отправке.|
|[DISP_FUNCTION](#disp_function)|Используется в диспетчерскую карту для определения функцию автоматизации OLE.|
|[DISP_PROPERTY](#disp_property)|Определяет свойство автоматизации OLE.|
|[DISP_PROPERTY_EX](#disp_property_ex)|Определяет свойство автоматизации OLE и имена функций Get и Set.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Определяет свойство автоматизации OLE с уведомлением.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Определяет свойства автоматизации OLE, который принимает параметры и имена функций Get и Set.|
|[DISP_DEFVALUE](#disp_defvalue)|Делает существующего свойства, значение по умолчанию объекта.|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

Если `CCmdTarget`-производный класс в программе поддерживает OLE-автоматизации, что класс должен предоставлять карту диспетчеризации для предоставления его методам и свойствам.

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Примечания

Используйте declare_dispatch_map-макрос в конце объявления класса. Затем в. CPP-файл, который определяет функции-члены класса, используйте begin_dispatch_map-макрос. Затем включите макрос записи для каждого из вашего класса предоставленные методы и свойства (DISP_FUNCTION DISP_PROPERTY и т. д.). Наконец используйте end_dispatch_map-макрос.

> [!NOTE]
> Если после DECLARE_DISPATCH_MAP объявляет никаких членов, необходимо указать новый тип доступа ( **открытый**, **частного**, или **защищенные**) для них.

Мастера мастер приложения и кода помогают в создании классов автоматизации и обслуживание схемы подготовки к отправке. Дополнительные сведения о схемы подготовки к отправке, см. в разделе [серверы автоматизации](../../mfc/automation-servers.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="begin_dispatch_map"></a>  BEGIN_DISPATCH_MAP

Объявляет определение карту диспетчеризации.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Задает имя класса, которому принадлежит эта карта распределения.

*baseClass*<br/>
Указывает имя базового класса *theClass*.

### <a name="remarks"></a>Примечания

В файле реализации (CPP), который определяет функции-члены класса начнем диспетчерскую карту с begin_dispatch_map-макрос, добавьте макрос записи для каждого диспетчеризации функций и свойств и завершения диспетчерскую карту с END_DISPATCH_ Макроса КАРТЫ.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

Завершает определение карту диспетчеризации.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Примечания

Он должен использоваться в сочетании с BEGIN_DISPATCH_MAP.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_function"></a>  DISP_FUNCTION

Определяет функцию автоматизации OLE, в диспетчерскую карту.

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
Внешнее имя функции.

*pfnMember*<br/>
Имя функции-члена.

*vtRetVal*<br/>
Значение, указывающее тип возвращаемого значения функции.

*vtsParams*<br/>
Разделенный пробелами список одной или нескольких констант, указав список параметров функции.

### <a name="remarks"></a>Примечания

*VtRetVal* аргумент имеет тип VARTYPE. Для этого аргумента следующие возможные значения берутся из `VARENUM` перечисления:

|Символ|Тип возвращаемого значения|
|------------|-----------------|
|ЗНАЧЕНИЕ VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

*VtsParams* аргумент является список с разделителями-пробелами значений из `VTS_*` константы. Один или несколько из следующих значений, разделенных пробелами (не запятыми) Указывает список параметров функции. Например, примененная к объекту директива

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

Указывает список, содержащий короткое целое число, а затем с помощью указателя в короткое целое число.

`VTS_` Константы и их значение представлено следующим образом:

|Символ|Тип параметра|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` или `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|LPDISPATCH|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` или `VARIANT&`|
|VTS_UNKNOWN|LPUNKNOWN|
|VTS_PI2|__короткий\*__|
|VTS_PI4|__Long\*__|
|VTS_PR4|__число с плавающей запятой\*__|
|VTS_PR8|__Double\*__|
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

## <a name="disp_property"></a>  DISP_PROPERTY

Определяет свойство автоматизации OLE, в диспетчерскую карту.

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
Внешнее имя свойства.

*Имя пользователя*<br/>
Имя переменной-члена, в котором хранится свойство.

*vtPropType*<br/>
Значение, указывающее тип свойства.

### <a name="remarks"></a>Примечания

*VtPropType* аргумент имеет тип **VARTYPE**. Возможные значения для этого аргумента берутся из перечисления VARENUM:

|Символ|Тип свойства|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

При изменении свойства, значение переменной-члена, заданные в внешнего клиента *memberName* изменении; нет уведомления об изменении.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_ex"></a>  DISP_PROPERTY_EX

Определяет свойство автоматизации OLE и имя функции, используемые для получения и задания значения свойства в диспетчерскую карту.

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
Внешнее имя свойства.

*memberGet*<br/>
Имя функции-члена, используемый для получения свойства.

*набор элементов*<br/>
Имя функции-члена, используемый для задания свойства.

*vtPropType*<br/>
Значение, указывающее тип свойства.

### <a name="remarks"></a>Примечания

*MemberGet* и *memberSet* функции имеют подписи, определяется *vtPropType* аргумент. *MemberGet* функция не принимает аргументы и возвращает значение типа, заданного параметром *vtPropType*. *MemberSet* функция принимает аргумент типа, заданного параметром *vtPropType* и не возвращает ничего.

*VtPropType* аргумент имеет тип VARTYPE. Возможные значения для этого аргумента берутся из перечисления VARENUM. Список этих значений, см. в разделе "Примечания" для *vtRetVal* параметр в [DISP_FUNCTION](#disp_function). Обратите внимание, что VT_EMPTY, перечисленные в примечаниях DISP_FUNCTION, запрещается использовать как тип данных свойства.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_notify"></a>  DISP_PROPERTY_NOTIFY

Определяет свойство автоматизации OLE с уведомлением в диспетчерскую карту.

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
Внешнее имя свойства.

*Имя пользователя*<br/>
Имя переменной-члена, в котором хранится свойство.

*pfnAfterSet*<br/>
Имя функции уведомления для *szExternalName*.

*vtPropType*<br/>
Значение, указывающее тип свойства.

### <a name="remarks"></a>Примечания

В отличие от свойства, определенные с DISP_PROPERTY, это свойство, определенное с помощью DISP_PROPERTY_NOTIFY автоматически вызывает функцию, указанную аргументом *pfnAfterSet* при изменении свойства.

*VtPropType* аргумент имеет тип VARTYPE. Возможные значения для этого аргумента берутся из перечисления VARENUM:

|Символ|Тип свойства|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|LPDISPATCH|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|LPUNKNOWN|

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_param"></a>  DISP_PROPERTY_PARAM

Определяет свойство с доступом с помощью отдельных `Get` и `Set` функций-членов.

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
Внешнее имя свойства.

*pfnGet*<br/>
Имя функции-члена, используемый для получения свойства.

*pfnSet*<br/>
Имя функции-члена, используемый для задания свойства.

*vtPropType*<br/>
Значение, указывающее тип свойства.

*vtsParams*<br/>
Строка с разделителями-пробелами `VTS_*` типы variant параметров, один для каждого параметра.

### <a name="remarks"></a>Примечания

В отличие от disp_property_ex-макрос этот макрос можно указать список параметров для свойства. Это полезно для реализации, которые индексируются или параметризованных свойств.

### <a name="example"></a>Пример

Рассмотрим следующее объявление get и набора функций, которые позволяют пользователю запрашивать указанной строке и столбце при доступе к свойству:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

Они соответствуют следующие disp_property_param-макрос в карте распределения элементов управления:

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

Еще один пример рассмотрим следующие get и набора функций:

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

Они соответствуют следующие disp_property_param-макрос в карте распределения элементов управления:

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_defvalue"></a>  DISP_DEFVALUE

Делает существующего свойства, значение по умолчанию объекта.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Параметры

*theClass*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя свойства, которое представляет «значение» объекта.

### <a name="remarks"></a>Примечания

Использование значения по умолчанию может сделать программирование более простой для приложений Visual Basic объект автоматизации.

«Значение по умолчанию» объекта — свойство, которое получении или задании, когда ссылка на объект не указывает функцию, свойства или элемента.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также

[Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)
