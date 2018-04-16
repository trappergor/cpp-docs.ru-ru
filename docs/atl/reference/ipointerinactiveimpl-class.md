---
title: Класс IPointerInactiveImpl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
dev_langs:
- C++
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe45700a941a8a59439b816124728f43e5f54f44
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ipointerinactiveimpl-class"></a>Класс IPointerInactiveImpl
Этот класс реализует **IUnknown** и [интерфейс IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) методы интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IPointerInactiveImpl
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Класс, производный от `IPointerInactiveImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Получает текущую политику активации для объекта. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Уведомляет объект, перемещенные указатель мыши над ним, указав объект срабатывают события мыши. Возвращает реализацию ATL **E_NOTIMPL**.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Задает указатель мыши для неактивного объекта. Возвращает реализацию ATL **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Примечания  
 Неактивные объекта — это просто загрузить или не запущены. В отличие от активного объекта неактивным объектом не получают сообщений Windows с помощью мыши и клавиатуры. Таким образом Неактивные объекты используют меньше ресурсов и обычно более эффективны.  
  
 [Интерфейс IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) интерфейс позволяет объекту для поддержки минимального уровня взаимодействия с мышью, оставаясь неактивным. Эта функция особенно полезна для элементов управления.  
  
 Класс `IPointerInactiveImpl` реализует `IPointerInactive` методов путем простого возврата **E_NOTIMPL**. Тем не менее, он реализует **IUnknown** , отправляя сведения в дамп устройства в отладочных построений.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [создается проект ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getactivationpolicy"></a>IPointerInactiveImpl::GetActivationPolicy  
 Получает текущую политику активации для объекта.  
  
```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPointerInactive::GetActivationPolicy](http://msdn.microsoft.com/library/windows/desktop/ms692470) в Windows SDK.  
  
##  <a name="oninactivemousemove"></a>IPointerInactiveImpl::OnInactiveMouseMove  
 Уведомляет объект, перемещенные указатель мыши над ним, указав объект срабатывают события мыши.  
  
```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPointerInactive::OnInactiveMouseMove](http://msdn.microsoft.com/library/windows/desktop/ms693374) в Windows SDK.  
  
##  <a name="oninactivesetcursor"></a>IPointerInactiveImpl::OnInactiveSetCursor  
 Задает указатель мыши для неактивного объекта.  
  
```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **E_NOTIMPL**.  
  
### <a name="remarks"></a>Примечания  
 В разделе [IPointerInactive::OnInactiveSetCursor](http://msdn.microsoft.com/library/windows/desktop/ms694336) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
