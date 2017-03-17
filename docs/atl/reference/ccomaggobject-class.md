---
title: "Класс CComAggObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAggObject
- ATLCOM/ATL::CComAggObject
- ATLCOM/ATL::CComAggObject::CComAggObject
- ATLCOM/ATL::CComAggObject::AddRef
- ATLCOM/ATL::CComAggObject::CreateInstance
- ATLCOM/ATL::CComAggObject::FinalConstruct
- ATLCOM/ATL::CComAggObject::FinalRelease
- ATLCOM/ATL::CComAggObject::QueryInterface
- ATLCOM/ATL::CComAggObject::Release
- ATLCOM/ATL::CComAggObject::m_contained
dev_langs:
- C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComAggObject class
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 386ab09418c879c0de0d82d729a3de1b2e270016
ms.lasthandoff: 02/24/2017

---
# <a name="ccomaggobject-class"></a>Класс CComAggObject
Этот класс реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейс для вычисляемого объекта. По определению вычисляемого объекта внутри внешнего объекта. `CComAggObject` Класс похож на [CComObject класса](../../atl/reference/ccomobject-class.md), за исключением того, что он предоставляет интерфейс, который доступен непосредственно для внешних клиентов.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class contained>  
class CComAggObject : public IUnknown, 
   public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Параметры  
 `contained`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), как хорошо от любых других интерфейсов, которую требуется поддерживать на объект.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAggObject::CComAggObject](#ccomaggobject)|Конструктор.|  
|[CComAggObject:: ~ CComAggObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAggObject::AddRef](#addref)|Увеличивает значение счетчика ссылок на объект статистические.|  
|[CComAggObject::CreateInstance](#createinstance)|Эта статическая функция позволяет создать новую **CComAggObject** `contained` ** > ** объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](#finalconstruct)|Выполняет инициализацию окончательный `m_contained`.|  
|[CComAggObject::FinalRelease](#finalrelease)|Выполняет удаление последней `m_contained`.|  
|[CComAggObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComAggObject::Release](#release)|Уменьшает счетчик ссылок на объект статистические.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComAggObject::m_contained](#m_contained)|Делегаты `IUnknown` вызовы внешняя Неизвестная строка.|  
  
## <a name="remarks"></a>Примечания  
 `CComAggObject`реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) для вычисляемого объекта. `CComAggObject`имеет свой собственный **IUnknown** интерфейс, отдельно от внешнего объекта **IUnknown** интерфейс и сохраняет число ссылок.  
  
 Дополнительные сведения о статистической обработке см. в статье [основы ATL COM объектов](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="addref"></a>CComAggObject::AddRef  
 Увеличивает значение счетчика ссылок на объект статистические.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="ccomaggobject"></a>CComAggObject::CComAggObject  
 Конструктор.  
  
```
CComAggObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 [in] Внешняя Неизвестная строка.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CComContainedObject` член, [m_contained](#m_contained)и увеличивает счетчик блокировки модуля.  
  
 Деструктор уменьшает счетчик блокировок модуля.  
  
##  <a name="dtor"></a>CComAggObject:: ~ CComAggObject  
 Деструктор  
  
```
~CComAggObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы, вызовы [FinalRelease](#finalrelease), и уменьшает счетчик блокировки модуля.  
  
##  <a name="createinstance"></a>CComAggObject::CreateInstance  
 Эта статическая функция позволяет создать новую **CComAggObject** `contained` ** > ** объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(
    LPUNKNOWN pUnkOuter,
    CComAggObject<contained>** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `pp`  
 [out] Указатель на **CComAggObject\<***содержится* ** > ** указателя. Если `CreateInstance` завершается неудачно, `pp` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый объект имеет нулевое число ссылок, поэтому вызов `AddRef` немедленно, воспользуйтесь **выпуска** освободить ссылку на указатель объекта после завершения.  
  
 Если не требуется прямой доступ к объекту, но по-прежнему необходимо создать новый объект без использования `CoCreateInstance`, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо.  
  
##  <a name="finalconstruct"></a>CComAggObject::FinalConstruct  
 Вызывается во время последних этапов создания объекта, этот метод выполняет инициализацию окончательный [m_contained](#m_contained) член.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="finalrelease"></a>CComAggObject::FinalRelease  
 Вызывается во время удаления объекта, этот метод освобождает [m_contained](#m_contained) член.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComAggObject::m_contained  
 Объект [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) объект, производный от класса.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Параметры  
 `contained`  
 [in] Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), как хорошо от любых других интерфейсов, которую требуется поддерживать на объект.  
  
### <a name="remarks"></a>Примечания  
 Все **IUnknown** вызывается с помощью `m_contained` делегируются внешнего неизвестно.  
  
##  <a name="queryinterface"></a>CComAggObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>
HRESULT STDMETHODCALLTYPE QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `iid`  
 [in] Идентификатор запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель интерфейса, идентифицируемый `iid`. Если объект не поддерживает этот интерфейс `ppvObject` равен **NULL**.  
  
 `pp`  
 [out] Указатель на указатель интерфейса, определенный по типу `Q`. Если объект не поддерживает этот интерфейс `pp` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если запрошенный интерфейс **IUnknown**, `QueryInterface` возвращает объединенные объекта собственный указатель **IUnknown** и увеличивает значение счетчика ссылок. В противном случае, этот метод запрашивает интерфейс через `CComContainedObject` член, [m_contained](#m_contained).  
  
##  <a name="release"></a>CComAggObject::Release  
 Уменьшает счетчик ссылок на объект статистические.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В сборках неотладочные **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Класс CComObject](../../atl/reference/ccomobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_ONLY_AGGREGATABLE](http://msdn.microsoft.com/library/a54220df-4330-4e4d-b7fb-8b63dd62d337)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

