---
title: Макрос точки входа интерфейса COM
ms.date: 03/28/2017
f1_keywords:
- atlcom/ATL::COM_INTERFACE_ENTRY
- atlcom/ATL::COM_INTERFACE_ENTRY_IID
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE
- atlcom/ATL::COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_BREAK
- atlcom/ATL::COM_INTERFACE_ENTRY_CACHED_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_TEAR_OFF
- atlcom/ATL::COM_INTERFACE_ENTRY_CHAIN
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC
- atlcom/ATL::COM_INTERFACE_ENTRY_FUNC_BLIND
- atlcom/ATL::COM_INTERFACE_ENTRY_NOINTERFACE
helpviewer_keywords:
- COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
ms.openlocfilehash: ed2b8445a0f13b82338d2904d43fd17688d05b9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62245586"
---
# <a name="cominterfaceentry-macros"></a>Макросы COM_INTERFACE_ENTRY

Эти макросы ввести интерфейсы объекта в его сопоставления COM, таким образом, чтобы они обращаются `QueryInterface`. Порядок записей в карте COM является интерфейсов порядок будет проверяться сопоставления IID во время `QueryInterface`.

|||
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|Вводит интерфейсы COM схему интерфейсов.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Используйте этот макрос для однозначного определения двух ветвей наследования.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Используйте этот макрос введите интерфейса в сопоставление COM и указать его идентификатор IID.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Совпадение с кодом [COM_INTERFACE_ENTRY2](#com_interface_entry2), за исключением того, можно указать разные IID.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Если интерфейс определяется *iid* запрашиваются, `COM_INTERFACE_ENTRY_AGGREGATE` пересылает `punk`.|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|Совпадение с кодом [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрос любой IID приводит пересылки запрос, чтобы *punk*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|Совпадение с кодом [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), кроме *punk* имеет значение NULL, он автоматически создает статистическое выражение, описываемое *clsid*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|Совпадение с кодом [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос любой IID приводит пересылки запрос, чтобы *punk*и если *punk* имеет значение NULL, автоматически создавая статистическое выражение, описываемое *clsid*.|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Выполняется вызов [DebugBreak](https://msdn.microsoft.com/library/windows/desktop/ms679297) при запросе указанный интерфейс.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Сохраняет данные на уровне интерфейса для каждого экземпляра.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Представляет перемещаемые интерфейсы.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Выполняет сопоставление COM базового класса, когда будет достигнут эту запись в карту COM.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Общий механизм для прикрепления ATL `QueryInterface` логики.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Совпадение с кодом [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос любой IID приводит к вызову для *func*.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Возвращается E_NOINTERFACE и завершения обработки COM карты при запросе указанный интерфейс.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="com_interface_entry"></a> COM_INTERFACE_ENTRY

Вводит интерфейсы COM схему интерфейсов.

### <a name="syntax"></a>Синтаксис

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Имя интерфейса класс объекта является производным от напрямую.

### <a name="remarks"></a>Примечания

Как правило это тип записи, наиболее часто используемых.

### <a name="example"></a>Пример

```cpp
BEGIN_COM_MAP(CThisExample)
   COM_INTERFACE_ENTRY(IThisExample)
   COM_INTERFACE_ENTRY(IDispatch)
   COM_INTERFACE_ENTRY(ISupportErrorInfo)
END_COM_MAP()
```

### <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

##  <a name="com_interface_entry2"></a>  COM_INTERFACE_ENTRY2

Используйте этот макрос для однозначного определения двух ветвей наследования.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Имя интерфейса, которому требуется предоставить доступ из объекта.

*x2*<br/>
[in] Имя ветви наследования, из которого *x* предоставляется.

### <a name="remarks"></a>Примечания

Например, если вы наследуете класс объекта из двух сдвоенные интерфейсы, можно предоставлять `IDispatch` с помощью COM_INTERFACE_ENTRY2 с момента `IDispatch` можно получить в любой из двух интерфейсов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

##  <a name="com_interface_entry_iid"></a>  COM_INTERFACE_ENTRY_IID

Используйте этот макрос введите интерфейса в сопоставление COM и указать его идентификатор IID.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор GUID интерфейса, предоставляемые.

*x*<br/>
[in] Имя класса, на которых vtable будет представляться как интерфейс, определенный *iid*.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

##  <a name="com_interface_entry2_iid"></a>  COM_INTERFACE_ENTRY2_IID

Совпадение с кодом [COM_INTERFACE_ENTRY2](#com_interface_entry2), за исключением того, можно указать разные IID.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор GUID, который вы указываете для интерфейса.

*x*<br/>
[in] Имя интерфейса, класс объекта является производным от напрямую.

*x2*<br/>
[in] Имя второй интерфейс, класс объекта является производным от напрямую.

##  <a name="com_interface_entry_aggregate"></a>  COM_INTERFACE_ENTRY_AGGREGATE

Если интерфейс определяется *iid* запрашивается для пересылает COM_INTERFACE_ENTRY_AGGREGATE *punk*.

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор GUID интерфейса, запрашивается.

*pUnk*<br/>
[in] Имя `IUnknown` указатель.

### <a name="remarks"></a>Примечания

*Punk* параметр предполагается, что для указания внутреннего неизвестно статистическое выражение или значение NULL, в противном случае операция учитывается. Как правило, вы бы `CoCreate` агрегатную функцию в `FinalConstruct`.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

##  <a name="com_interface_entry_aggregate_blind"></a>  COM_INTERFACE_ENTRY_AGGREGATE_BLIND

Совпадение с кодом [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрос любой IID приводит пересылки запрос, чтобы *punk*.

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
[in] Имя `IUnknown` указатель.

### <a name="remarks"></a>Примечания

Если интерфейс запрос завершится с ошибкой, обработка COM карты продолжается.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

##  <a name="com_interface_entry_autoaggregate"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE

Совпадение с кодом [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), кроме *punk* имеет значение NULL, он автоматически создает статистическое выражение, описываемое *clsid*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор GUID интерфейса, запрашивается.

*pUnk*<br/>
[in] Имя `IUnknown` указатель. Необходимо быть членом класса, содержащего COM карты.

*CLSID*<br/>
[in] Идентификатор агрегата, который будет создан в том случае, если *punk* имеет значение NULL.

### <a name="remarks"></a>Примечания

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

##  <a name="com_interface_entry_autoaggregate_blind"></a>  COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

Совпадение с кодом [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос любой IID приводит пересылки запрос, чтобы *punk*и если *punk* имеет значение NULL, автоматически создавая статистическое выражение, описываемое *clsid*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>Параметры

*pUnk*<br/>
[in] Имя `IUnknown` указатель. Необходимо быть членом класса, содержащего COM карты.

*CLSID*<br/>
[in] Идентификатор агрегата, который будет создан в том случае, если *punk* имеет значение NULL.

### <a name="remarks"></a>Примечания

Если интерфейс запрос завершится с ошибкой, обработка COM карты продолжается.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

##  <a name="com_interface_entry_break"></a>  COM_INTERFACE_ENTRY_BREAK

Выполняется вызов [DebugBreak](https://msdn.microsoft.com/library/windows/desktop/ms679297) при запросе указанный интерфейс.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Текст, используемый для создания идентификатора интерфейса.

### <a name="remarks"></a>Примечания

Интерфейс IID будет сформировать, добавив *x* для `IID_`. Например если *x* — `IPersistStorage`, будет иметь идентификатор IID `IID_IPersistStorage`.

##  <a name="com_interface_entry_cached_tear_off"></a>  COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

Сохраняет данные на уровне интерфейса для каждого экземпляра.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор GUID интерфейса перемещаемой.

*x*<br/>
[in] Имя класса, реализующего интерфейс.

*pUnk*<br/>
[in] Имя `IUnknown` указатель. Необходимо быть членом класса, содержащего COM карты. Должен быть инициализирован NULL в конструктор класса объекта.

### <a name="remarks"></a>Примечания

Если интерфейс не используется, это уменьшает общий размер экземпляра объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

##  <a name="com_interface_entry_tear_off"></a>  COM_INTERFACE_ENTRY_TEAR_OFF

Представляет перемещаемые интерфейсы.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор GUID интерфейса перемещаемой.

*x*<br/>
[in] Имя класса, реализующего интерфейс.

### <a name="remarks"></a>Примечания

Перемещаемые интерфейс реализуется как отдельный объект, экземпляр которого создается каждый раз, интерфейс, он представляет запрашиваются. Как правило вы создадите интерфейса как перемещаемые Если этот интерфейс используется редко, так как это сэкономить vtable указателя в каждом экземпляре основного объекта. Перемещаемое удаляется, когда его счетчик становится равным нулю. Класс, реализующий перемещаемой должен быть производным от `CComTearOffObjectBase` и иметь свой собственный COM карты.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

##  <a name="com_interface_entry_chain"></a>  COM_INTERFACE_ENTRY_CHAIN

Выполняет сопоставление COM базового класса, когда будет достигнут эту запись в карту COM.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>Параметры

*classname*<br/>
[in] Базовый класс текущего объекта.

### <a name="remarks"></a>Примечания

Например в следующем коде:

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

Обратите внимание на то, что первая запись в карту COM, должен быть интерфейсом на объекте, содержащем COM карты. Таким образом, не может начинаться на записях сопоставления COM. с COM_INTERFACE_ENTRY_CHAIN, что приводит к COM карты другого объекта для поиска в точке, где **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** отображается в ваш объект COM карты. Если вы хотите сначала поиск COM карты другого объекта, добавьте запись интерфейс для `IUnknown` в сопоставление COM, затем объединить в цепочку другой объект COM карты. Пример:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

##  <a name="com_interface_entry_func"></a>  COM_INTERFACE_ENTRY_FUNC

Общий механизм для прикрепления ATL `QueryInterface` логики.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>Параметры

*IID*<br/>
[in] Идентификатор GUID интерфейса, предоставляемые.

*dw*<br/>
[in] Параметр, передаваемый через *func*.

*func*<br/>
[in] Указатель на функцию, которая вернет *iid*.

### <a name="remarks"></a>Примечания

Если *iid* соответствующий идентификатор IID интерфейса, запрашивается, а затем функцию, указанную аргументом *func* вызывается. Объявление функции должно быть:

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

При вызове функции `pv` указывает на объект класса. *Riid* параметр ссылается на интерфейс, запрашиваемый для, `ppv` — указатель на расположение, где функция следует хранить указатель на интерфейс, и *dw* является параметром вы указанный в записи. Необходимо задать функцию \* `ppv` значение NULL и возврата E_NOINTERFACE или S_FALSE, если он выбирает не для возврата интерфейса. С E_NOINTERFACE завершает обработку COM карты. С помощью S_FALSE, COM карты обработка продолжается, несмотря на то, что было возвращено не указатель на интерфейс. Если функция возвращает указатель интерфейса, она должна возвращать S_OK.

##  <a name="com_interface_entry_func_blind"></a>  COM_INTERFACE_ENTRY_FUNC_BLIND

Совпадение с кодом [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос любой IID приводит к вызову для *func*.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>Параметры

*dw*<br/>
[in] Параметр, передаваемый через *func*.

*func*<br/>
[in] Функция, которая вызывается при обработке данной записи в COM карты.

### <a name="remarks"></a>Примечания

Любой сбой приведет обработка будет продолжена на карте COM. Если функция возвращает указатель интерфейса, она должна возвращать S_OK.

##  <a name="com_interface_entry_nointerface"></a>  COM_INTERFACE_ENTRY_NOINTERFACE

Возвращается E_NOINTERFACE и завершения обработки COM карты при запросе указанный интерфейс.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
[in] Текст, используемый для создания идентификатора интерфейса.

### <a name="remarks"></a>Примечания

Этот макрос можно использовать для предотвращения использования в конкретном случае интерфейс. Например этот макрос можно вставить в сопоставление COM непосредственно перед COM_INTERFACE_ENTRY_AGGREGATE_BLIND для предотвращения пересылки в неизвестный тип агрегата внутренний запрос для интерфейса.

Интерфейс IID будет сформировать, добавив *x* для `IID_`. Например если *x* — `IPersistStorage`, будет иметь идентификатор IID `IID_IPersistStorage`.
