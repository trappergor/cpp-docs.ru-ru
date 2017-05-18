---
title: "Класс CComClassFactoryAutoThread | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread
- ATLCOM/ATL::CComClassFactoryAutoThread::CreateInstance
- ATLCOM/ATL::CComClassFactoryAutoThread::LockServer
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactoryAutoThread class
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 88728e6fccc4aea6e8a1f0bbb2811ed299dd4ad9
ms.contentlocale: ru-ru
ms.lasthandoff: 03/31/2017

---
# <a name="ccomclassfactoryautothread-class"></a>Класс CComClassFactoryAutoThread
Этот класс реализует [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) интерфейса и позволяет создавать в нескольких подразделениях объекты.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComClassFactoryAutoThread 
   : public IClassFactory, 
     public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](#createinstance)|Создает объект для указанного идентификатора CLSID.|  
|[CComClassFactoryAutoThread::LockServer](#lockserver)|Блокирует фабрики класса в памяти.|  
  
## <a name="remarks"></a>Примечания  
 `CComClassFactoryAutoThread`Аналогично [CComClassFactory](../../atl/reference/ccomclassfactory-class.md), но позволяет объектам должен быть создан в нескольких подразделениях. Чтобы воспользоваться преимуществами этой поддержки, являются производными модуля exe-ФАЙЛ из [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс содержит макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) как фабрика класса по умолчанию. Для использования `CComClassFactoryAutoThread`, укажите [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) макроса в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM #9](../../atl/codesnippet/cpp/ccomclassfactoryautothread-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="createinstance"></a>CComClassFactoryAutoThread::CreateInstance  
 Создает объект для указанного идентификатора CLSID и возвращает указатель интерфейса на этот объект.  
  
```
STDMETHODIMP CreateInstance(
    LPUNKNOWN pUnkOuter,
    REFIID riid,
    void** ppvObj);
```  
  
### <a name="parameters"></a>Параметры  
 `pUnkOuter`  
 [in] Если объект создается как часть агрегата, затем `pUnkOuter` должен быть внешняя Неизвестная строка. В противном случае `pUnkOuter` должно быть **NULL**.  
  
 `riid`  
 [in] Идентификатор IID запрошенного интерфейса. Если `pUnkOuter` не является **NULL**, `riid` должно быть **IID_IUnknown**.  
  
 `ppvObj`  
 [out] Указатель на указатель на интерфейс, определяемый `riid`. Если объект не поддерживает этот интерфейс `ppvObj` равно **NULL**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 Если модуль является производным от [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md), `CreateInstance` сначала выделяются поток, чтобы создать объект в связанный подразделении.  
  
##  <a name="lockserver"></a>CComClassFactoryAutoThread::LockServer  
 Увеличение и уменьшение, счетчик блокировок модуля путем вызова **_Module::Lock** и **_Module::Unlock**соответственно.  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### <a name="parameters"></a>Параметры  
 `fLock`  
 [in] Если **TRUE**, счетчик блокировок увеличивается; в противном случае, уменьшается на единицу счетчик блокировок.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
### <a name="remarks"></a>Примечания  
 При использовании `CComClassFactoryAutoThread`, **_Module** обычно ссылается на глобальный экземпляр класса [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md).  
  
 Вызов `LockServer` позволяет клиенту удерживаться в фабрику класса, чтобы быстро создать несколько объектов.  
  
## <a name="see-also"></a>См. также  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [Класс CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)   
 [Класс CComClassFactorySingleton](../../atl/reference/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx-класс](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

