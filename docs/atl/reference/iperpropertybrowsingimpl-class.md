---
title: Класс IPerPropertyBrowsingImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d9fffd6151405eaf53e99f770281139d7664b01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="iperpropertybrowsingimpl-class"></a>Класс IPerPropertyBrowsingImpl
Этот класс реализует **IUnknown** и позволяет клиенту получить доступ к информации на страницах свойств объекта.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPerPropertyBrowsingImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Возвращает строку, описывающую данное свойство.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Возвращает массив строк, соответствующих значений, которые могут принимать заданного свойства.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Извлекает **VARIANT** содержащий значение свойства, идентифицируемого по заданной DISPID. Идентификатор DISPID связан с данным именем строки, полученные из `GetPredefinedStrings`. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Извлекает идентификатор CLSID страницы свойств, связанных с заданного свойства.|  
  
## <a name="remarks"></a>Примечания  
 [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) интерфейс позволяет получить доступ к информации на страницах свойств объекта. Класс `IPerPropertyBrowsingImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
> [!NOTE]
>  При использовании Microsoft Access в качестве приложения-контейнера, должен быть производным от класса `IPerPropertyBrowsingImpl`. В противном случае доступ не будет загружать элемент управления.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString  
 Возвращает строку, описывающую данное свойство.  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734) в Windows SDK.  
  
##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings  
 Заполняет каждый массив с нулевыми элементами.  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Реализация ATL [GetPredefinedValue](#getpredefinedvalue) возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPerPropertyBrowsing::GetPredefinedStrings](http://msdn.microsoft.com/library/windows/desktop/ms679724) в Windows SDK.  
  
##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue  
 Извлекает **VARIANT** содержащий значение свойства, идентифицируемого по заданной DISPID. Идентификатор DISPID связан с данным именем строки, полученные из `GetPredefinedStrings`.  
  
```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 Реализация ATL [GetPredefinedStrings](#getpredefinedstrings) нет соответствующей строки.  
  
 В разделе [IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401) в Windows SDK.  
  
##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage  
 Извлекает идентификатор CLSID страницы свойств, связанных с указанным свойством.  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>Примечания  
 ATL использует сопоставление свойств объекта для получения этих сведений.  
  
 В разделе [IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Класс IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)   
 [Класс ISpecifyPropertyPagesImpl](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
