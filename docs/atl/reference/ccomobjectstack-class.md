---
title: "Класс CComObjectStack | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CComObjectStack
- ATL.CComObjectStack
- ATL::CComObjectStack<Base>
- ATL.CComObjectStack<Base>
- CComObjectStack
dev_langs:
- C++
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: 19
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
ms.openlocfilehash: 0738eae13fdca5906596194016ce22812fbfcd36
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectstack-class"></a>Класс CComObjectStack
Этот класс создает временный объект COM и предоставляет его с базовой реализацией **IUnknown**.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любого другого интерфейса, которую требуется поддерживать на объект.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectStack::CComObjectStack](#ccomobjectstack)|Конструктор.|  
|[CComObjectStack:: ~ CComObjectStack](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectStack::AddRef](#addref)|Возвращает ноль. В режиме отладки, вызывает `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](#queryinterface)|Возвращает **E_NOINTERFACE**. В режиме отладки, вызывает `_ASSERTE`.|  
|[CComObjectStack::Release](#release)|Возвращает ноль. В режиме отладки, вызывает `_ASSERTE`. ~|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectStack::m_hResFinalConstruct](#m_hresfinalconstruct)|Содержит **HRESULT** возвращается при построении `CComObjectStack` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CComObjectStack`используется для создания временных объектов COM и предоставить объект базовой реализации **IUnknown**. Как правило объект используется как локальная переменная в одну функцию (которая помещается в стек). Поскольку объект уничтожается после завершения работы функции, подсчет ссылок не выполняется для повышения эффективности.  
  
 Приведенный ниже показано, как создать объект COM, который используется внутри функции:  
  
 [!code-cpp[NVC_ATL_COM&#42;](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 Временный объект `Tempobj` помещается в стек и автоматически удаляется после завершения работы функции.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameaddrefa--ccomobjectstackaddref"></a><a name="addref"></a>CComObjectStack::AddRef  
 Возвращает ноль.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ноль.  
  
### <a name="remarks"></a>Примечания  
 В режиме отладки, вызывает `_ASSERTE`.  
  
##  <a name="a-nameccomobjectstacka--ccomobjectstackccomobjectstack"></a><a name="ccomobjectstack"></a>CComObjectStack::CComObjectStack  
 Конструктор.  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы `FinalConstruct` , а затем присваивает [m_hResFinalConstruct](#m_hresfinalconstruct) для `HRESULT` возвращаемый `FinalConstruct`. Если не иметь производные от базового класса [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), необходимо предоставить свои собственные `FinalConstruct` метод. Деструктор вызывает `FinalRelease`.  
  
##  <a name="a-namedtora--ccomobjectstackccomobjectstack"></a><a name="dtor"></a>CComObjectStack:: ~ CComObjectStack  
 Деструктор  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы и вызывает [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="a-namemhresfinalconstructa--ccomobjectstackmhresfinalconstruct"></a><a name="m_hresfinalconstruct"></a>CComObjectStack::m_hResFinalConstruct  
 Содержит `HRESULT` возвращаемый вызовом `FinalConstruct` во время создания `CComObjectStack` объекта.  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="a-namequeryinterfacea--ccomobjectstackqueryinterface"></a><a name="queryinterface"></a>CComObjectStack::QueryInterface  
 Возвращает **E_NOINTERFACE**.  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOINTERFACE**.  
  
### <a name="remarks"></a>Примечания  
 В режиме отладки, вызывает `_ASSERTE`.  
  
##  <a name="a-namereleasea--ccomobjectstackrelease"></a><a name="release"></a>CComObjectStack::Release  
 Возвращает ноль.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ноль.  
  
### <a name="remarks"></a>Примечания  
 В режиме отладки, вызывает `_ASSERTE`.  
  
## <a name="see-also"></a>См. также  
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

