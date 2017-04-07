---
title: "Класс CComObjectNoLock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::CComObjectNoLock
- ATLCOM/ATL::CComObjectNoLock::AddRef
- ATLCOM/ATL::CComObjectNoLock::QueryInterface
- ATLCOM/ATL::CComObjectNoLock::Release
dev_langs:
- C++
helpviewer_keywords:
- CComObjectNoLock class
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
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
ms.openlocfilehash: 4cf4cad1a3b1a4ac0a21ef76a0eaca35732abf3a
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobjectnolock-class"></a>Класс CComObjectNoLock
Этот класс реализует **IUnknown** для неагрегированные объекта, но не не приращения счетчик блокировок модуля в конструкторе.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class Base>  
class CComObjectNoLock : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любого другого интерфейса, которую требуется поддерживать на объект.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](#ccomobjectnolock)|Конструктор.|  
|[CComObjectNoLock:: ~ CComObjectNoLock](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObjectNoLock::AddRef](#addref)|Увеличивает значение счетчика ссылок на объект.|  
|[CComObjectNoLock::QueryInterface](#queryinterface)|Возвращает указатель на запрошенный интерфейс.|  
|[CComObjectNoLock::Release](#release)|Уменьшает счетчик ссылок на объект.|  
  
## <a name="remarks"></a>Примечания  
 `CComObjectNoLock`Аналогично [CComObject](../../atl/reference/ccomobject-class.md) в том, что он реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) неагрегированные объекта; Однако `CComObjectNoLock` выполняет подсчет приращения блокировки модуля в конструкторе.  
  
 Использует ATL `CComObjectNoLock` внутренне для фабрики классов. Как правило вы не будет использовать этот класс непосредственно.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComObjectNoLock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="addref"></a>CComObjectNoLock::AddRef  
 Увеличивает значение счетчика ссылок на объект.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="ccomobjectnolock"></a>CComObjectNoLock::CComObjectNoLock  
 Конструктор. В отличие от [CComObject](../../atl/reference/ccomobject-class.md), не увеличивает счетчик блокировки модуля.  
  
```
CComObjectNoLock(void* = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 **void\***  
 [in] Это Неименованный параметр не используется. Он существует для симметрии с другими **CCom***XXX*`Object`*XXX* конструкторы.  
  
##  <a name="dtor"></a>CComObjectNoLock:: ~ CComObjectNoLock  
 Деструктор  
  
```
~CComObjectNoLock();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы и вызывает [FinalRelease](ccomobjectrootex-class.md#finalrelease).  

  
##  <a name="queryinterface"></a>CComObjectNoLock::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, идентифицируемый `iid`. Если объект не поддерживает этот интерфейс `ppvObject` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="release"></a>CComObjectNoLock::Release  
 Уменьшает счетчик ссылок на объект.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В сборках неотладочные **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

