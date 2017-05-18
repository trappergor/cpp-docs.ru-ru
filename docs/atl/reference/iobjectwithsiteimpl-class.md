---
title: "Класс интерфейс IObjectWithSiteImpl | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 18
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 49c52810417650c3d80fe4d0c09ccb2b67208ad4
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="iobjectwithsiteimpl-class"></a>Интерфейс IObjectWithSiteImpl класса
Этот класс предоставляет методы, что объект для взаимодействия со своим сайтом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>
    class ATL_NO_VTABLE IObjectWithSiteImpl :
    public IObjectWithSite
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IObjectWithSiteImpl`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectWithSiteImpl::GetSite](#getsite)|Запрашивает указатель интерфейса на сайте.|  
|[IObjectWithSiteImpl::SetChildSite](#setchildsite)|Предоставляет объект на сайте **IUnknown** указателя.|  
|[IObjectWithSiteImpl::SetSite](#setsite)|Предоставляет объект на сайте **IUnknown** указателя.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[IObjectWithSiteImpl::m_spUnkSite](#m_spunksite)|Управляет веб-узла **IUnknown** указателя.|  
  
## <a name="remarks"></a>Примечания  
 [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) интерфейс позволяет объекту обмениваться данными с сайтом. Класс `IObjectWithSiteImpl` предоставляет стандартную реализацию этого интерфейса и реализует **IUnknown** при отправке информации для дампа строит устройства в режиме отладки.  
  
 `IObjectWithSiteImpl`Определяет два метода. Клиент сначала вызывает `SetSite`, передав сайта **IUnknown** указателя. Этот указатель сохранен внутри объекта и более поздней версии можно получить путем вызова `GetSite`.  
  
 Как правило, являются производными от класса `IObjectWithSiteImpl` при создании объекта, не является элементом управления. Для элементов управления, являются производными от класса [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), предоставляющий указатель сайта. Не наследуйте класс оба `IObjectWithSiteImpl` и `IOleObjectImpl`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="getsite"></a>IObjectWithSiteImpl::GetSite  
 Запрашивает указатель интерфейса, определенного на сайте `riid`.  
  
```
STDMETHOD(GetSite)(
    REFIID riid,
    void** ppvSite);
```  
  
### <a name="remarks"></a>Примечания  
 Если узел поддерживает этот интерфейс, указатель, возвращенный через `ppvSite`. В противном случае — `ppvSite` равен **NULL**.  
  
 В разделе [IObjectWithSite::GetSite](http://msdn.microsoft.com/library/windows/desktop/ms694452) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="m_spunksite"></a>IObjectWithSiteImpl::m_spUnkSite  
 Управляет веб-узла **IUnknown** указателя.  
  
```
CComPtr<IUnknown> m_spUnkSite;
```  
  
### <a name="remarks"></a>Примечания  
 `m_spUnkSite`Сначала получит этот указатель посредством вызова [SetSite](#setsite).  
  
##  <a name="setchildsite"></a>IObjectWithSiteImpl::SetChildSite  
 Предоставляет объект на сайте **IUnknown** указателя.  
  
```
HRESULT SetChildSite(IUnknown* pUnkSite);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnkSite*  
 [in] Указатель на **IUnknown** указатель интерфейса управления данного объекта сайта. Если значение равно NULL, объект должен вызывать `IUnknown::Release` на любой существующего сайта, после чего объект больше не знает своего сайта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `S_OK`.  
  
##  <a name="setsite"></a>IObjectWithSiteImpl::SetSite  
 Предоставляет объект на сайте **IUnknown** указателя.  
  
```
STDMETHOD(SetSite)(IUnknown* pUnkSite);
```  
  
### <a name="remarks"></a>Примечания  
 В разделе [IObjectWithSite::SetSite](http://msdn.microsoft.com/library/windows/desktop/ms683869) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

