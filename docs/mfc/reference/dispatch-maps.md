---
title: Схемы подготовки к отправке
ms.date: 06/20/2018
helpviewer_keywords:
- dispatch maps [MFC], macros
- dispatch maps [MFC]
- dispatch map macros [MFC]
ms.assetid: bef9d08b-ad35-4c3a-99d8-04150c7c04e2
ms.openlocfilehash: f1afa95d7c20d54f2015255a7e4e0d7ad9ae9c2b
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2019
ms.locfileid: "68916512"
---
# <a name="dispatch-maps"></a>Схемы подготовки к отправке

OLE Automation предоставляет способы вызова методов и доступа к свойствам в разных приложениях. Механизм, предоставляемый библиотека Microsoft Foundation Class для диспетчеризации этих запросов, — это "схема диспетчеризации", которая обозначает внутренние и внешние имена функций и свойств объектов, а также типы данных самих свойств и аргументы функции.

|Отправить макрос с картой|Описание|
|-|-|
|[DECLARE_DISPATCH_MAP](#declare_dispatch_map)|Объявляет, что для предоставления методов и свойств класса (необходимо использовать в объявлении класса) диспетчер диспетчеризации будет использоваться.|
|[BEGIN_DISPATCH_MAP](#begin_dispatch_map)|Запускает определение схемы диспетчеризации.|
|[END_DISPATCH_MAP](#end_dispatch_map)|Завершает определение схемы диспетчеризации.|
|[DISP_FUNCTION](#disp_function)|Используется в схеме диспетчеризации для определения функции OLE-автоматизации.|
|[DISP_PROPERTY](#disp_property)|Определяет свойство OLE Automation.|
|[DISP_PROPERTY_EX](#disp_property_ex)|Определяет свойство OLE Automation и называет функции Get и Set.|
|[DISP_PROPERTY_NOTIFY](#disp_property_notify)|Определяет свойство OLE Automation с уведомлением.|
|[DISP_PROPERTY_PARAM](#disp_property_param)|Определяет свойство OLE Automation, которое принимает параметры и называет функции Get и Set.|
|[DISP_DEFVALUE](#disp_defvalue)|Делает существующее свойство значением по умолчанию для объекта.|

## <a name="declare_dispatch_map"></a>  DECLARE_DISPATCH_MAP

Если класс, производный от, в программе поддерживает OLE -автоматизацию,этотклассдолженпредоставлятькартудиспетчеризациидляпредоставлениясвоихметодовисвойств.`CCmdTarget`

```cpp
DECLARE_DISPATCH_MAP()
```

### <a name="remarks"></a>Примечания

Используйте макрос DECLARE_DISPATCH_MAP в конце объявления класса. Затем в. CPP файл, который определяет функции элементов для класса, используется макрос BEGIN_DISPATCH_MAP. Затем включите записи макросов для каждого из предоставленных методов класса и свойств (DISP_FUNCTION, DISP_PROPERTY и т. д.). Наконец, используйте макрос END_DISPATCH_MAP.

> [!NOTE]
> Если после DECLARE_DISPATCH_MAP объявляются члены, для них необходимо указать новый тип доступа ( **открытый**, **частный**или защищенный).

Мастер приложений и мастера кода помогают создавать классы автоматизации и поддерживать карты диспетчеризации. Дополнительные сведения об отправке карт см. в разделе [серверы автоматизации](../../mfc/automation-servers.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCAutomation#10](../../mfc/codesnippet/cpp/dispatch-maps_1.h)]

### <a name="requirements"></a>Требования

**Заголовок:** afxwin.h

## <a name="begin_dispatch_map"></a>BEGIN_DISPATCH_MAP

Объявляет определение схемы диспетчеризации.

```cpp
BEGIN_DISPATCH_MAP(theClass, baseClass)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Указывает имя класса, которому принадлежит эта схема диспетчеризации.

*baseClass*<br/>
Указывает имя базового класса для *секласс*.

### <a name="remarks"></a>Примечания

В файле реализации (. cpp), который определяет функции-члены для класса, запустите карту диспетчеризации с помощью макроса BEGIN_DISPATCH_MAP, добавьте записи макросов для каждой из функций и свойств диспетчеризации и завершите карту диспетчеризации с помощью END_DISPATCH_. Макрос MAP.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="end_dispatch_map"></a>  END_DISPATCH_MAP

Завершает определение схемы диспетчеризации.

```cpp
END_DISPATCH_MAP()
```

### <a name="remarks"></a>Примечания

Он должен использоваться совместно с BEGIN_DISPATCH_MAP.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_function"></a>DISP_FUNCTION

Определяет функцию OLE-автоматизации в сопоставлении диспетчеризации.

```cpp
DISP_FUNCTION(
    theClass,
    pszName,
    pfnMember,
    vtRetVal,
    vtsParams)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя функции.

*пфнмембер*<br/>
Имя функции члена.

*втретвал*<br/>
Значение типа, указывающее тип возвращаемого значения функции.

*втспарамс*<br/>
Список с разделителями-пробелами одной или нескольких констант, указывающих список параметров функции.

### <a name="remarks"></a>Примечания

Аргумент *втретвал* имеет тип VarType. Следующие возможные значения для этого аргумента взяты из `VARENUM` перечисления:

|Символ|Возвращаемый тип|
|------------|-----------------|
|VT_EMPTY|**void**|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|BSTR|
|VT_DISPATCH|ЛПДИСПАТЧ|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|ЛПУНКНОВН|

Аргумент *втспарамс* представляет собой разделенный пробелами список значений `VTS_*` констант. Одно или несколько из этих значений, разделенных пробелами (а не запятыми), задает список параметров функции. Например, примененная к объекту директива

[!code-cpp[NVC_MFCAutomation#14](../../mfc/codesnippet/cpp/dispatch-maps_2.cpp)]

Указывает список, содержащий короткое целое число, за которым следует указатель на короткое целое число.

Ниже `VTS_` приведены константы и их значения.

|Символ|Тип параметра|
|------------|--------------------|
|VTS_I2|**short**|
|VTS_I4|**long**|
|VTS_R4|**float**|
|VTS_R8|**double**|
|VTS_CY|`const CY` или `CY*`|
|VTS_DATE|DATE|
|VTS_BSTR|LPCSTR|
|VTS_DISPATCH|ЛПДИСПАТЧ|
|VTS_SCODE|SCODE|
|VTS_BOOL|BOOL|
|VTS_VARIANT|`const VARIANT*` или `VARIANT&`|
|VTS_UNKNOWN|ЛПУНКНОВН|
|VTS_PI2|__промежуток\*__|
|VTS_PI4|__поддерживаем\*__|
|VTS_PR4|__сделать\*__|
|VTS_PR8|__Дважды\*__|
|VTS_PCY|`CY*`|
|VTS_PDATE|`DATE*`|
|VTS_PBSTR|`BSTR*`|
|VTS_PDISPATCH|`LPDISPATCH*`|
|VTS_PSCODE|`SCODE*`|
|VTS_PBOOL|`BOOL*`|
|VTS_PVARIANT|`VARIANT*`|
|VTS_PUNKNOWN|`LPUNKNOWN*`|
|VTS_NONE|Нет параметров|

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property"></a>DISP_PROPERTY

Определяет свойство OLE-автоматизации в сопоставлении диспетчеризации.

```cpp
DISP_PROPERTY(
    theClass,
    pszName,
    memberName,
    vtPropType)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя свойства.

*memberName*<br/>
Имя переменной-члена, в которой хранится свойство.

*втпроптипе*<br/>
Значение типа, указывающее тип свойства.

### <a name="remarks"></a>Примечания

Аргумент *втпроптипе* имеет тип **VarType**. Возможные значения этого аргумента взяты из перечисления VARENUM:

|Символ|Тип свойства|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|ЛПДИСПАТЧ|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|ЛПУНКНОВН|

Когда внешний клиент изменяет свойство, значение переменной члена, заданной параметром *MemberName* , изменяется на. уведомления об изменении не изменяются.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_ex"></a>DISP_PROPERTY_EX

Определяет свойство OLE-автоматизации и присваивает имя функциям, используемым для получения и задания значения свойства в сопоставлении диспетчеризации.

```cpp
DISP_PROPERTY_EX(
    theClass,
    pszName,
    memberGet,
    memberSet,
    vtPropType)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя свойства.

*мембержет*<br/>
Имя функции члена, используемой для получения свойства.

*memberSet*<br/>
Имя функции члена, используемой для задания свойства.

*втпроптипе*<br/>
Значение типа, указывающее тип свойства.

### <a name="remarks"></a>Примечания

Функции *мембержет* и *member* имеют сигнатуры, определяемые аргументом *втпроптипе* . Функция *мембержет* не принимает аргументы и возвращает значение типа, заданного параметром *втпроптипе*. Функция *набора элементов* принимает аргумент типа, указанного параметром *втпроптипе* , и не возвращает ничего.

Аргумент *втпроптипе* имеет тип VarType. Возможные значения этого аргумента взяты из перечисления VARENUM. Список этих значений см. в разделе Примечания для параметра *втретвал* в [DISP_FUNCTION](#disp_function). Обратите внимание, что VT_EMPTY, перечисленные в комментариях DISP_FUNCTION, не разрешены в качестве типа данных свойства.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_notify"></a>DISP_PROPERTY_NOTIFY

Определяет свойство OLE-автоматизации с уведомлением в сопоставлении диспетчеризации.

```cpp
DISP_PROPERTY_NOTIFY(
    theClass,
    szExternalName,
    memberName,
    pfnAfterSet,
    vtPropType)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса.

*сзекстерналнаме*<br/>
Внешнее имя свойства.

*memberName*<br/>
Имя переменной-члена, в которой хранится свойство.

*пфнафтерсет*<br/>
Имя функции уведомления для *сзекстерналнаме*.

*втпроптипе*<br/>
Значение типа, указывающее тип свойства.

### <a name="remarks"></a>Примечания

В отличие от свойств, определенных с помощью DISP_PROPERTY, свойство, определенное с помощью DISP_PROPERTY_NOTIFY, будет автоматически вызывать функцию, указанную *пфнафтерсет* при изменении свойства.

Аргумент *втпроптипе* имеет тип VarType. Возможные значения этого аргумента взяты из перечисления VARENUM:

|Символ|Тип свойства|
|------------|-----------------------|
|VT_I2|**short**|
|VT_I4|**long**|
|VT_R4|**float**|
|VT_R8|**double**|
|VT_CY|CY|
|VT_DATE|DATE|
|VT_BSTR|`CString`|
|VT_DISPATCH|ЛПДИСПАТЧ|
|VT_ERROR|SCODE|
|VT_BOOL|BOOL|
|VT_VARIANT|VARIANT|
|VT_UNKNOWN|ЛПУНКНОВН|

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_property_param"></a>DISP_PROPERTY_PARAM

Определяет свойство, доступ к которому `Get` осуществляется `Set` с помощью отдельных функций-членов и.

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

*секласс*<br/>
Имя класса.

*псзекстерналнаме*<br/>
Внешнее имя свойства.

*пфнжет*<br/>
Имя функции члена, используемой для получения свойства.

*пфнсет*<br/>
Имя функции члена, используемой для задания свойства.

*втпроптипе*<br/>
Значение типа, указывающее тип свойства.

*втспарамс*<br/>
Строка типов параметров типа Variant, `VTS_*` разделенных пробелами, по одному для каждого параметра.

### <a name="remarks"></a>Примечания

В отличие от макроса DISP_PROPERTY_EX, этот макрос позволяет указать список параметров для свойства. Это полезно для реализации индексированных или параметризованных свойств.

### <a name="example"></a>Пример

Рассмотрим следующее объявление функций-членов Get и Set, которые позволяют пользователю запрашивать определенную строку и столбец при доступе к свойству:

[!code-cpp[NVC_MFCActiveXControl#9](../../mfc/codesnippet/cpp/dispatch-maps_3.h)]

Они соответствуют следующему макросу DISP_PROPERTY_PARAM в карте диспетчеризации элемента управления:

[!code-cpp[NVC_MFCActiveXControl#10](../../mfc/codesnippet/cpp/dispatch-maps_4.cpp)]

В качестве другого примера рассмотрим следующие функции элементов Get и Set:

[!code-cpp[NVC_MFCActiveXControl#11](../../mfc/codesnippet/cpp/dispatch-maps_5.h)]

Они соответствуют следующему макросу DISP_PROPERTY_PARAM в карте диспетчеризации элемента управления:

[!code-cpp[NVC_MFCActiveXControl#12](../../mfc/codesnippet/cpp/dispatch-maps_6.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="disp_defvalue"></a>DISP_DEFVALUE

Делает существующее свойство значением по умолчанию для объекта.

```cpp
DISP_DEFVALUE(theClass, pszName)
```

### <a name="parameters"></a>Параметры

*секласс*<br/>
Имя класса.

*pszName*<br/>
Внешнее имя свойства, представляющего "значение" объекта.

### <a name="remarks"></a>Примечания

Использование значения по умолчанию может упростить программирование объекта автоматизации для Visual Basic приложений.

Значение по умолчанию для объекта — это свойство, которое извлекается или задается, если ссылка на объект не указывает свойство или функцию-член.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="see-also"></a>См. также

[Макросы и глобальные](../../mfc/reference/mfc-macros-and-globals.md)
