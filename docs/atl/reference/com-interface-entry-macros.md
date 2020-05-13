---
title: Com Интерфейс Вход Макрос
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
ms.openlocfilehash: bb7498f639f463290a4a6593ef7c0fbac09b539b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326679"
---
# <a name="com_interface_entry-macros"></a>COM_INTERFACE_ENTRY Макрос

Эти макросы вводят интерфейсы объекта в его карту COM, `QueryInterface`чтобы к ним можно было получить доступ. Порядок записей на карте COM является интерфейсы заказа будут проверены `QueryInterface`на соответствие IID во время.

|||
|-|-|
|[COM_INTERFACE_ENTRY](#com_interface_entry)|Вводит интерфейсы в карту интерфейса COM.|
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Используйте этот макрос, чтобы выдать две ветви наследования.|
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Используйте этот макрос, чтобы ввести интерфейс в карту COM и указать его IID.|
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|Так же, как [COM_INTERFACE_ENTRY2,](#com_interface_entry2)за исключением того, что вы можете указать другой IID.|
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Когда интерфейс, идентифицированный *iid,* `COM_INTERFACE_ENTRY_AGGREGATE` запрашивается `punk`для, перенаправляет в .|
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|То же самое, [что COM_INTERFACE_ENTRY_AGGREGATE,](#com_interface_entry_aggregate)за исключением того, что запрос для любого IID приводит к пересылке запроса в *панк.*|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|То же самое, [что и COM_INTERFACE_ENTRY_AGGREGATE,](#com_interface_entry_aggregate)за исключением, если *панк* является NULL, он автоматически создает агрегат, описанный *clsid*.|
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|То же самое, [что COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос для любого IID приводит к пересылке запроса в *панк,* и если *панк* является NULL, автоматически создавая агрегат, описанный *clsid*.|
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Вызывает вызов программы [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) при запросе указанного интерфейса.|
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Сохраняет данные, связанные с интерфейсом, для каждого экземпляра.|
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Выставляет ваши отрывая интерфейсы.|
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Обрабатывает карту COM базового класса, когда обработка достигает этой записи на карте COM.|
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Общий механизм подключения к логике `QueryInterface` ATL.|
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|Так же, как [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос для любого IID приводит к вызову *func*.|
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Возвращает E_NOINTERFACE и завершает обработку карты COM при запросе указанного интерфейса.|

## <a name="requirements"></a>Требования

**Заголовок:** atlcom.h

## <a name="com_interface_entry"></a><a name="com_interface_entry"></a>COM_INTERFACE_ENTRY

Вводит интерфейсы в карту интерфейса COM.

### <a name="syntax"></a>Синтаксис

```
COM_INTERFACE_ENTRY( x )
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Название интерфейса объекта класса происходит от прямого.

### <a name="remarks"></a>Remarks

Как правило, это тип входа, который вы используете чаще всего.

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

## <a name="com_interface_entry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2

Используйте этот макрос, чтобы выдать две ветви наследования.

```
COM_INTERFACE_ENTRY2(x, x2)
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Название интерфейса, который вы хотите выявить с объекта.

*x2*<br/>
(в) Название ветви наследования, из которой подвергается *x.*

### <a name="remarks"></a>Remarks

Например, если вы получаете объект класса из `IDispatch` двух двойных интерфейсов, вы подвергаете себя использованию COM_INTERFACE_ENTRY2 поскольку `IDispatch` можно получить из одного из интерфейсов.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]

## <a name="com_interface_entry_iid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID

Используйте этот макрос, чтобы ввести интерфейс в карту COM и указать его IID.

```
COM_INTERFACE_ENTRY_IID(iid, x)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID интерфейса подвергается.

*x*<br/>
(в) Название класса, vtable которого будет выставлено в виде интерфейса, идентифицированного *iid.*

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]

## <a name="com_interface_entry2_iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID

Так же, как [COM_INTERFACE_ENTRY2,](#com_interface_entry2)за исключением того, что вы можете указать другой IID.

```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID, указанный для интерфейса.

*x*<br/>
(в) Название интерфейса, от которого объект класса происходит напрямую.

*x2*<br/>
(в) Название второго интерфейса, от которого объект класса происходит напрямую.

## <a name="com_interface_entry_aggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE

Когда интерфейс, идентифицированный *iid,* запрашивается, COM_INTERFACE_ENTRY_AGGREGATE перенаправляет в *панк.*

```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID интерфейса запрашивается.

*Панк*<br/>
(в) Имя `IUnknown` указателя.

### <a name="remarks"></a>Remarks

Предполагается, что параметр *панка* указывает на внутреннее неизвестность агрегата или null, и в этом случае запись игнорируется. Как правило, `CoCreate` вы `FinalConstruct`бы агрегат в .

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]

## <a name="com_interface_entry_aggregate_blind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND

То же самое, [что COM_INTERFACE_ENTRY_AGGREGATE,](#com_interface_entry_aggregate)за исключением того, что запрос для любого IID приводит к пересылке запроса в *панк.*

```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Имя `IUnknown` указателя.

### <a name="remarks"></a>Remarks

Если запрос интерфейса завершается неудачей, обработка карты COM продолжается.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]

## <a name="com_interface_entry_autoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE

То же самое, [что и COM_INTERFACE_ENTRY_AGGREGATE,](#com_interface_entry_aggregate)за исключением, если *панк* является NULL, он автоматически создает агрегат, описанный *clsid*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID интерфейса запрашивается.

*Панк*<br/>
(в) Имя `IUnknown` указателя. Должен быть членом класса, содержащим карту COM.

*clsid*<br/>
(в) Идентификатор агрегата, который будет создан, если *панк* является NULL.

### <a name="remarks"></a>Remarks

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]

## <a name="com_interface_entry_autoaggregate_blind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND

То же самое, [что COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос для любого IID приводит к пересылке запроса в *панк,* и если *панк* является NULL, автоматически создавая агрегат, описанный *clsid*.

```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```

### <a name="parameters"></a>Параметры

*Панк*<br/>
(в) Имя `IUnknown` указателя. Должен быть членом класса, содержащим карту COM.

*clsid*<br/>
(в) Идентификатор агрегата, который будет создан, если *панк* является NULL.

### <a name="remarks"></a>Remarks

Если запрос интерфейса завершается неудачей, обработка карты COM продолжается.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]

## <a name="com_interface_entry_break"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK

Вызывает вызов программы [DebugBreak](/windows/win32/api/debugapi/nf-debugapi-debugbreak) при запросе указанного интерфейса.

```
COM_INTERFACE_ENTRY_BREAK(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Текст, используемый для построения идентификатора интерфейса.

### <a name="remarks"></a>Remarks

Интерфейс IID будет построен путем *x* приложения `IID_`x к . Например, *x* если `IPersistStorage`x является, IID будет `IID_IPersistStorage`.

## <a name="com_interface_entry_cached_tear_off"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF

Сохраняет данные, связанные с интерфейсом, для каждого экземпляра.

```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID интерфейса отрыва.

*x*<br/>
(в) Название класса, реализующего интерфейс.

*Панк*<br/>
(в) Имя `IUnknown` указателя. Должен быть членом класса, содержащим карту COM. Должен быть инициализирован до NULL в конструкторе объекта класса.

### <a name="remarks"></a>Remarks

Если интерфейс не используется, это снижает общий размер экземпляра объекта.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]

## <a name="com_interface_entry_tear_off"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF

Выставляет ваши отрывая интерфейсы.

```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID интерфейса отрыва.

*x*<br/>
(в) Название класса, реализующего интерфейс.

### <a name="remarks"></a>Remarks

Интерфейс отрыва реализуется как отдельный объект, который мгновенно выполняется каждый раз, когда запрашивается интерфейс, для которого он представляет. Как правило, вы строите интерфейс как разрыв, если интерфейс используется редко, так как это сохраняет указатель vtable в каждом экземпляре вашего основного объекта. Разрыв удаляется, когда количество ссылок становится нулевым. Класс, осуществляющий разрыв, должен быть `CComTearOffObjectBase` получен из собственной карты COM.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]

## <a name="com_interface_entry_chain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN

Обрабатывает карту COM базового класса, когда обработка достигает этой записи на карте COM.

```
COM_INTERFACE_ENTRY_CHAIN(classname)
```

### <a name="parameters"></a>Параметры

*Classname*<br/>
(в) Базовый класс текущего объекта.

### <a name="remarks"></a>Remarks

Например, в следующем коде:

[!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]

Обратите внимание, что первая запись на карте COM должна быть интерфейсом на объекте, содержащем карту COM. Таким образом, вы не можете начать записи карты COM с COM_INTERFACE_ENTRY_CHAIN, что приводит к поиску карты COM другого объекта в точке, где **COM_INTERFACE_ENTRY_CHAIN ()**`COtherObject`**)** отображается на карте COM объекта. Если сначала требуется сначала выполнить поиск карты COM `IUnknown` другого объекта, добавьте запись интерфейса для вашей карты COM, а затем цепочку COM карты другого объекта. Пример:

[!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]

## <a name="com_interface_entry_func"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC

Общий механизм подключения к логике `QueryInterface` ATL.

```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```

### <a name="parameters"></a>Параметры

*Iid*<br/>
(в) GUID интерфейса подвергается.

*dw*<br/>
(в) Параметр прошел через *func*.

*func*<br/>
(в) Функция указатель, который будет возвращать *iid*.

### <a name="remarks"></a>Remarks

Если *iid* соответствует IID запрашиваемого интерфейса, то вызывается функция, указанная *func.* Декларация для функции должна быть:

`HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`

Когда функция вызывается, `pv` указывает на объект класса. Параметр *riid* относится к запрашиваемому интерфейсу, `ppv` является указателем на место, где функция должна хранить указатель на интерфейс, а *dw* — это параметр, указанный в записи. Функция должна \* `ppv` быть установлена null и возврат E_NOINTERFACE или S_FALSE, если она решит не возвращать интерфейс. С E_NOINTERFACE обработка карты COM прекращается. С S_FALSE, обработка карты COM продолжается, даже если ни один указатель интерфейса не был возвращен. Если функция возвращает указатель интерфейса, она должна вернуть S_OK.

## <a name="com_interface_entry_func_blind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND

Так же, как [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос для любого IID приводит к вызову *func*.

```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```

### <a name="parameters"></a>Параметры

*dw*<br/>
(в) Параметр прошел через *func*.

*func*<br/>
(в) Функция, которая вызывается при обработке этой записи на карте COM.

### <a name="remarks"></a>Remarks

Любой сбой приведет к продолжению обработки на карте COM. Если функция возвращает указатель интерфейса, она должна вернуть S_OK.

## <a name="com_interface_entry_nointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE

Возвращает E_NOINTERFACE и завершает обработку карты COM при запросе указанного интерфейса.

```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```

### <a name="parameters"></a>Параметры

*x*<br/>
(в) Текст, используемый для построения идентификатора интерфейса.

### <a name="remarks"></a>Remarks

Этот макрос можно использовать для предотвращения использования интерфейса в конкретном случае. Например, этот макрос можно вставить в карту COM прямо перед COM_INTERFACE_ENTRY_AGGREGATE_BLIND чтобы предотвратить переадресации запроса для интерфейса на внутренний неизвестный агрегат.

Интерфейс IID будет построен путем *x* приложения `IID_`x к . Например, *x* если `IPersistStorage`x является, IID будет `IID_IPersistStorage`.
