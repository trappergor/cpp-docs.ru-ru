---
title: Службы модели объекта во время выполнения
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: f8b891467d91d0c945b6c59c90dbc49fd7cbcb30
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2020
ms.locfileid: "78855364"
---
# <a name="run-time-object-model-services"></a>Службы модели объекта во время выполнения

Классы [CObject](../../mfc/reference/cobject-class.md) и [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) инкапсулируют несколько служб объектов, включая доступ к сведениям о классе времени выполнения, сериализации и динамическому созданию объектов. Все классы, производные от `CObject`, наследуют эту функциональность.

Доступ к сведениям о классе времени выполнения позволяет определить сведения о классе объекта во время выполнения. Возможность определить класс объекта во время выполнения полезна, если требуется дополнительное определение типа аргументов функции и когда необходимо написать специальный код на основе класса объекта. Сведения о классе времени выполнения не поддерживаются непосредственно C++ языком.

Сериализация — это процесс записи или считывания содержимого объекта в файл или из него. Можно использовать сериализацию для хранения содержимого объекта даже после выхода из приложения. Затем объект может быть считан из файла при перезапуске приложения. Такие объекты данных называются «постоянными».

Динамическое создание объектов позволяет создать объект указанного класса во время выполнения. Например, объекты Document, View и Frame должны поддерживать динамическое создание, так как платформа должна создавать их динамически.

В следующей таблице перечислены макросы MFC, поддерживающие сведения о классе времени выполнения, сериализацию и динамическое создание.

Дополнительные сведения об этих службах объектов времени выполнения и сериализации см. в статье [класс CObject: доступ к сведениям о классе времени выполнения](../../mfc/accessing-run-time-class-information.md).

