---
title: "Класс CComObject | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComObject<Base>
- ATL::CComObject
- ATL::CComObject<Base>
- ATL.CComObject
- CComObject
dev_langs:
- C++
helpviewer_keywords:
- CComObject class
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5f752b96d4a722fbddfcc9e5be3a82b8b12a86a1
ms.lasthandoff: 02/24/2017

---
# <a name="ccomobject-class"></a>Класс CComObject
Этот класс реализует **IUnknown** нестатистические объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class Base>  
class CComObject : public Base
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Класс, производный от [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) или [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), как хорошо от любых других интерфейсов, которую требуется поддерживать на объект.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObject::CComObject](#ccomobject)|Конструктор.|  
|[CComObject:: ~ CComObject](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComObject::AddRef](#addref)|Увеличивает значение счетчика ссылок на объект.|  
|[CComObject::CreateInstance](#createinstance)|(Статический) Создает новый `CComObject` объекта.|  
|[CComObject::QueryInterface](#queryinterface)|Извлекает указатель на запрошенный интерфейс.|  
|[CComObject::Release](#release)|Уменьшает счетчик ссылок на объект.|  
  
## <a name="remarks"></a>Примечания  
 `CComObject`реализует [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) нестатистические объекта. Однако вызовы `QueryInterface`, `AddRef`, и **выпуска** делегируются `CComObjectRootEx`.  
  
 Дополнительные сведения об использовании `CComObject`, см. в статье [основы ATL COM объектов](../../atl/fundamentals-of-atl-com-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `Base`  
  
 `CComObject`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameaddrefa--ccomobjectaddref"></a><a name="addref"></a>CComObject::AddRef  
 Увеличивает значение счетчика ссылок на объект.  
  
```
STDMETHOD_(ULONG, AddRef)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает новый счетчик ссылок увеличивается на объект. Это значение может быть полезен для диагностики и тестирования.  
  
##  <a name="a-nameccomobjecta--ccomobjectccomobject"></a><a name="ccomobject"></a>CComObject::CComObject  
 Конструктор увеличивает счетчик блокировки модуля.  
  
```
CComObject(void* = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 **void\***  
 [in] Это Неименованный параметр не используется. Он существует для симметрии с другими **CCom***XXX*`Object`*XXX* конструкторы.  
  
### <a name="remarks"></a>Примечания  
 Деструктор уменьшает его.  
  
 Если `CComObject`-успешно производного объекта создается с помощью **новый** оператор, начальное значение счетчика ссылок равно 0. Значение счетчика ссылок соответствующее значение (1), чтобы вызов [AddRef](#addref) функции.  
  
##  <a name="a-namedtora--ccomobjectccomobject"></a><a name="dtor"></a>CComObject:: ~ CComObject  
 Деструктор  
  
```
CComObject();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы, вызовы [FinalRelease](ccomobjectrootex-class.md#finalrelease), и уменьшает счетчик блокировки модуля.  

  
##  <a name="a-namecreateinstancea--ccomobjectcreateinstance"></a><a name="createinstance"></a>CComObject::CreateInstance  
 Эта статическая функция позволяет создать новую **CComObject** `Base` ** > ** объекта без использования [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).  
  
```
static HRESULT WINAPI CreateInstance(CComObject<Base>** pp);
```  
  
### <a name="parameters"></a>Параметры  
 `pp`  
 [out] Указатель на **CComObject** `Base` ** > ** указателя. Если `CreateInstance` завершается неудачно, `pp` равен **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Возвращаемый объект имеет нулевое число ссылок, поэтому вызов `AddRef` немедленно, воспользуйтесь **выпуска** освободить ссылку на указатель объекта после завершения.  
  
 Если не требуется прямой доступ к объекту, но по-прежнему необходимо создать новый объект без использования `CoCreateInstance`, используйте [CComCoClass::CreateInstance](../../atl/reference/ccomcoclass-class.md#createinstance) вместо.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_COM&#38;](../../atl/codesnippet/cpp/ccomobject-class_1.h)]  
  
 [!code-cpp[NVC_ATL_COM&#39;](../../atl/codesnippet/cpp/ccomobject-class_2.cpp)]  
  
##  <a name="a-namequeryinterfacea--ccomobjectqueryinterface"></a><a name="queryinterface"></a>CComObject::QueryInterface  
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
  
##  <a name="a-namereleasea--ccomobjectrelease"></a><a name="release"></a>CComObject::Release  
 Уменьшает счетчик ссылок на объект.  
  
```
STDMETHOD_(ULONG, Release)();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Эта функция возвращает новый счетчик ссылок уменьшается на единицу для объекта. В отладочных построениях возвращаемое значение может быть полезно для диагностики или тестирования. В сборках неотладочные **выпуска** всегда возвращает значение 0.  
  
## <a name="see-also"></a>См. также  
 [Класс CComAggObject](../../atl/reference/ccomaggobject-class.md)   
 [Класс CComPolyObject](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab)   
 [DECLARE_NOT_AGGREGATABLE](http://msdn.microsoft.com/library/2a116c7c-bab8-4f2a-a9ad-03d7aba0f762)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

