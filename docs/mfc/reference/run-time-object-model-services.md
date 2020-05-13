---
title: Службы модели объекта во время выполнения
ms.date: 03/27/2019
helpviewer_keywords:
- run-time object model services macros
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
ms.openlocfilehash: f1cefdad368ebcd006dcb4ecf653247147f36d03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372943"
---
# <a name="run-time-object-model-services"></a>Службы модели объекта во время выполнения

Классы [CObject](../../mfc/reference/cobject-class.md) и [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) инкапсулируют несколько объектов служб, включая доступ к информации о классе времени выполнения, сериализацию и создание динамических объектов. Все классы, `CObject` полученные из наследуют эту функциональность.

Доступ к информации о классе времени выполнения позволяет определить информацию о классе объекта во время выполнения. Возможность определения класса объекта во время выполнения полезна, когда требуется дополнительная проверка типов функциональных аргументов и когда необходимо написать специальный код на основе класса объекта. Информация о забеге не поддерживается непосредственно языком СЗ.

Сериализация — это процесс написания или чтения содержимого объекта в файл или из нее. Сериализация может использоваться для хранения содержимого объекта даже после выхода приложения. Объект может быть прочитан из файла при перезапущени приложении. Такие объекты данных считаются "постоянными".

Создание динамического объекта позволяет создать объект заданного класса во время выполнения. Например, объекты документов, представления и кадра должны поддерживать динамическое создание, поскольку инфраструктуре необходимо создать их динамически.

В следующей таблице перечислены макросы MFC, поддерживающие информацию о классе времени выполнения, сериализацию и создание динамических данных.

Для получения дополнительной информации об этих службах объектов и сериализации в течение выполнения можно ознакомиться в статье [CObject Class: Accessing Run-Time Class Information](../../mfc/accessing-run-time-class-information.md).

### <a name="run-time-object-model-services-macros"></a>Выполнить-время объект модели служб макрос

