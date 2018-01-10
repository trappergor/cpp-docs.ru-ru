---
title: "Класс CComObjectGlobal | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
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
dev_langs: C++
helpviewer_keywords: CComObjectGlobal class
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8d5264a2ab8e1bbc4c3f4eac4d83d096d91e8846
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любого другого интерфейса, которые требуется поддерживать на объект.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](#ccomobjectglobal)|Конструктор.|  
|[CComObjectGlobal:: ~ CComObjectGlobal](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComObjectGlobal::AddRef](#addref)|Реализует глобальную `AddRef`.|  
|[CComObjectGlobal::QueryInterface](#queryinterface)|Реализует глобальную `QueryInterface`.|  
|[CComObjectGlobal::Release](#release)|Реализует глобальную **выпуска**.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComObjectGlobal::m_hResFinalConstruct](#m_hresfinalconstruct)|Содержит **HRESULT** возвращается при построении `CComObjectGlobal` объекта.|  
  
## <a name="remarks"></a>Примечания  
 `CComObjectGlobal`Управляет значение счетчика ссылок на модуль, содержащий ваш `Base` объекта. `CComObjectGlobal`гарантирует, что объект не удаляется до тех пор, пока модуль не освобождается. Объект будет удален только в том случае, когда счетчик ссылок на весь модуль становится равен нулю.  
  
 Например, с помощью `CComObjectGlobal`, фабрика класса может содержать общие глобальный объект, который является общим для всех своих клиентов.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComObjectGlobal`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>CComObjectGlobal::AddRef  
 Увеличивает счетчик ссылок объекта, на 1.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию `AddRef` вызовы **_Module::Lock**, где **_Module** — это глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.  
  
##  <a name="ccomobjectglobal"></a>CComObjectGlobal::CComObjectGlobal  
 Конструктор. Вызовы `FinalConstruct` , а затем задает [m_hResFinalConstruct](#m_hresfinalconstruct) для `HRESULT` возвращенных `FinalConstruct`.  
  
```
CComObjectGlobal(void* = NULL));
```  
  
### <a name="remarks"></a>Примечания  
 Если не иметь производные от базового класса [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md), вы должны предоставить свои собственные `FinalConstruct` метод. Деструктор вызывает `FinalRelease`.  
  
##  <a name="dtor"></a>CComObjectGlobal:: ~ CComObjectGlobal  
 Деструктор  
  
```
CComObjectGlobal();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы и вызывает метод [FinalRelease](ccomobjectrootex-class.md#finalrelease).  
  
##  <a name="m_hresfinalconstruct"></a>CComObjectGlobal::m_hResFinalConstruct  
 Содержит `HRESULT` от вызова `FinalConstruct` при построении `CComObjectGlobal` объекта.  
  
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
 [out] Указатель на указатель интерфейса, определенный с iid, или **NULL** Если интерфейс не найден.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 `QueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM.  
  
##  <a name="release"></a>CComObjectGlobal::Release  
 Уменьшает счетчик ссылок объекта, на 1.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В неотладочных сборках **выпуска** всегда возвращает значение 0.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию **выпуска** вызовы **_Module::Unlock**, где **_Module** — это глобальный экземпляр [CComModule](../../atl/reference/ccommodule-class.md) или класс, производный от него.  
  
## <a name="see-also"></a>См. также  
 [Класс CComObjectStack](../../atl/reference/ccomobjectstack-class.md)   
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
