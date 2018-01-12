---
title: "Макросы записи COM-интерфейса | Документы Microsoft"
ms.custom: 
ms.date: 03/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
helpviewer_keywords: COM interfaces, COM interface entry macros
ms.assetid: 19dcb768-2e1f-4b8d-a618-453a01a4bd00
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76352cf2015661bc970b2987b9794f3bf023cc15
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cominterfaceentry-macros"></a>Макросы COM_INTERFACE_ENTRY  
 Эти макросы ввести интерфейсы объекта в его сопоставления COM, чтобы они могли быть доступны для `QueryInterface`. Порядок записей в карте COM является интерфейсы заказа будет проверяться соответствие **IID** во время `QueryInterface`.  

 |||
 |-|-|
 |[COM_INTERFACE_ENTRY](#com_interface_entry)|Вводит интерфейсы COM схему интерфейсов.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Используйте этот макрос для однозначного определения двух ветвей наследования.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Используйте этот макрос для входа в интерфейс в сопоставление COM и укажите его IID.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|То же, что [COM_INTERFACE_ENTRY2](#com_interface_entry2), за исключением того, можно указать другой IID.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Если интерфейс определяется `iid` запрашиваются, `COM_INTERFACE_ENTRY_AGGREGATE` пересылает `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрашивает все IID приведет к переадресации запросов в `punk`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), кроме `punk` — **NULL**, он автоматически создает статистическое выражение, описываемое `clsid`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|То же, что [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрашивает все IID приведет к переадресации запросов для `punk`и если `punk` — **NULL**, автоматически создавая статистическое выражение, описываемое `clsid`.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Выполняется вызов [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) при запросе для указанного интерфейса.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Сохраняет данные на уровне интерфейса для каждого экземпляра.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Представляет перемещаемые интерфейсы.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Выполняет сопоставление COM базового класса, когда будет достигнут этой записи в схеме COM.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Основной механизм для прикрепления ATL `QueryInterface` логику.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|То же, что [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос для любой IID приводит к вызову для `func`.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Возвращает **E_NOINTERFACE** и завершает обработку карты COM, когда запрашиваются указанного интерфейса.|  

## <a name="requirements"></a>Требования
**Заголовок:** atlcom.h

## <a name="com_interface_entry"></a>COM_INTERFACE_ENTRY
Вводит интерфейсы COM схему интерфейсов.

### <a name="syntax"></a>Синтаксис

```
COM_INTERFACE_ENTRY( x )
```
### <a name="parameters"></a>Параметры

x [in] Имя интерфейса класса объекта является производным от напрямую.

### <a name="remarks"></a>Примечания
Как правило это наиболее часто используемых тип операции.

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
  
##  <a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 Используйте этот макрос для однозначного определения двух ветвей наследования.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя интерфейса, которому требуется предоставить доступ из объекта.  
  
 `x2`  
 [in] Имя ветви наследования, из которого *x* предоставляется.  
  
### <a name="remarks"></a>Примечания  
 Например, если вы наследуете класс объекта из двух сдвоенные интерфейсы, доступ к которым предоставляется `IDispatch` с помощью `COM_INTERFACE_ENTRY2` с момента `IDispatch` можно получить с помощью одного из интерфейсов.  
  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#118](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 Используйте этот макрос для входа в интерфейс в сопоставление COM и укажите его IID.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, предоставляемые.  
  
 *x*  
 [in] Имя класса, чьи vtable будет представляться как интерфейс, определенный `iid`.  
  
 
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#117](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 То же, что [COM_INTERFACE_ENTRY2](#com_interface_entry2), за исключением того, можно указать другой IID.  
  
```
COM_INTERFACE_ENTRY2_IID(iid, x, x2)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID, который вы указываете для интерфейса.  
  
 *x*  
 [in] Имя интерфейса, который напрямую наследует класс объекта.  
  
 `x2`  
 [in] Имя второй интерфейс, который напрямую наследует класс объекта.  
  
##  <a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Если интерфейс определяется `iid` запрашиваются, `COM_INTERFACE_ENTRY_AGGREGATE` пересылает `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, который обрабатывает запросы.  
  
 `punk`  
 [in] Имя **IUnknown** указателя.  
  
### <a name="remarks"></a>Примечания  
 `punk` Предполагается указывает внутреннее неизвестно статистическое выражение или значение параметра **NULL**, в этом случае операция учитывается. Как правило, вы бы **CoCreate** статистического выражения в `FinalConstruct`.  
  
  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#112](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрашивает все IID приведет к переадресации запросов в `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Параметры  
 `punk`  
 [in] Имя **IUnknown** указателя.  
  
### <a name="remarks"></a>Примечания  
 Если интерфейс запрос завершится ошибкой, обработка карты COM продолжается.  
  
  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#113](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  

##  <a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), кроме `punk` — **NULL**, он автоматически создает статистическое выражение, описываемое `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, который обрабатывает запросы.  
  
 `punk`  
 [in] Имя **IUnknown** указателя. Необходимо быть членом класса, содержащего сопоставления COM.  
  
 `clsid`  
 [in] Идентификатор статистическое выражение, которое создается, если `punk` — **NULL**.  
  
### <a name="remarks"></a>Примечания  
  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#114](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 То же, что [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрашивает все IID приведет к переадресации запросов для `punk`и если `punk` — **NULL**, автоматически создавая статистическое выражение, описываемое `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Параметры  
 `punk`  
 [in] Имя **IUnknown** указателя. Необходимо быть членом класса, содержащего сопоставления COM.  
  
 `clsid`  
 [in] Идентификатор статистическое выражение, которое создается, если `punk` — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если интерфейс запрос завершится ошибкой, обработка карты COM продолжается.  
  
  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing#115](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 Выполняется вызов [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) при запросе для указанного интерфейса.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Текст, используемый для создания идентификатора интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Будет создан путем добавления IID интерфейса *x* для `IID_`. Например если *x* — `IPersistStorage`, будет IID `IID_IPersistStorage`.  
  
  
  
##  <a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
 Сохраняет данные на уровне интерфейса для каждого экземпляра.  
  
```
COM_INTERFACE_ENTRY_CACHED_TEAR_OFF(iid, x, punk)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса перемещаемые.  
  
 *x*  
 [in] Имя класса, реализующего интерфейс.  
  
 `punk`  
 [in] Имя **IUnknown** указателя. Необходимо быть членом класса, содержащего сопоставления COM. Должен быть инициализирован для **NULL** в конструктор объекта класса.  
  
### <a name="remarks"></a>Примечания  
 Если интерфейс не используется, это сокращает общий размер экземпляра объекта.  
  
  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#54](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
 Представляет перемещаемые интерфейсы.  
  
```
COM_INTERFACE_ENTRY_TEAR_OFF(iid, x)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса перемещаемые.  
  
 *x*  
 [in] Имя класса, реализующего интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Перемещаемые интерфейс реализован как отдельный объект, экземпляр которого создается каждый раз, интерфейс, он представляет запрашиваются. Как правило вы построение интерфейс как перемещаемое интерфейс используется редко, так как это сохраняет указатель vtable в каждом из экземпляров основного объекта. Перемещаемое удаляется, если число ссылок становится равным нулю. Класс, реализующий перемещаемое должен быть производным от `CComTearOffObjectBase` и иметь собственный COM карты.  
  
  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM#1](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 Выполняет сопоставление COM базового класса, когда будет достигнут этой записи в схеме COM.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Параметры  
 *classname*  
 [in] Базовый класс для текущего объекта.  
  
### <a name="remarks"></a>Примечания  
 Например в следующем коде:  
  
 [!code-cpp[NVC_ATL_Windowing#116](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 Обратите внимание, что первая запись в схеме COM должен быть интерфейсом на объект, содержащий сопоставления COM. Таким образом, невозможно запустить на записях сопоставления COM. с `COM_INTERFACE_ENTRY_CHAIN`, чего сопоставление COM другого объекта для поиска в точке, где **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** отображается в сопоставление COM объекта. Поиск картой COM другого объекта в первую очередь следует добавить запись интерфейс для **IUnknown** сопоставление COM, затем цепочки сопоставления COM и другой объект. Пример:  
  
 [!code-cpp[NVC_ATL_Windowing#111](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
  
  
##  <a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 Основной механизм для прикрепления ATL `QueryInterface` логику.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, предоставляемые.  
  
 `dw`  
 [in] Параметр, передаваемый через `func`.  
  
 `func`  
 [in] Указатель функции, которая вернет `iid`.  
  
### <a name="remarks"></a>Примечания  
 Если *iid* совпадает с IID этого интерфейса, запрашивать, а затем функции, указанной `func` вызывается. Объявление функции должно быть:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 При вызове функции `pv` указывает класс объекта. `riid` Параметр ссылается на интерфейс, запрашиваемый для, `ppv` — указатель на расположения хранения указателя на интерфейс, в функцию и `dw` имеет параметр, указанный в операции. Функция следует установить \* `ppv` для **NULL** и возвращают **E_NOINTERFACE** или **S_FALSE** желанию не для возврата интерфейса. С **E_NOINTERFACE**, завершает операцию обработки COM карты. С **S_FALSE**, COM карты обработка продолжается, несмотря на то, что указатель на интерфейс был возвращен. Если функция возвращает указатель интерфейса, он должен возвращать `S_OK`.  
  
  
  
##  <a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 То же, что [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос для любой IID приводит к вызову для `func`.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Параметры  
 `dw`  
 [in] Параметр, передаваемый через `func`.  
  
 `func`  
 [in] Функция, которая вызывается при обработке данной записи в схеме COM.  
  
### <a name="remarks"></a>Примечания  
 Любые сбои приведет к обработке продолжать на COM-карты. Если функция возвращает указатель интерфейса, он должен возвращать `S_OK`.  
  
  
##  <a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 Возвращает **E_NOINTERFACE** и завершает обработку карты COM, когда запрашиваются указанного интерфейса.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Текст, используемый для создания идентификатора интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос можно использовать для предотвращения использования в конкретном случае интерфейс. Например, этот макрос можно вставить в ваш COM сопоставить прямо перед `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` для предотвращения пересылаются на неизвестный внутреннее статистическое выражение запроса для интерфейса.  
  
 Будет создан путем добавления IID интерфейса *x* для `IID_`. Например если *x* — `IPersistStorage`, будет IID `IID_IPersistStorage`.  
  
  