|||
|-|-|
|[DECLARE_DYNAMIC](#declare_dynamic)|Обеспечивает доступ к информации о классе времени выполнения (должна использоваться в декларации класса).|
|[DECLARE_DYNCREATE](#declare_dyncreate)|Обеспечивает динамическое создание и доступ к информации о классе времени выполнения (должна использоваться в декларации класса).|
|[DECLARE_SERIAL](#declare_serial)|Позволяет сериализацию и доступ к информации о классе времени выполнения (должна использоваться в декларации класса).|
|[IMPLEMENT_DYNAMIC](#implement_dynamic)|Обеспечивает доступ к информации о классе времени выполнения (должна использоваться в реализации класса).|
|[IMPLEMENT_DYNCREATE](#implement_dyncreate)|Обеспечивает динамическое создание и доступ к информации о времени выполнения (должна использоваться в реализации класса).|
|[IMPLEMENT_SERIAL](#implement_serial)|Разрешает сериализацию и доступ к информации о классе времени выполнения (должны использоваться в реализации класса).|
|[RUNTIME_CLASS](#runtime_class)|Возвращает `CRuntimeClass` структуру, соответствующую названному классу.|

OLE часто требует динамического создания объектов во время выполнения. Например, серверное приложение OLE должно быть в состоянии динамически создавать элементы OLE в ответ на запрос клиента. Аналогичным образом, сервер автоматизации должен быть в состоянии создавать элементы в ответ на запросы клиентов автоматизации.

Библиотека класса Фонда Майкрософт предоставляет два макроса, специфичных для OLE.

### <a name="dynamic-creation-of-ole-objects"></a>Динамическое создание объектов OLE

|||
|-|-|
|[AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)|Определяет, реализует ли библиотека Common Controls указанный API.|
|[AFX_COMCTL32_IF_EXISTS2](#afx_comctl32_if_exists2)|Определяет, реализует ли библиотека Common Controls указанный API.|
|[DECLARE_OLECREATE](#declare_olecreate)|Позволяет создавать объекты с помощью автоматизации OLE.|
|[DECLARE_OLECTLTYPE](#declare_olectltype)|Объявляет `GetUserTypeNameID` функции `GetMiscStatus` и функции элемента вашего класса управления.|
|[DECLARE_PROPPAGEIDS](#declare_proppageids)|Заявляет, что элемент управления OLE предоставляет список страниц свойств для отображения его свойств.|
|[IMPLEMENT_OLECREATE](#implement_olecreate)|Позволяет создавать объекты системой OLE.|
|[IMPLEMENT_OLECTLTYPE](#implement_olectltype)|Реализует `GetUserTypeNameID` функции `GetMiscStatus` элемента управления и функций элемента.|
|[IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags)|Либо этот макрос, либо [IMPLEMENT_OLECREATE](#implement_olecreate) должны отображаться `DECLARE_OLECREATE`в файле реализации для любого класса, который использует. |

## <a name="afx_comctl32_if_exists"></a><a name="afx_comctl32_if_exists"></a>AFX_COMCTL32_IF_EXISTS

Определяет, реализует ли библиотека Common Controls указанный API.

### <a name="syntax"></a>Синтаксис

```
AFX_COMCTL32_IF_EXISTS(  proc );
```

### <a name="parameters"></a>Параметры

*proc*<br/>
Указатель на нулевую строку, содержащую имя функции, или опознавательный значение функции. Если этот параметр является порядковым значением, он должен быть в слове с низким уровнем порядка; слово высокого порядка должно быть нулевым. Этот параметр должен быть в Unicode.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы определить, является ли библиотека Common Controls функцией, указанной *proc* (вместо вызова [GetProcAddress.](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress)

### <a name="requirements"></a>Требования

afxcomctl32.h, afxcomctl32.inl

## <a name="afx_comctl32_if_exists2"></a><a name="afx_comctl32_if_exists2"></a>AFX_COMCTL32_IF_EXISTS2

Определяет, реализует ли библиотека Common Controls указанный API (это версия [AFX_COMCTL32_IF_EXISTS](#afx_comctl32_if_exists)Unicode).

### <a name="syntax"></a>Синтаксис

```
AFX_COMCTL32_IF_EXISTS2( proc );
```

### <a name="parameters"></a>Параметры

*proc*<br/>
Указатель на нулевую строку, содержащую имя функции, или опознавательный значение функции. Если этот параметр является порядковым значением, он должен быть в слове с низким уровнем порядка; слово высокого порядка должно быть нулевым. Этот параметр должен быть в Unicode.

### <a name="remarks"></a>Remarks

Используйте этот макрос, чтобы определить, является ли библиотека Common Controls функцией, указанной *proc* (вместо вызова [GetProcAddress.](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) Этот макрос — версия AFX_COMCTL32_IF_EXISTS Unicode.

### <a name="requirements"></a>Требования

afxcomctl32.h, afxcomctl32.inl

## <a name="declare_dynamic"></a><a name="declare_dynamic"></a>DECLARE_DYNAMIC

Добавляет возможность доступа к информации о времени выполнения класса при произвеспособности класса. `CObject`

```
DECLARE_DYNAMIC(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

### <a name="remarks"></a>Remarks

Добавьте DECLARE_DYNAMIC макрос в модуль заголовка (.h) для класса, а затем включите этот модуль во все модули .cpp, которые нуждаются в доступе к объектам этого класса.

Если вы используете DECLARE_ DYNAMIC и IMPLEMENT_DYNAMIC макросы, как `CObject::IsKindOf` описано, вы можете использовать RUNTIME_CLASS макрос и функцию для определения класса ваших объектов во время выполнения.

Если DECLARE_DYNAMIC включена в декларацию класса, то IMPLEMENT_DYNAMIC должны быть включены в реализацию класса.

Для получения дополнительной информации о DECLARE_DYNAMIC макрос, [см.](../../mfc/using-cobject.md)

### <a name="example"></a>Пример

Смотрите пример [для IMPLEMENT_DYNAMIC](#implement_dynamic).

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="declare_dyncreate"></a><a name="declare_dyncreate"></a>DECLARE_DYNCREATE

Позволяет динамически создавать объекты `CObject`высвоенных классов во время выполнения.

```
DECLARE_DYNCREATE(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

### <a name="remarks"></a>Remarks

Платформа использует эту способность для динамического создания новых объектов. Например, новое представление создается при открытии нового документа. Классы документов, представлений и кадров должны поддерживать динамическое создание, поскольку структура должна создавать их динамически.

Добавьте DECLARE_DYNCREATE макрос в модуль .h для класса, а затем включите этот модуль во все модули .cpp, которые нуждаются в доступе к объектам этого класса.

Если DECLARE_DYNCREATE включенв в декларацию класса, то IMPLEMENT_DYNCREATE должны быть включены в реализацию класса.

Для получения дополнительной информации о DECLARE_DYNCREATE макрос, [см.](../../mfc/using-cobject.md)

> [!NOTE]
> Макрос DECLARE_DYNCREATE включает в себя всю функциональность DECLARE_DYNAMIC.

### <a name="example"></a>Пример

Смотрите пример [для IMPLEMENT_DYNCREATE](#implement_dyncreate).

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="declare_olectltype"></a><a name="declare_olectltype"></a>DECLARE_OLECTLTYPE

Объявляет `GetUserTypeNameID` функции `GetMiscStatus` и функции элемента вашего класса управления.

### <a name="syntax"></a>Синтаксис

```
DECLARE_OLECTLTYPE( class_name )
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса управления.

### <a name="remarks"></a>Remarks

`GetUserTypeNameID`и `GetMiscStatus` являются чистыми виртуальными функциями, объявленными в `COleControl`. Поскольку эти функции являются чистыми виртуальными, они должны быть переопределены в вашем классе управления. В дополнение к DECLARE_OLECTLTYPE необходимо добавить IMPLEMENT_OLECTLTYPE макрос в декларацию класса управления.

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="declare_proppageids"></a><a name="declare_proppageids"></a>DECLARE_PROPPAGEIDS

Заявляет, что элемент управления OLE предоставляет список страниц свойств для отображения его свойств.

### <a name="syntax"></a>Синтаксис

```
DECLARE_PROPPAGEIDS( class_name )
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса управления, владеющего страницами свойств.

### <a name="remarks"></a>Remarks

Используйте `DECLARE_PROPPAGEIDS` макрос в конце объявления класса. Затем в файле .cpp, определяющем функции участника `BEGIN_PROPPAGEIDS` для класса, используйте макрос, макрозаписи для `END_PROPPAGEIDS` каждой страницы свойств элемента управления и макрос для объявления конца списка страниц свойств.

Для получения дополнительной информации о страницах свойств смотрите статью [ActiveX Controls: Property Pages](../mfc-activex-controls-property-pages.md).

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="declare_serial"></a><a name="declare_serial"></a>DECLARE_SERIAL

Генерирует код заголовка СЗ, необходимый для класса, полученного, `CObject`который может быть сериализован.

```
DECLARE_SERIAL(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

### <a name="remarks"></a>Remarks

Сериализация — это процесс написания или чтения содержимого объекта в файл и из нее.

Используйте DECLARE_SERIAL макрос в модуле .h, а затем включите этот модуль во все модули .cpp, которые нуждаются в доступе к объектам этого класса.

Если DECLARE_SERIAL включенв в декларацию класса, то IMPLEMENT_SERIAL должны быть включены в реализацию класса.

Макрос DECLARE_SERIAL включает в себя все функционал DECLARE_DYNAMIC и DECLARE_DYNCREATE.

Можно использовать AFX_API макрос для `CArchive` автоматического экспорта оператора извлечения для классов, которые используют DECLARE_SERIAL и IMPLEMENT_SERIAL макросы. Кронштейн классовых деклараций (расположенных в файле .h) со следующим кодом:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Для получения дополнительной информации о DECLARE_SERIAL макрос, [см.](../../mfc/using-cobject.md)

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#21](../../mfc/codesnippet/cpp/run-time-object-model-services_2.h)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="implement_dynamic"></a><a name="implement_dynamic"></a>IMPLEMENT_DYNAMIC

Генерирует код СЗ, необходимый `CObject`для динамического класса с доступом к названию и положению класса в иерархии.

```
IMPLEMENT_DYNAMIC(class_name, base_class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

*base_class_name*<br/>
Имя базового класса.

### <a name="remarks"></a>Remarks

Используйте IMPLEMENT_DYNAMIC макрос в модуле .cpp, а затем свяжете полученный объектный код только один раз.

Для получения дополнительной [информации](../../mfc/using-cobject.md)см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#2](../../mfc/codesnippet/cpp/run-time-object-model-services_3.h)]

[!code-cpp[NVC_MFCCObjectSample#3](../../mfc/codesnippet/cpp/run-time-object-model-services_4.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="implement_dyncreate"></a><a name="implement_dyncreate"></a>IMPLEMENT_DYNCREATE

Позволяет динамически `CObject`создавать объекты выдержанных классов во время выполнения при использовании с DECLARE_DYNCREATE макросом.

```
IMPLEMENT_DYNCREATE(class_name, base_class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

*base_class_name*<br/>
Фактическое название базового класса.

### <a name="remarks"></a>Remarks

Фрейм использует эту возможность для динамического создания новых объектов, например, когда он считывает объект с диска во время сериализации. Добавьте IMPLEMENT_DYNCREATE макрос атакжем в файл реализации класса. Для получения дополнительной [информации](../../mfc/using-cobject.md)см.

Если вы используете DECLARE_DYNCREATE и IMPLEMENT_DYNCREATE макросы, можно `CObject::IsKindOf` использовать RUNTIME_CLASS макрос и функцию члена для определения класса объектов во время выполнения.

Если DECLARE_DYNCREATE включенв в декларацию класса, то IMPLEMENT_DYNCREATE должны быть включены в реализацию класса.

Обратите внимание, что это макроопределение будет вызывать конструктора по умолчанию для вашего класса. Если нетривиальный конструктор явно реализован классом, он также должен явно реализовать конструктор по умолчанию. Конструктор по умолчанию может быть добавлен в **частные** или **защищенные** разделы участников класса, чтобы предотвратить его вызов из-за пределов реализации класса.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#22](../../mfc/codesnippet/cpp/run-time-object-model-services_5.h)]

[!code-cpp[NVC_MFCCObjectSample#23](../../mfc/codesnippet/cpp/run-time-object-model-services_6.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="implement_olecreate_flags"></a><a name="implement_olecreate_flags"></a>IMPLEMENT_OLECREATE_FLAGS

Либо этот макрос, либо [IMPLEMENT_OLECREATE](#implement_olecreate) должны отображаться в файле реализации для любого класса, использующем DECLARE_OLECREATE.

### <a name="syntax"></a>Синтаксис

```
IMPLEMENT_OLECREATE_FLAGS( class_name, external_name, nFlags,
    l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

*external_name*<br/>
Имя объекта, подверженное другим приложениям (прилагается в кавычках).

*nФлаги*<br/>
Содержит один или несколько из следующих флагов:

- `afxRegInsertable`Позволяет элементуправления отображаться в диалоговом окне объекта вставки для объектов OLE.
- `afxRegApartmentThreading`Устанавливает модель резьбы в реестре на ThreadingModel-Квартира.
- `afxRegFreeThreading`Устанавливает модель потоков в реестре на ThreadingModel-Free.

Вы можете объединить `afxRegApartmentThreading` два `afxRegFreeThreading` флага и установить ThreadingModel-Оба. Подробнее о регистрации моделей потоков читайте в [см. InprocServer32.](/windows/win32/com/inprocserver32)

*l*, *w1,* *w2,* *b1*, *b2,* *b3,* *b4,* *b5,* *b6,* *b7,* *b8* Компоненты CLSID класса.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Если вы используете IMPLEMENT_OLECREATE_FLAGS, можно указать, какую модель потоков поддерживает ваш объект, используя параметр *nFlags.* Если вы хотите поддерживать только модель с одним протекторами, используйте IMPLEMENT_OLECREATE.

Внешнее имя — это идентификатор, подверженный другим приложениям. Клиентские приложения используют внешнее имя для запроса объекта этого класса с сервера автоматизации.

Идентификатор класса OLE является уникальным 128-разрядным идентификатором для объекта. Он состоит из одного **длинного,** два **WORD**с, и восемь **BYTE**s, как представлено *l*, *w1*, *w2*, и *b1* через *b8* в описании синтаксиса. Мастер приложений и мастера кода создают уникальные идентифицироваться по классу OLE по мере необходимости.

### <a name="requirements"></a>Требования

**Заголовок:** afxdisp.h

## <a name="implement_olectltype"></a><a name="implement_olectltype"></a>IMPLEMENT_OLECTLTYPE

Реализует `GetUserTypeNameID` функции `GetMiscStatus` элемента управления и функций элемента.

### <a name="syntax"></a>Синтаксис

```
DECLARE_OLECTLTYPE( class_name, idsUserTypeName, dwOleMisc )
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Название класса управления.

*idsUserTypeName*<br/>
Идентификатор ресурса строки, содержащий внешнее название элемента управления.

*dwOleMisc*<br/>
Перечисление, содержащее один или несколько флагов. Более подробную информацию об этом перечислении [можно](/windows/win32/api/oleidl/ne-oleidl-olemisc) опереть в SDK Windows.

### <a name="remarks"></a>Remarks

В дополнение к IMPLEMENT_OLECTLTYPE необходимо добавить DECLARE_OLECTLTYPE макрос в декларацию класса управления.

Функция `GetUserTypeNameID` элемента возвращает строку ресурса, которая определяет класс управления. `GetMiscStatus`возвращает биты OLEMISC для вашего контроля. Этот перечне указывает набор параметров, описывающих различные характеристики вашего элемента управления. Полное описание настроек OLEMISC [можно](/windows/win32/api/oleidl/ne-oleidl-olemisc) узнать в SDK windows.

> [!NOTE]
> Настройки по умолчанию, используемые ActiveX ControlWizard: OLEMISC_ACTIVATEWHENVISIBLE, OLEMISC_SETCLIENTSITEFIRST, OLEMISC_INSIDEOUT, OLEMISC_CANTLINKINSIDE и OLEMISC_RECOMPOSEONRESIZE.

### <a name="requirements"></a>Требования

**Заголовок:** afxctl.h

## <a name="implement_serial"></a><a name="implement_serial"></a>IMPLEMENT_SERIAL

Генерирует код СЗ, необходимый `CObject`для динамического класса с доступом к названию и положению класса в иерархии.

```
IMPLEMENT_SERIAL(class_name, base_class_name, wSchema)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

*base_class_name*<br/>
Имя базового класса.

*wSchema*<br/>
"Номер версии UINT", который будет закодирован в архиве, чтобы программа десериализации могла идентифицировать и обрабатывать данные, созданные более ранними версиями программы. Номер схемы класса не должен быть -1.

### <a name="remarks"></a>Remarks

Используйте IMPLEMENT_SERIAL макрос в модуле .cpp; затем связать полученный объектный код только один раз.

Можно использовать AFX_API макрос для `CArchive` автоматического экспорта оператора извлечения для классов, которые используют DECLARE_SERIAL и IMPLEMENT_SERIAL макросы. Кронштейн классовых деклараций (расположенных в файле .h) со следующим кодом:

[!code-cpp[NVC_MFCCObjectSample#20](../../mfc/codesnippet/cpp/run-time-object-model-services_1.h)]

Для получения дополнительной [информации](../../mfc/using-cobject.md)см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#24](../../mfc/codesnippet/cpp/run-time-object-model-services_7.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="runtime_class"></a><a name="runtime_class"></a>RUNTIME_CLASS

Получает структуру класса времени выполнения от имени класса СЗ.

```
RUNTIME_CLASS(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса (не заключено в кавычки).

### <a name="remarks"></a>Remarks

RUNTIME_CLASS возвращает указатель в структуру [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) для класса, указанного *class_name.* Только `CObject`-производные классы, объявленные с DECLARE_DYNAMIC, `CRuntimeClass` DECLARE_DYNCREATE или DECLARE_SERIAL, вернут указатели в структуру.

Для получения дополнительной [информации](../../mfc/using-cobject.md)см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCCObjectSample#25](../../mfc/codesnippet/cpp/run-time-object-model-services_8.cpp)]

### <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="declare_olecreate"></a><a name="declare_olecreate"></a>DECLARE_OLECREATE

Позволяет создавать `CCmdTarget`объекты вылимых классов с помощью автоматизации OLE.

```
DECLARE_OLECREATE(class_name)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

### <a name="remarks"></a>Remarks

Этот макрос позволяет другим приложениям с поддержкой OLE создавать объекты этого типа.

Добавьте DECLARE_OLECREATE макрос в модуль .h для класса, а затем включите этот модуль во все модули .cpp, которые нуждаются в доступе к объектам этого класса.

Если DECLARE_OLECREATE включенв в декларацию класса, то IMPLEMENT_OLECREATE должны быть включены в реализацию класса. Декларация класса с использованием DECLARE_OLECREATE также должна использовать сяDECLARE_DYNCREATE или DECLARE_SERIAL.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="implement_olecreate"></a><a name="implement_olecreate"></a>IMPLEMENT_OLECREATE

Либо этот макрос, либо [IMPLEMENT_OLECREATE_FLAGS](#implement_olecreate_flags) должны отображаться `DECLARE_OLECREATE`в файле реализации для любого класса, который использует.

```
IMPLEMENT_OLECREATE(class_name, external_name, l, w1, w2, b1, b2, b3, b4, b5, b6, b7, b8)
```

### <a name="parameters"></a>Параметры

*class_name*<br/>
Фактическое название класса.

*external_name*<br/>
Имя объекта, подверженное другим приложениям (прилагается в кавычках).

*l*, *w1,* *w2,* *b1*, *b2,* *b3,* *b4,* *b5,* *b6,* *b7,* *b8* Компоненты CLSID класса.

### <a name="remarks"></a>Remarks

> [!NOTE]
> Если вы используете IMPLEMENT_OLECREATE, по умолчанию вы поддерживаете только одну модель потоков. Если вы используете IMPLEMENT_OLECREATE_FLAGS, можно указать, какую модель потоков поддерживает ваш объект, используя параметр *nFlags.*

Внешнее имя — это идентификатор, подверженный другим приложениям. Клиентские приложения используют внешнее имя для запроса объекта этого класса с сервера автоматизации.

Идентификатор класса OLE является уникальным 128-разрядным идентификатором для объекта. Он состоит из одного **длинного,** два **WORD**с, и восемь **BYTE**s, как представлено *l*, *w1*, *w2*, и *b1* через *b8* в описании синтаксиса. Мастер приложений и мастера кода создают уникальные идентифицироваться по классу OLE по мере необходимости.

### <a name="requirements"></a>Требования

**Заголовок**: afxdisp.h

## <a name="see-also"></a>См. также раздел

[Макросы и глобальные объекты](mfc-macros-and-globals.md)<br/>
[Изоляция Библиотеки общего контроля МФЦ](../isolation-of-the-mfc-common-controls-library.md)<br/>
[CLSID Ключ](/windows/win32/com/clsid-key-hklm)
