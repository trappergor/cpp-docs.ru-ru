---
title: "Класс CComPolyObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPolyObject
- ATLCOM/ATL::CComPolyObject
- ATLCOM/ATL::CComPolyObject::CComPolyObject
- ATLCOM/ATL::CComPolyObject::AddRef
- ATLCOM/ATL::CComPolyObject::CreateInstance
- ATLCOM/ATL::CComPolyObject::FinalConstruct
- ATLCOM/ATL::CComPolyObject::FinalRelease
- ATLCOM/ATL::CComPolyObject::QueryInterface
- ATLCOM/ATL::CComPolyObject::Release
- ATLCOM/ATL::CComPolyObject::m_contained
dev_langs: C++
helpviewer_keywords:
- aggregate objects [C++], in ATL
- aggregation [C++], ATL objects
- CComPolyObject class
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 49945127d726c1a83ed01f70dee2190622a4c68d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="ccompolyobject-class"></a>Класс CComPolyObject
Этот класс реализует **IUnknown** для суммирования или неагрегированные объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class contained>  
class CComPolyObject : public IUnknown,
      public CComObjectRootEx<contained::_ThreadModel::ThreadModelNoCS>
```  
  
#### <a name="parameters"></a>Параметры  
 `contained`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любых других интерфейсов, которые требуется поддерживать на объект.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPolyObject::CComPolyObject](#ccompolyobject)|Конструктор.|  
|[CComPolyObject:: ~ CComPolyObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPolyObject::AddRef](#addref)|Увеличивает значение счетчика ссылок объекта.|  
|[CComPolyObject::CreateInstance](#createinstance)|(Статический) Позволяет создать новый **CComPolyObject <** `contained`  **>**  объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComPolyObject::FinalConstruct](#finalconstruct)|Выполняет окончательной инициализации `m_contained`.|  
|[CComPolyObject::FinalRelease](#finalrelease)|Выполняет окончательного удаления `m_contained`.|  
|[CComPolyObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComPolyObject::Release](#release)|Уменьшает значение счетчика ссылок объекта.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPolyObject::m_contained](#m_contained)|Делегаты **IUnknown** вызывает внешняя Неизвестная строка, если объект является статистическим выражением, или для **IUnknown** объекта, если объект не является статистическим выражением.|  
  
## <a name="remarks"></a>Примечания  
 `CComPolyObject`реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) для суммирования или неагрегированные объекта.  
  
 При создании экземпляра `CComPolyObject` создается значение внешнего проверяется unknown. Если это **NULL**, **IUnknown** реализуется для неагрегированные объекта. Если внешняя Неизвестная строка не **NULL**, **IUnknown** реализуется для вычисляемого объекта.  
  
 Преимущество использования `CComPolyObject` — избежать обладает и разрешением [CComAggObject](../../atl/reference/ccomaggobject-class.md) и [CComObject](../../atl/reference/ccomobject-class.md) в модуле для обработки случаев, статистические и нестатистические. Один `CComPolyObject` объект обрабатывает в обоих случаях. Это означает, что существуют только одна копия виртуальной таблице и одной копии функций в модуле. При большом вашей vtable это существенно уменьшить размер вашего модуля. Тем не менее, используемой при небольших вашей vtable `CComPolyObject` может привести к немного больший размер модуля, так как он не оптимизирован для суммирования или неагрегированные объекта, как `CComAggObject` и `CComObject`.  
  
 Если `DECLARE_POLY_AGGREGATABLE` макрос, указанный в определении класса объекта, `CComPolyObject` будет использоваться для создания объекта. `DECLARE_POLY_AGGREGATABLE`будет автоматически объявлено при использовании мастера проектов ATL для создания полного доступа или управления Internet Explorer.  
  
 Если статистическим выражением, `CComPolyObject` объект имеет свой собственный **IUnknown**, отдельно от внешнего объекта **IUnknown**и хранит число ссылок. `CComPolyObject`использует [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) делегировать внешняя Неизвестная строка.  
  
 Дополнительные сведения о статистической обработки см. в статье [основы объекта ATL COM-объекты](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="addref"></a>CComPolyObject::AddRef  
 Увеличивает счетчик ссылок на объект.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение, которое может быть полезно для диагностики и тестирования.  
  
##  <a name="ccompolyobject"></a>CComPolyObject::CComPolyObject  
 Конструктор.  
  
```
CComPolyObject(void* pv);
```  
  
### <a name="parameters"></a>Параметры  
 `pv`  
 [in] Указатель на внешняя Неизвестная статистической обработки, если объект или **NULL** Если объект, если объект не является статистическим выражением.  
  
### <a name="remarks"></a>Примечания  
 Инициализирует `CComContainedObject` данные-член [m_contained](#m_contained)и увеличивает счетчик блокировки модуля.  
  
 Деструктор уменьшает счетчик блокировки модуля.  
  
##  <a name="dtor"></a>CComPolyObject:: ~ CComPolyObject  
 Деструктор  
  
```
~CComPolyObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы, вызовы [FinalRelease](#finalrelease), и уменьшает счетчик блокировки модуля.  
  
##  <a name="createinstance"></a>CComPolyObject::CreateInstance  
 Позволяет создать новый **CComPolyObject <** `contained`  **>**  объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(  
    LPUNKNOWN pUnkOuter, 
    CComPolyObject<contained>** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `pp`  
 [out] Указатель на **CComPolyObject <** `contained`  **>**  указателя. Если `CreateInstance` завершается неудачно, `pp` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый объект имеет нулевое число ссылок, поэтому вызовов `AddRef` немедленно, воспользуйтесь **выпуска** освободить ссылку на указатель на объект после завершения.  
  
 Если не требуется прямой доступ к объекту, но все равно хотите создать новый объект без необходимости проведения `CoCreateInstance`, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо него.  
  
##  <a name="finalconstruct"></a>CComPolyObject::FinalConstruct  
 Вызывается во время последних этапов создания объекта, этот метод выполняет инициализацию окончательного [m_contained](#m_contained) члена данных.  
  
```
HRESULT FinalConstruct();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
##  <a name="finalrelease"></a>CComPolyObject::FinalRelease  
 Вызывается при уничтожении объекта, этот метод освобождает [m_contained](#m_contained) члена данных.  
  
```
void FinalRelease();
```  
  
##  <a name="m_contained"></a>CComPolyObject::m_contained  
 Объект [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) объект, производный от класса.  
  
```
CComContainedObject<contained> m_contained;
```  
  
### <a name="parameters"></a>Параметры  
 `contained`  
 [in] Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), также как и из любых других интерфейсов, которые требуется поддерживать на объект.  
  
### <a name="remarks"></a>Примечания  
 **IUnknown** вызывается с помощью `m_contained` делегируются внешняя Неизвестная строка, если объект является статистическим выражением, или **IUnknown** этого объекта, если объект не является статистическим выражением.  
  
##  <a name="queryinterface"></a>CComPolyObject::QueryInterface  
 Извлекает указатель на запрошенный интерфейс.  
  
```
STDMETHOD(QueryInterface)(REFIID iid, void** ppvObject);
template <class Q>  
HRESULT QueryInterface(Q** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `Q`  
 COM-интерфейса.  
  
 `iid`  
 [in] Идентификатор запрашиваемого интерфейса.  
  
 `ppvObject`  
 [out] Указатель на указатель на интерфейс, определяемый `iid`. Если объект не поддерживает этот интерфейс `ppvObject` равно **NULL**.  
  
 `pp`  
 [out] Указатель на интерфейс, определенный **__uuidof(Q)**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Для вычисляемого объекта, если запрошенный интерфейс **IUnknown**, `QueryInterface` возвращает указатель на статистические объекта собственные **IUnknown** и увеличивает счетчик ссылок. В противном случае этот метод запрашивает интерфейс через `CComContainedObject` данные-член [m_contained](#m_contained).  
  
##  <a name="release"></a>CComPolyObject::Release  
 Уменьшает счетчик ссылок на объект.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 В отладочных построениях **выпуска** возвращает значение, которое может быть полезно для диагностики и тестирования. В сборках отладки **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [CComObjectRootEx-класс](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE_POLY_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_poly_aggregatable)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
