---
title: "Класс CComObjectGlobal | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::CComObjectGlobal
- ATLCOM/ATL::CComObjectGlobal::AddRef
- ATLCOM/ATL::CComObjectGlobal::QueryInterface
- ATLCOM/ATL::CComObjectGlobal::Release
- ATLCOM/ATL::CComObjectGlobal::m_hResFinalConstruct
dev_langs:
- C++
helpviewer_keywords:
- CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 8c371eee9de660a2bb08e67f35a5a6c81d32eee0
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectglobal-class"></a>Класс CComObjectGlobal
Этот класс управляет значение счетчика ссылок на модуль, содержащий ваш `Base` объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class Base>
class CComObjectGlobal : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любого другого интерфейса, которую требуется поддерживать на объект.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Конструктор.|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|Реализует глобальный `AddRef`.|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|Реализует глобальный `QueryInterface`.|  
|[CComObjectGlobal::Release](#release)|Реализует глобальный **версии**.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Содержит **HRESULT** возвращается при построении `CComObjectGlobal` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CComObjectGlobal`Управляет значение счетчика ссылок на модуль, содержащий ваш `Base` объекта. `CComObjectGlobal`гарантирует, что объект не удаляется до тех пор, пока модуль не будет освобожден. Объект будет удален только в том случае, если счетчик ссылок на весь модуль становится равным нулю.  
  
 Например, с помощью `CComObjectGlobal`, фабрика классов может содержать глобальный объект, общих для всех своих клиентов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="addref"></a>CComObjectGlobal::AddRef  
 Увеличивает счетчик ссылок объекта на 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `AddRef` вызовов **_Module::Lock**, где **_Module** — глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.  
  
##  <a name="ccomobjectglobal"></a>CComObjectGlobal::CComObjectGlobal  
 Конструктор. Вызовы `FinalConstruct` , а затем присваивает [m_hResFinalConstruct](#m_hresfinalconstruct) для `HRESULT` возвращаемый `FinalConstruct`.  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>Примечания  
 Если не иметь производные от базового класса [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), необходимо предоставить свои собственные `FinalConstruct` метод. Деструктор вызывает `FinalRelease`.  
  
##  <a name="dtor"></a>CComObjectGlobal:: ~ CComObjectGlobal  
 Деструктор  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы и вызывает [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct  
 Содержит `HRESULT` из телефонной `FinalConstruct` во время создания `CComObjectGlobal` объекта.  
  
```
HRESULT m_hResFinalConstruct;
```  
  
##  <a name="queryinterface"></a>CComObjectGlobal::QueryInterface  
 Извлекает указатель на указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор GUID запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, идентифицируемый iid, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 `QueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM.  
  
##  <a name="release"></a>CComObjectGlobal::Release  
 Уменьшает счетчик ссылок объекта на 1.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В сборках неотладочные **выпуска** всегда возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию **выпуска** вызовов **_Module::Unlock**, где **_Module** — глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.  
  
## <a name="see-also"></a>См. также  
 [Класс CComObjectStack](../../atl/reference/ccomobjectstack-class.md)   
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