### <a name="run-time-object-model-services-macros"></a>Макросы служб объектной модели времени выполнения

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|Предоставляет доступ к сведениям о классе времени выполнения (необходимо использовать в объявлении класса).|
|[DECLARE_DYNCREATE](#declare_dyncreate)|Обеспечивает динамическое создание и доступ к сведениям о классе времени выполнения (необходимо использовать в объявлении класса).|
|[DECLARE_SERIAL](#declare_serial)|Обеспечивает сериализацию и доступ к сведениям о классе времени выполнения (необходимо использовать в объявлении класса).|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Предоставляет доступ к сведениям о классе времени выполнения (должен использоваться в реализации класса).|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Обеспечивает динамическое создание и доступ к сведениям времени выполнения (необходимо использовать в реализации класса).|
|[IMPLEMENT_SERIAL](#implement_serial)|Разрешает сериализацию и доступ к сведениям о классе времени выполнения (необходимо использовать в реализации класса).|
|[RUNTIME_CLASS](#runtime_class)|Возвращает структуру `CRuntimeClass`, соответствующую именованному классу.|

OLE часто требует динамического создания объектов во время выполнения. Например, приложение OLE-сервера должно иметь возможность динамически создавать объекты OLE в ответ на запрос от клиента. Аналогичным образом сервер автоматизации должен иметь возможность создавать элементы в ответ на запросы от клиентов автоматизации.

Библиотека Microsoft Foundation Class предоставляет два макроса, характерные для OLE.

### <a name="dynamic-creation-of-ole-objects"></a>Динамическое создание объектов OLE

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Определяет, реализует ли библиотека общих элементов управления указанный API.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Определяет, реализует ли библиотека общих элементов управления указанный API.|
|[DECLARE_OLECREATE](#declare_olecreate)|Позволяет создавать объекты с помощью OLE-автоматизации.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Объявляет функции членов класса Control `GetUserTypeNameID` и `GetMiscStatus`.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|Объявляет, что элемент управления OLE предоставляет список страниц свойств для вывода его свойств.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Позволяет создавать объекты в системе OLE.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Реализует функции членов класса Control `GetUserTypeNameID` и `GetMiscStatus`.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Этот макрос или [IMPLEMENT_OLECREATE](#implement_olecreate) должны присутствовать в файле реализации для любого класса, использующего `DECLARE_OLECREATE`. |

## <a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS

Определяет, реализует ли библиотека общих элементов управления указанный API.

### <a name="syntax"></a>Синтаксис

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>Параметры

*proc*<br/>
Указатель на строку, завершающуюся нулем, содержащую имя функции, или задает порядковое значение функции. Если этот параметр является порядковым значением, он должен находиться в слове нижнего порядка; слово с высоким порядковым значением должно быть равно нулю. Этот параметр должен быть в Юникоде.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы определить, является ли библиотека Common Controls функцией, заданной *процедурой* (вместо вызова [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress).

### <a name="requirements"></a>Требования

afxcomctl32. h, afxcomctl32. inl

## <a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2

Определяет, реализует ли библиотека Common Controls указанный API (это версия Юникода [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)).

### <a name="syntax"></a>Синтаксис

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>Параметры

*proc*<br/>
Указатель на строку, завершающуюся нулем, содержащую имя функции, или задает порядковое значение функции. Если этот параметр является порядковым значением, он должен находиться в слове нижнего порядка; слово с высоким порядковым значением должно быть равно нулю. Этот параметр должен быть в Юникоде.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы определить, является ли библиотека Common Controls функцией, заданной *процедурой* (вместо вызова [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress). Этот макрос является версией AFX_COMCTL32_IF_EXISTS в Юникоде.

### <a name="requirements"></a>Требования

afxcomctl32. h, afxcomctl32. inl

##  <a name="declare_dynamic"></a>DECLARE_DYNAMIC

Добавляет возможность доступа к сведениям времени выполнения о классе объекта при создании производного класса от `CObject`.

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Remarks

Добавьте DECLARE_DYNAMIC макрос в модуль header (. h) для класса, а затем включите этот модуль во все cpp-модули, которым требуется доступ к объектам этого класса.

При использовании DECLARE_ динамических и IMPLEMENT_DYNAMICных макросов, как описано выше, для определения класса объектов во время выполнения можно использовать макрос RUNTIME_CLASS и функцию `CObject::IsKindOf`.

Если в объявление класса входит DECLARE_DYNAMIC, то IMPLEMENT_DYNAMIC необходимо включать в реализацию класса.

Дополнительные сведения о макросе DECLARE_DYNAMIC см. в [разделах о классах CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

См. пример для [IMPLEMENT_DYNAMIC](#implement_dynamic).

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="declare_dyncreate"></a>DECLARE_DYNCREATE

Позволяет динамически создавать объекты производных от `CObject`классов во время выполнения.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Remarks

Платформа использует эту возможность для динамического создания новых объектов. Например, новое представление, созданное при открытии нового документа. Классы документов, представлений и фреймов должны поддерживать динамическое создание, так как платформа должна создавать их динамически.

Добавьте макрос DECLARE_DYNCREATE в модуль h для класса, а затем включите этот модуль во все cpp модули, которым требуется доступ к объектам этого класса.

Если в объявление класса входит DECLARE_DYNCREATE, то IMPLEMENT_DYNCREATE необходимо включать в реализацию класса.

Дополнительные сведения о макросе DECLARE_DYNCREATE см. в [разделах о классах CObject](../../mfc/using-cobject.md).

> [!NOTE]
>  Макрос DECLARE_DYNCREATE включает все функции DECLARE_DYNAMIC.

### <a name="example"></a>Пример

См. пример для [IMPLEMENT_DYNCREATE](#implement_dyncreate).

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="declare_olectltype"></a>DECLARE_OLECTLTYPE

Объявляет функции членов класса Control `GetUserTypeNameID` и `GetMiscStatus`.

### <a name="syntax"></a>Синтаксис

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления.

### <a name="remarks"></a>Remarks

`GetUserTypeNameID` и `GetMiscStatus` являются чистыми виртуальными функциями, объявленными в `COleControl`. Так как эти функции являются чисто виртуальными, они должны быть переопределены в классе элемента управления. В дополнение к DECLARE_OLECTLTYPE необходимо добавить макрос IMPLEMENT_OLECTLTYPE в объявление класса элемента управления.

### <a name="requirements"></a>Требования

**Заголовок:** afxctl. h

## <a name="declare_proppageids"></a>DECLARE_PROPPAGEIDS

Объявляет, что элемент управления OLE предоставляет список страниц свойств для вывода его свойств.

### <a name="syntax"></a>Синтаксис

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления, которому принадлежат страницы свойств.

### <a name="remarks"></a>Remarks

Используйте макрос `DECLARE_PROPPAGEIDS` в конце объявления класса. Затем в cpp-файле, который определяет функции-члены для класса, используйте макрос `BEGIN_PROPPAGEIDS`, записи макросов для каждой страницы свойств элемента управления и макрос `END_PROPPAGEIDS`, чтобы объявить конец списка страниц свойств.

Дополнительные сведения о страницах свойств см. в статье [элементы управления ActiveX: страницы свойств](../mfc-activex-controls-property-pages.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxctl. h

##  <a name="declare_serial"></a>DECLARE_SERIAL

Создает код C++ заголовка, необходимый для класса, производного от `CObject`, который можно сериализовать.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Remarks

Сериализация — это процесс записи или чтения содержимого объекта в файл и из него.

Используйте макрос DECLARE_SERIAL в модуле h, а затем включите этот модуль во все cpp модули, которым требуется доступ к объектам этого класса.

Если в объявление класса входит DECLARE_SERIAL, то IMPLEMENT_SERIAL необходимо включать в реализацию класса.

Макрос DECLARE_SERIAL включает все функции DECLARE_DYNAMIC и DECLARE_DYNCREATE.

Чтобы автоматически экспортировать оператор извлечения `CArchive` для классов, использующих макросы DECLARE_SERIAL и IMPLEMENT_SERIAL, можно использовать макрос AFX_API. Скобки объявления класса (расположенные в h-файле) со следующим кодом:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Дополнительные сведения о макросе DECLARE_SERIAL см. в [разделах о классах CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC

Создает C++ код, необходимый для динамического производного от `CObject`класса с доступом во время выполнения к имени класса и его положению в иерархии.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*base_class_name*<br/>
Имя базового класса.

### <a name="remarks"></a>Remarks

Используйте макрос IMPLEMENT_DYNAMIC в модуле. cpp, а затем свяжите полученный объектный код только один раз.

Дополнительные сведения см. в [разделах о классах CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE

Позволяет динамически создавать объекты производных от `CObject`классов во время выполнения при использовании с макросом DECLARE_DYNCREATE.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*base_class_name*<br/>
Фактическое имя базового класса.

### <a name="remarks"></a>Remarks

Платформа использует эту возможность для динамического создания новых объектов, например при считывании объекта с диска во время сериализации. Добавьте IMPLEMENT_DYNCREATE макрос в файл реализации класса. Дополнительные сведения см. в [разделах о классах CObject](../../mfc/using-cobject.md).

При использовании макросов DECLARE_DYNCREATE и IMPLEMENT_DYNCREATE можно использовать макрос RUNTIME_CLASS и функцию члена `CObject::IsKindOf`, чтобы определить класс объектов во время выполнения.

Если в объявление класса входит DECLARE_DYNCREATE, то IMPLEMENT_DYNCREATE необходимо включать в реализацию класса.

Обратите внимание, что это определение макроса вызовет конструктор по умолчанию для класса. Если нетривиальный конструктор явно реализуется классом, он также должен явно реализовывать конструктор по умолчанию. Конструктор по умолчанию можно добавить в **закрытые** или **защищенные** разделы члена класса, чтобы предотвратить его вызов извне реализации класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS

Этот макрос или [IMPLEMENT_OLECREATE](#implement_olecreate) должны присутствовать в файле реализации для любого класса, использующего DECLARE_OLECREATE.

### <a name="syntax"></a>Синтаксис

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*external_name*<br/>
Имя объекта, доступное другим приложениям (заключенное в кавычки).

*нфлагс*<br/>
Содержит один или несколько следующих флагов:

   - `afxRegInsertable` позволяет элементу управления отображаться в диалоговом окне «Вставка объекта» для объектов OLE.
   - `afxRegApartmentThreading` задает для потоковой модели в реестре значение ThreadingModel = апартамент.
   - `afxRegFreeThreading` задает для модели потоков в реестре значение ThreadingModel = Free.

         You can combine the two flags `afxRegApartmentThreading` and `afxRegFreeThreading` to set ThreadingModel=Both. See [InprocServer32](/windows/win32/com/inprocserver32) in the Windows SDK for more information on threading model registration.

компоненты *l*, *W1*, *W2*, *B1*, *B2*, *B3*, *B4*, *B5*, *B6*, *B7*, *B8* класса CLSID.

### <a name="remarks"></a>Remarks

> [!NOTE]
>  При использовании IMPLEMENT_OLECREATE_FLAGS можно указать, какую модель потоков поддерживает объект, с помощью параметра *нфлагс* . Если требуется поддержка только модели с одним треадинг, используйте IMPLEMENT_OLECREATE.

Внешнее имя — это идентификатор, предоставляемый другим приложениям. Клиентские приложения используют внешнее имя для запроса объекта этого класса с сервера автоматизации.

Идентификатор класса OLE — это уникальный 128-разрядный идентификатор объекта. Он состоит из одного **длинного**, **двух слов**s и восьми **байт**, представленных *l*, *W1*, *W2*и *B1* через *B8* в описании синтаксиса. Мастер приложений и мастера кода при необходимости создают уникальные идентификаторы классов OLE.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="implement_olectltype"></a>IMPLEMENT_OLECTLTYPE

Реализует функции членов класса Control `GetUserTypeNameID` и `GetMiscStatus`.

### <a name="syntax"></a>Синтаксис

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Имя класса элемента управления.

*идсусертипенаме*<br/>
Идентификатор ресурса строки, содержащей внешнее имя элемента управления.

*дволемиск*<br/>
Перечисление, содержащее один или несколько флагов. Дополнительные сведения об этом перечислении см. в разделе [олемиск](/windows/win32/api/oleidl/ne-oleidl-olemisc) в Windows SDK.

### <a name="remarks"></a>Remarks

В дополнение к IMPLEMENT_OLECTLTYPE необходимо добавить макрос DECLARE_OLECTLTYPE в объявление класса элемента управления.

Функция члена `GetUserTypeNameID` возвращает строку ресурса, определяющую класс элемента управления. `GetMiscStatus` возвращает биты ОЛЕМИСК для элемента управления. Это перечисление задает коллекцию параметров, описывающих различные характеристики элемента управления. Полное описание параметров ОЛЕМИСК см. в разделе [олемиск](/windows/win32/api/oleidl/ne-oleidl-olemisc) в Windows SDK.

> [!NOTE]
>  Параметры по умолчанию, используемые Контролвизард ActiveX,: OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE и OLEMISC_RECOMPOSEONRESIZE.

### <a name="requirements"></a>Требования

**Заголовок:** afxctl. h

##  <a name="implement_serial"></a>IMPLEMENT_SERIAL

Создает C++ код, необходимый для динамического производного от `CObject`класса с доступом во время выполнения к имени класса и его положению в иерархии.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*base_class_name*<br/>
Имя базового класса.

*всчема*<br/>
Значение типа UINT "номер версии", которое будет закодировано в архиве, чтобы позволить десериализовать программу для обнаружения и обработке данных, созданных в предыдущих версиях программ. Номер схемы класса не должен быть равен-1.

### <a name="remarks"></a>Remarks

Используйте макрос IMPLEMENT_SERIAL в модуле. cpp; затем свяжите полученный объектный код только один раз.

Чтобы автоматически экспортировать оператор извлечения `CArchive` для классов, использующих макросы DECLARE_SERIAL и IMPLEMENT_SERIAL, можно использовать макрос AFX_API. Скобки объявления класса (расположенные в h-файле) со следующим кодом:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Дополнительные сведения см. в [статьях о классе CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="runtime_class"></a>RUNTIME_CLASS

Возвращает структуру класса времени выполнения из имени C++ класса.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса (не заключено в кавычки).

### <a name="remarks"></a>Remarks

RUNTIME_CLASS возвращает указатель на структуру [крунтимекласс](../../mfc/reference/cruntimeclass-structure.md) для класса, заданного *class_name*. Только классы, производные от `CObject`, объявленные с DECLARE_DYNAMIC, DECLARE_DYNCREATE или DECLARE_SERIAL, будут возвращать указатели на структуру `CRuntimeClass`.

Дополнительные сведения см. в [разделах о классах CObject](../../mfc/using-cobject.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="declare_olecreate"></a>DECLARE_OLECREATE

Позволяет создавать объекты производных от `CCmdTarget`классов с помощью OLE-автоматизации.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

### <a name="remarks"></a>Remarks

Этот макрос позволяет другим приложениям с поддержкой OLE создавать объекты этого типа.

Добавьте макрос DECLARE_OLECREATE в модуль h для класса, а затем включите этот модуль во все cpp модули, которым требуется доступ к объектам этого класса.

Если в объявление класса входит DECLARE_OLECREATE, то IMPLEMENT_OLECREATE необходимо включать в реализацию класса. Объявление класса, использующее DECLARE_OLECREATE, должно также использовать DECLARE_DYNCREATE или DECLARE_SERIAL.

### <a name="requirements"></a>Требования

**Заголовок**: афксдисп. h

##  <a name="implement_olecreate"></a>IMPLEMENT_OLECREATE

Этот макрос или [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) должны присутствовать в файле реализации для любого класса, использующего `DECLARE_OLECREATE`.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое имя класса.

*external_name*<br/>
Имя объекта, доступное другим приложениям (заключенное в кавычки).

компоненты *l*, *W1*, *W2*, *B1*, *B2*, *B3*, *B4*, *B5*, *B6*, *B7*, *B8* класса CLSID.

### <a name="remarks"></a>Remarks

> [!NOTE]
>  При использовании IMPLEMENT_OLECREATE по умолчанию поддерживается только одна потоковая модель. При использовании IMPLEMENT_OLECREATE_FLAGS можно указать, какую модель потоков поддерживает объект, с помощью параметра *нфлагс* .

Внешнее имя — это идентификатор, предоставляемый другим приложениям. Клиентские приложения используют внешнее имя для запроса объекта этого класса с сервера автоматизации.

Идентификатор класса OLE — это уникальный 128-разрядный идентификатор объекта. Он состоит из одного **длинного**, **двух слов**s и восьми **байт**, представленных *l*, *W1*, *W2*и *B1* через *B8* в описании синтаксиса. Мастер приложений и мастера кода при необходимости создают уникальные идентификаторы классов OLE.

### <a name="requirements"></a>Требования

**Заголовок**: афксдисп. h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные](mfc-macros-and-globals.md)<br/>
[Изоляция библиотеки общих элементов управления MFC](../isolation-of-the-mfc-common-controls-library.md)<br/>
[Ключ CLSID](/windows/win32/com/clsid-key-hklm)
