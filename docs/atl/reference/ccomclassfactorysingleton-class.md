---
title: Класс CComClassFactorySingleton | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
author: mikeblome
ms.author: mblome
ms.openlocfilehash: ee594cb3cfef5ebc67b953b62d05b933b71f9f1d
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37884198"
---
# <a name="ccomclassfactorysingleton-class"></a>Класс CComClassFactorySingleton
Этот класс является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class CComClassFactorySingleton : public CComClassFactory
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Класс.  
  
 `CComClassFactorySingleton` является производным от [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) и использует [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) для создания объекта. Каждый вызов `CreateInstance` метод просто запрашивает этот объект для указателя на интерфейс.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComClassFactorySingleton::CreateInstance](#createinstance)|Запросы `m_spObj` для указателя на интерфейс.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComClassFactorySingleton::m_spObj](#m_spobj)|[CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объект, созданный с `CComClassFactorySingleton`.|  
  
## <a name="remarks"></a>Примечания  
 Объекты ATL обычно получить фабрику класса путем наследования от [CComCoClass](../../atl/reference/ccomcoclass-class.md). Этот класс включает макрос [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory), который объявляет `CComClassFactory` как фабрики класса по умолчанию. Чтобы использовать `CComClassFactorySingleton`, укажите [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) макроса в определении класса объекта. Пример:  
  
 [!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md)  
  
 `CComClassFactorySingleton`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="createinstance"></a>  CComClassFactorySingleton::CreateInstance  
 Вызовы `QueryInterface` через [m_spObj](#m_spobj) для получения указателя на интерфейс.  
  
```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkOuter*  
 [in] Если объект создается как часть агрегата, затем *pUnkOuter* должен быть внешняя Неизвестная строка. В противном случае *pUnkOuter* должен иметь значение NULL.  
  
 *riid*  
 [in] Идентификатор IID запрошенного интерфейса. Если *pUnkOuter* отлично от NULL, *riid* должно быть `IID_IUnknown`.  
  
 *ppvObj*  
 [out] Указатель на указатель интерфейса, идентифицируемый *riid*. Если объект не поддерживает этот интерфейс *ppvObj* имеет значение NULL.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение HRESULT.  
  
##  <a name="m_spobj"></a>  CComClassFactorySingleton::m_spObj  
 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) объект, созданный с `CComClassFactorySingleton`.  
  
```
CComPtr<IUnknown> m_spObj;
```  
  
### <a name="remarks"></a>Примечания  
 Каждый вызов [CreateInstance](#createinstance) метод просто запрашивает этот объект для указателя на интерфейс.  
  
 Обратите внимание, что текущий способ `m_spObj` представляет критическое изменение из-за способа, `CComClassFactorySingleton` работали в предыдущих версиях библиотеки ATL. В предыдущих версиях `CComClassFactorySingleton` объект был создан в то же время, так как фабрика класса, при инициализации сервера. В Visual C++ .NET 2003 создается объект неактивно, при первом запросе. Это изменение может привести к ошибкам в программ, использующих ранних инициализации.  
  
## <a name="see-also"></a>См. также  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [Класс CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md)   
 [Класс CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md)   
 [Класс CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
