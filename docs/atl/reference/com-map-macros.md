---
title: "Макросы сопоставления COM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, COM map macros
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 79658b6ac22719af7172c9d2848675faf2a23a0c
ms.lasthandoff: 02/24/2017

---
# <a name="com-map-macros"></a>Макросы сопоставления COM
Эти макросы определить сопоставления COM интерфейс.  
  
|||  
|-|-|  
|[BEGIN_COM_MAP](#begin_com_map)|Отмечает начало записей сопоставления COM интерфейс.|  
|[COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00)|Вводит интерфейс сопоставления COM интерфейсы.|  
|[COM_INTERFACE_ENTRY2](#com_interface_entry2)|Используйте этот макрос для однозначного определения двух ветвей наследования.|  
|[COM_INTERFACE_ENTRY_IID](#com_interface_entry_iid)|Используйте этот макрос для входа в интерфейс в сопоставление COM и указать его идентификатор IID.|  
|[COM_INTERFACE_ENTRY2_IID](#com_interface_entry2_iid)|То же, что [COM_INTERFACE_ENTRY2](#com_interface_entry2), но можно указать другой идентификатор IID.|  
|[COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate)|Если интерфейс определяется `iid` запрашиваются, `COM_INTERFACE_ENTRY_AGGREGATE` пересылает `punk`.|  
|[COM_INTERFACE_ENTRY_AGGREGATE_BLIND](#com_interface_entry_aggregate_blind)|То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрос любой IID приводит пересылает запрос на `punk`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate)|То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), кроме `punk` — **NULL**, он автоматически создает статистическое выражение, описываемых `clsid`.|  
|[COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND](#com_interface_entry_autoaggregate_blind)|То же, что [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос любой IID приводит пересылает запрос на `punk`и если `punk` — **NULL**автоматически создания агрегата, описываемых `clsid`.|  
|[COM_INTERFACE_ENTRY_BREAK](#com_interface_entry_break)|Программа для вызова [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) при запросе указанный интерфейс.|  
|[COM_INTERFACE_ENTRY_CACHED_TEAR_OFF](#com_interface_entry_cached_tear_off)|Сохраняет данные на уровне интерфейса для каждого экземпляра.|  
|[COM_INTERFACE_ENTRY_TEAR_OFF](#com_interface_entry_tear_off)|Представляет перемещаемые интерфейсы.|  
|[COM_INTERFACE_ENTRY_CHAIN](#com_interface_entry_chain)|Обрабатывает сопоставления COM базового класса при обработке достигает этой записи в схеме COM.|  
|[COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func)|Общий механизм для прикрепления ATL `QueryInterface` логики.|  
|[COM_INTERFACE_ENTRY_FUNC_BLIND](#com_interface_entry_func_blind)|То же, что [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос любой IID приводит к вызову для `func`.|  
|[COM_INTERFACE_ENTRY_NOINTERFACE](#com_interface_entry_nointerface)|Возвращает **E_NOINTERFACE** и завершает обработку карты COM, когда запрашиваются указанный интерфейс.|  
|[END_COM_MAP](#end_com_map)|Отмечает конец записей сопоставления COM интерфейс.|  

## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
   
##  <a name="a-namebegincommapa--begincommap"></a><a name="begin_com_map"></a>BEGIN_COM_MAP  
 Сопоставления COM — это механизм, предоставляет интерфейсы объекта клиенту с помощью `QueryInterface`.  
  
```
BEGIN_COM_MAP(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя класса объекта используется предоставление интерфейсов.  
  
### <a name="remarks"></a>Примечания  
 [CComObjectRootEx::InternalQueryInterface](ccomobjectrootex-class.md#internalqueryinterface) возвращает только указателей для интерфейсов COM карты. Запустить интерфейс карты с `BEGIN_COM_MAP` макрос, добавьте записи для каждого из интерфейсов с [COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5) макрос или одного из его вариантов и выполнить сопоставление с [END_COM_MAP](#end_com_map) макрос.  

  
### <a name="example"></a>Пример  
 От библиотеки ATL [BEEPER](../../visual-cpp-samples.md) пример:  
  
 [!code-cpp[NVC_ATL_COM&#1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrymacrosa--cominterfaceentry-macros"></a><a name="com_interface_entry_macros"></a>Макросы COM_INTERFACE_ENTRY  
 Эти макросы введите интерфейсы объекта в его сопоставления COM, чтобы они может осуществляться `QueryInterface`. — Порядок записей сопоставления COM интерфейсы заказа будет проверяться соответствие **IID** во время `QueryInterface`.  
  
##  <a name="a-namecominterfaceentry2x2a--cominterfaceentry2"></a><a name="com_interface_entry2_x2"></a>COM_INTERFACE_ENTRY2  
 Используйте этот макрос для однозначного определения двух ветвей наследования.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя интерфейса, которому требуется предоставить доступ из объекта.  
  
 `x2`  
 [in] Имя ветви наследования, из которой *x* предоставляется.  
  
### <a name="remarks"></a>Примечания  
 Например, если произвести класс объекта из двух сдвоенные интерфейсы можно предоставлять `IDispatch` с помощью `COM_INTERFACE_ENTRY2` поскольку `IDispatch` можно получить в любой из двух интерфейсов.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryiida--cominterfaceentryiid"></a><a name="com_interface_entry_iid"></a>COM_INTERFACE_ENTRY_IID  
 Используйте этот макрос для входа в интерфейс в сопоставление COM и указать его идентификатор IID.  
  
```
COM_INTERFACE_ENTRY_IID(iid, x)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, предоставляемого.  
  
 *x*  
 [in] Имя класса, в которых vtable будет представляться как интерфейс, определяемый `iid`.  
  
### <a name="remarks"></a>Примечания  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#117;](../../atl/codesnippet/cpp/com-map-macros_3.h)]  
  
##  <a name="a-namecominterfaceentry2iida--cominterfaceentry2iid"></a><a name="com_interface_entry2_iid"></a>COM_INTERFACE_ENTRY2_IID  
 То же, что [COM_INTERFACE_ENTRY2](#com_interface_entry2), но можно указать другой идентификатор IID.  
  
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
  
### <a name="remarks"></a>Примечания  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
##  <a name="a-namecominterfaceentry2a--cominterfaceentry2"></a><a name="com_interface_entry2"></a>COM_INTERFACE_ENTRY2  
 Используйте этот макрос для однозначного определения двух ветвей наследования.  
  
```
COM_INTERFACE_ENTRY2(x, x2)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Имя интерфейса, которому требуется предоставить доступ из объекта.  
  
 `x2`  
 [in] Имя ветви наследования, из которой *x* предоставляется.  
  
### <a name="remarks"></a>Примечания  
 Например, если произвести класс объекта из двух сдвоенные интерфейсы можно предоставлять `IDispatch` с помощью `COM_INTERFACE_ENTRY2` поскольку `IDispatch` можно получить в любой из двух интерфейсов.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#118;](../../atl/codesnippet/cpp/com-map-macros_2.h)]  
  
##  <a name="a-namecominterfaceentryaggregate2a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate2"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Если интерфейс определяется `iid` запрашиваются, `COM_INTERFACE_ENTRY_AGGREGATE` пересылает `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, который запрашивается.  
  
 `punk`  
 [in] Имя **IUnknown** указателя.  
  
### <a name="remarks"></a>Примечания  
 `punk` Параметр предполагается указывает внутреннее неизвестно агрегатную функцию или к **NULL**, в этом случае операция учитывается. Как правило, будет **CoCreate** статистического выражения в `FinalConstruct`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryaggregateblinda--cominterfaceentryaggregateblind"></a><a name="com_interface_entry_aggregate_blind"></a>COM_INTERFACE_ENTRY_AGGREGATE_BLIND  
 То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), за исключением того, что запрос любой IID приводит пересылает запрос на `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE_BLIND(punk)
```  
  
### <a name="parameters"></a>Параметры  
 `punk`  
 [in] Имя **IUnknown** указателя.  
  
### <a name="remarks"></a>Примечания  
 Если происходит сбой запроса интерфейса, обработка сопоставления COM продолжается.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#113;](../../atl/codesnippet/cpp/com-map-macros_5.h)]  
  
##  <a name="a-namecominterfaceentryaggregate3a--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate3"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Если интерфейс определяется `iid` запрашиваются, `COM_INTERFACE_ENTRY_AGGREGATE` пересылает `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, который запрашивается.  
  
 `punk`  
 [in] Имя **IUnknown** указателя.  
  
### <a name="remarks"></a>Примечания  
 `punk` Параметр предполагается указывает внутреннее неизвестно агрегатную функцию или к **NULL**, в этом случае операция учитывается. Как правило, будет **CoCreate** статистического выражения в `FinalConstruct`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregatea--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), кроме `punk` — **NULL**, он автоматически создает статистическое выражение, описываемых `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, который запрашивается.  
  
 `punk`  
 [in] Имя **IUnknown** указателя. Необходимо быть членом класса, содержащего сопоставления COM.  
  
 `clsid`  
 [in] Статистическое выражение, которое создается, если идентификатор `punk` — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentryaggregatea--cominterfaceentryaggregate"></a><a name="com_interface_entry_aggregate"></a>COM_INTERFACE_ENTRY_AGGREGATE  
 Если интерфейс определяется `iid` запрашиваются, `COM_INTERFACE_ENTRY_AGGREGATE` пересылает `punk`.  
  
```
COM_INTERFACE_ENTRY_AGGREGATE(iid, punk)
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, который запрашивается.  
  
 `punk`  
 [in] Имя **IUnknown** указателя.  
  
### <a name="remarks"></a>Примечания  
 `punk` Параметр предполагается указывает внутреннее неизвестно агрегатную функцию или к **NULL**, в этом случае операция учитывается. Как правило, будет **CoCreate** статистического выражения в `FinalConstruct`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#112;](../../atl/codesnippet/cpp/com-map-macros_4.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregateblinda--cominterfaceentryautoaggregateblind"></a><a name="com_interface_entry_autoaggregate_blind"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND  
 То же, что [COM_INTERFACE_ENTRY_AUTOAGGREGATE](#com_interface_entry_autoaggregate), за исключением того, что запрос любой IID приводит пересылает запрос на `punk`и если `punk` — **NULL**автоматически создания агрегата, описываемых `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND(punk, clsid)
```  
  
### <a name="parameters"></a>Параметры  
 `punk`  
 [in] Имя **IUnknown** указателя. Необходимо быть членом класса, содержащего сопоставления COM.  
  
 `clsid`  
 [in] Статистическое выражение, которое создается, если идентификатор `punk` — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 Если происходит сбой запроса интерфейса, обработка сопоставления COM продолжается.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#115;](../../atl/codesnippet/cpp/com-map-macros_7.h)]  
  
##  <a name="a-namecominterfaceentryautoaggregate2a--cominterfaceentryautoaggregate"></a><a name="com_interface_entry_autoaggregate2"></a>COM_INTERFACE_ENTRY_AUTOAGGREGATE  
 То же, что [COM_INTERFACE_ENTRY_AGGREGATE](#com_interface_entry_aggregate), кроме `punk` — **NULL**, он автоматически создает статистическое выражение, описываемых `clsid`.  
  
```
COM_INTERFACE_ENTRY_AUTOAGGREGATE(iid, punk, clsid)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, который запрашивается.  
  
 `punk`  
 [in] Имя **IUnknown** указателя. Необходимо быть членом класса, содержащего сопоставления COM.  
  
 `clsid`  
 [in] Статистическое выражение, которое создается, если идентификатор `punk` — **NULL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Windowing&#114;](../../atl/codesnippet/cpp/com-map-macros_6.h)]  
  
##  <a name="a-namecominterfaceentrybreaka--cominterfaceentrybreak"></a><a name="com_interface_entry_break"></a>COM_INTERFACE_ENTRY_BREAK  
 Программа для вызова [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) при запросе указанный интерфейс.  
  
```
COM_INTERFACE_ENTRY_BREAK(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Текст, используемый для создания идентификатора интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Интерфейс IID будут созданы путем добавления *x* в `IID_`. Например если *x* — `IPersistStorage`, IID будет `IID_IPersistStorage`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
##  <a name="a-namecominterfaceentrycachedtearoffa--cominterfaceentrycachedtearoff"></a><a name="com_interface_entry_cached_tear_off"></a>COM_INTERFACE_ENTRY_CACHED_TEAR_OFF  
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
 Если этот интерфейс не используется, это уменьшает общий размер экземпляра объекта.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#54;](../../atl/codesnippet/cpp/com-map-macros_8.h)]  
  
##  <a name="a-namecominterfaceentrytearoffa--cominterfaceentrytearoff"></a><a name="com_interface_entry_tear_off"></a>COM_INTERFACE_ENTRY_TEAR_OFF  
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
 Перемещаемое интерфейс реализуется как отдельный объект, экземпляр которого создается каждый раз, когда интерфейс, он представляет запрашиваются. Как правило построение интерфейса как перемещаемые Если интерфейс используется редко, поскольку это экономит указателя vtable в каждом экземпляре основного объекта. Перемещаемое удаляется, если число ссылок становится равным нулю. Класс, реализующий перемещаемое должен быть получен из `CComTearOffObjectBase` и имеют собственный COM карты.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#1;](../../atl/codesnippet/cpp/com-map-macros_1.h)]  
  
##  <a name="a-namecominterfaceentrychaina--cominterfaceentrychain"></a><a name="com_interface_entry_chain"></a>COM_INTERFACE_ENTRY_CHAIN  
 Обрабатывает сопоставления COM базового класса при обработке достигает этой записи в схеме COM.  
  
```
COM_INTERFACE_ENTRY_CHAIN(classname)
```  
  
### <a name="parameters"></a>Параметры  
 *className*  
 [in] Базовый класс для текущего объекта.  
  
### <a name="remarks"></a>Примечания  
 Например в следующем коде:  
  
 [!code-cpp[NVC_ATL_Windowing&116;](../../atl/codesnippet/cpp/com-map-macros_9.h)]  
  
 Обратите внимание, что первая запись в таблице COM должен быть интерфейсом на объект, содержащий сопоставления COM. Таким образом, не удается запустить записи сопоставления COM с `COM_INTERFACE_ENTRY_CHAIN`, чего сопоставления COM другого объекта для поиска в точке, где **COM_INTERFACE_ENTRY_CHAIN (**`COtherObject`**)** отображается в ваш объект COM карты. Для поиска сопоставления COM другого объекта сначала следует добавить запись интерфейс для **IUnknown** в сопоставление COM, затем цепочку сопоставления COM и другой объект. Например:  
  
 [!code-cpp[NVC_ATL_Windowing&#111;](../../atl/codesnippet/cpp/com-map-macros_10.h)]  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
##  <a name="a-namecominterfaceentryfunc2a--cominterfaceentryfunc"></a><a name="com_interface_entry_func2"></a>COM_INTERFACE_ENTRY_FUNC  
 Общий механизм для прикрепления ATL `QueryInterface` логики.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, предоставляемого.  
  
 `dw`  
 [in] Параметр, передаваемый через `func`.  
  
 `func`  
 [in] Указатель на функцию, которая будет возвращать `iid`.  
  
### <a name="remarks"></a>Примечания  
 Если *iid* соответствующий идентификатор IID интерфейса, запрашивать, а затем функция, заданная параметром `func` вызывается. Объявление функции должно быть:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 При вызове функции `pv` указывает на объект класса. `riid` Параметр ссылается на интерфейс, запрашиваемый, `ppv` — указатель на расположения хранения указателя на интерфейс, в функцию и `dw` — это параметр, указанный в записи. Функция следует установить \* `ppv` для **NULL** и вернуть **E_NOINTERFACE** или **S_FALSE** желанию не для возврата интерфейса. С **E_NOINTERFACE**, завершает обработку карты COM. С **S_FALSE**, COM карты обработка продолжается, даже если был возвращен указатель на интерфейс. Если функция возвращает указатель интерфейса, он должен вернуть `S_OK`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
##  <a name="a-namecominterfaceentryfuncblinda--cominterfaceentryfuncblind"></a><a name="com_interface_entry_func_blind"></a>COM_INTERFACE_ENTRY_FUNC_BLIND  
 То же, что [COM_INTERFACE_ENTRY_FUNC](#com_interface_entry_func), за исключением того, что запрос любой IID приводит к вызову для `func`.  
  
```
COM_INTERFACE_ENTRY_FUNC_BLIND(dw, func)
```  
  
### <a name="parameters"></a>Параметры  
 `dw`  
 [in] Параметр, передаваемый через `func`.  
  
 `func`  
 [in] Функция, которая вызывается при обработке этой записи в схеме COM.  
  
### <a name="remarks"></a>Примечания  
 Любой сбой вызовет на карте COM продолжение обработки. Если функция возвращает указатель интерфейса, он должен вернуть `S_OK`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
##  <a name="a-namecominterfaceentryfunca--cominterfaceentryfunc"></a><a name="com_interface_entry_func"></a>COM_INTERFACE_ENTRY_FUNC  
 Общий механизм для прикрепления ATL `QueryInterface` логики.  
  
```
COM_INTERFACE_ENTRY_FUNC(iid, dw, func)
```   
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID интерфейса, предоставляемого.  
  
 `dw`  
 [in] Параметр, передаваемый через `func`.  
  
 `func`  
 [in] Указатель на функцию, которая будет возвращать `iid`.  
  
### <a name="remarks"></a>Примечания  
 Если *iid* соответствующий идентификатор IID интерфейса, запрашивать, а затем функция, заданная параметром `func` вызывается. Объявление функции должно быть:  
  
 `HRESULT WINAPI func(void* pv, REFIID riid, LPVOID* ppv, DWORD_PTR dw);`  
  
 При вызове функции `pv` указывает на объект класса. `riid` Параметр ссылается на интерфейс, запрашиваемый, `ppv` — указатель на расположения хранения указателя на интерфейс, в функцию и `dw` — это параметр, указанный в записи. Функция следует установить \* `ppv` для **NULL** и вернуть **E_NOINTERFACE** или **S_FALSE** желанию не для возврата интерфейса. С **E_NOINTERFACE**, завершает обработку карты COM. С **S_FALSE**, COM карты обработка продолжается, даже если был возвращен указатель на интерфейс. Если функция возвращает указатель интерфейса, он должен вернуть `S_OK`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
##  <a name="a-namecominterfaceentrynointerfacea--cominterfaceentrynointerface"></a><a name="com_interface_entry_nointerface"></a>COM_INTERFACE_ENTRY_NOINTERFACE  
 Возвращает **E_NOINTERFACE** и завершает обработку карты COM, когда запрашиваются указанный интерфейс.  
  
```
COM_INTERFACE_ENTRY_NOINTERFACE(x)
```  
  
### <a name="parameters"></a>Параметры  
 *x*  
 [in] Текст, используемый для создания идентификатора интерфейса.  
  
### <a name="remarks"></a>Примечания  
 Этот макрос можно использовать для предотвращения использования в конкретном случае интерфейс. Например, этот макрос можно вставить в ваш COM сопоставить прямо перед `COM_INTERFACE_ENTRY_AGGREGATE_BLIND` для предотвращения пересылки неизвестно внутреннее статистическое выражение запроса для интерфейса.  
  
 Интерфейс IID будут созданы путем добавления *x* в `IID_`. Например если *x* — `IPersistStorage`, IID будет `IID_IPersistStorage`.  
  
 В разделе [Макросы COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/19dcb768-2e1f-4b8d-a618-453a01a4bd00) примечания о COM записей сопоставления.  
  
##  <a name="a-nameendcommapa--endcommap"></a><a name="end_com_map"></a>END_COM_MAP  
 Завершает определение сопоставление COM интерфейс.  
  
```
END_COM_MAP()
```  
  
## <a name="see-also"></a>См. также  
 [Макросы](../../atl/reference/atl-macros.md)   
 [Глобальные функции сопоставления COM](../../atl/reference/com-map-global-functions.md)

