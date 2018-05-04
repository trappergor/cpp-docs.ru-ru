---
title: Класс CComObjectStack | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComObjectStack
- ATLCOM/ATL::CComObjectStack
- ATLCOM/ATL::CComObjectStack::CComObjectStack
- ATLCOM/ATL::CComObjectStack::AddRef
- ATLCOM/ATL::CComObjectStack::QueryInterface
- ATLCOM/ATL::CComObjectStack::Release
- ATLCOM/ATL::CComObjectStack::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectStack class
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac37ac5abc193082aaccb8d5de1a4f75f8a3f7c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomobjectstack-class"></a>Класс CComObjectStack
Этот класс создает временный объект COM и обеспечивает его с базовой реализацией **IUnknown**.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class  Base>  
class CComObjectStack
 : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любого другого интерфейса, которые требуется поддерживать на объект.  
  
## <a name="members"></a>Участники  
  
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
 `CComObjectStack` используется для создания временных объектов COM и предоставить объект базовой реализации **IUnknown**. Объект, как правило, используется как локальная переменная в пределах одной функции (которая помещается в стек). Так как данный объект удаляется после завершения работы функции, подсчет ссылок не выполняется для повышения эффективности.  
  
 Приведенный ниже показано, как создать объект COM, который используется внутри функции:  
  
 [!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/cpp/ccomobjectstack-class_1.cpp)]  
  
 Временный объект `Tempobj` помещается в стек и автоматически исчезает после завершения работы функции.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComObjectStack`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>  CComObjectStack::AddRef  
 Возвращает ноль.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ноль.  
  
### <a name="remarks"></a>Примечания  
 В режиме отладки, вызывает `_ASSERTE`.  
  
##  <a name="ccomobjectstack"></a>  CComObjectStack::CComObjectStack  
 Конструктор.  
  
```
CComObjectStack(void* = NULL);
```  
  
### <a name="remarks"></a>Примечания  
 Вызовы `FinalConstruct` , а затем задает [m_hResFinalConstruct](#m_hresfinalconstruct) для `HRESULT` возвращенных `FinalConstruct`. Если не иметь производные от базового класса [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), вы должны предоставить свои собственные `FinalConstruct` метод. Деструктор вызывает `FinalRelease`.  
  
##  <a name="dtor"></a>  CComObjectStack:: ~ CComObjectStack  
 Деструктор  
  
```
CComObjectStack();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы и вызывает метод [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>  CComObjectStack::m_hResFinalConstruct  
 Содержит `HRESULT` возвращаемый вызовом `FinalConstruct` при построении `CComObjectStack` объекта.  
  
```
HRESULT    m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>  CComObjectStack::QueryInterface  
 Возвращает **E_NOINTERFACE**.  
  
```
HRESULT    QueryInterface(REFIID, void**)
 ;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOINTERFACE**.  
  
### <a name="remarks"></a>Примечания  
 В режиме отладки, вызывает `_ASSERTE`.  
  
##  <a name="release"></a>  CComObjectStack::Release  
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
