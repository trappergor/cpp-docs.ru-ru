---
title: Класс IObjectWithSiteImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl
- ATLCOM/ATL::IObjectWithSiteImpl::GetSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetChildSite
- ATLCOM/ATL::IObjectWithSiteImpl::SetSite
- ATLCOM/ATL::IObjectWithSiteImpl::m_spUnkSite
dev_langs:
- C++
helpviewer_keywords:
- IObjectWithSiteImpl class
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d4e2b1fe58ab7ea408438b703b9fe803996fa791
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219042"
---
# <a name="iobjectwithsiteimpl-class"></a>Класс IObjectWithSiteImpl
Этот класс предоставляет методы, что объект, для взаимодействия со своим сайтом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Запрашивает место для указателя на интерфейс.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Предоставляет объект с этим сайтом `IUnknown` указатель.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Предоставляет объект с этим сайтом `IUnknown` указатель.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Управляет веб-узла `IUnknown` указатель.|  
  
## <a name="remarks"></a>Примечания  
 [IObjectWithSite](/windows/desktop/api/ocidl/nn-ocidl-iobjectwithsite) интерфейс позволяет объекту обмениваться данными со своим сайтом. Класс `IObjectWithSiteImpl` предоставляет стандартную реализацию этого интерфейса и реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 `IObjectWithSiteImpl` Указывает два метода. Клиент вызывает первый `SetSite`, передав сайта `IUnknown` указатель. Этот указатель хранится в объекте и более поздней версии можно получить путем вызова `GetSite`.  
  
 Как правило, являются производными от класса `IObjectWithSiteImpl` при создании объекта, не является элементом управления. Для элементов управления, являются производными от класса [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), предоставляющий указатель на узел. Является производным класса оба `IObjectWithSiteImpl` и `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="getsite"></a>  IObjectWithSiteImpl::GetSite  
 Запрашивает указатель на интерфейс, определенный на сайте `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Примечания  
 Если сайт поддерживает этот интерфейс, через возвращается указатель `ppvSite`. В противном случае `ppvSite` имеет значение NULL.  
  
 См. в разделе [IObjectWithSite::GetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-getsite) в Windows SDK.  
  
##  <a name="m_spunksite"></a>  IObjectWithSiteImpl::m_spUnkSite  
 Управляет веб-узла `IUnknown` указатель.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Примечания  
 `m_spUnkSite` Сначала он получит этот указатель посредством вызова [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>  IObjectWithSiteImpl::SetChildSite  
 Предоставляет объект с этим сайтом `IUnknown` указатель.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkSite*  
 [in] Указатель на `IUnknown` указатель на интерфейс управления данного объекта сайта. Если значение равно NULL, объект должен вызвать `IUnknown::Release` на любой существующий сайт, после чего объект больше не знает его сайта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK.  
  
##  <a name="setsite"></a>  IObjectWithSiteImpl::SetSite  
 Предоставляет объект с этим сайтом `IUnknown` указатель.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IObjectWithSite::SetSite](/windows/desktop/api/ocidl/nf-ocidl-iobjectwithsite-setsite) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
