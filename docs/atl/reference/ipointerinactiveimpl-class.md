---
title: Класс IPointerInactiveImpl | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d916d2e2f8f42a4162966a1d0ddc7de55eb6bd4b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883584"
---
# <a name="ipointerinactiveimpl-class"></a>Класс IPointerInactiveImpl
Этот класс реализует `IUnknown` и [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) методы интерфейса.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class IPointerInactiveImpl
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Ваш класс, производный от `IPointerInactiveImpl`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Извлекает текущую политику активации для объекта. Реализация ATL возвращает E_NOTIMPL.|  
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Уведомляет объект, указатель мыши наведен на его, указав объект срабатывают события мыши. Реализация ATL возвращает E_NOTIMPL.|  
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Задает указатель мыши для неактивного объекта. Реализация ATL возвращает E_NOTIMPL.|  
  
## <a name="remarks"></a>Примечания  
 Неактивные объекта — это просто загрузке или выполнении. В отличие от активного объекта неактивные объекта не может принимать сообщения клавиатуры и мыши Windows. Таким образом Неактивные объекты используют меньше ресурсов и обычно более эффективны.  
  
 [IPointerInactive](http://msdn.microsoft.com/library/windows/desktop/ms693712) интерфейс позволяет объекту для поддержки минимальный уровень взаимодействия с мышью, оставаясь неактивной. Эта функция особенно полезна для элементов управления.  
  
 Класс `IPointerInactiveImpl` реализует `IPointerInactive` методы, с помощью простого возврата E_NOTIMPL. Тем не менее, он реализует `IUnknown` , отправляя данные в дамп сборок устройства в режиме отладки.  
  
 **Связанные статьи** [учебник по ATL](../../atl/active-template-library-atl-tutorial.md), [Создание проекта ATL](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IPointerInactive`  
  
 `IPointerInactiveImpl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlctl.h  
  
##  <a name="getactivationpolicy"></a>  IPointerInactiveImpl::GetActivationPolicy  
 Извлекает текущую политику активации для объекта.  
  
```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPointerInactive::GetActivationPolicy](http://msdn.microsoft.com/library/windows/desktop/ms692470) в Windows SDK.  
  
##  <a name="oninactivemousemove"></a>  IPointerInactiveImpl::OnInactiveMouseMove  
 Уведомляет объект, указатель мыши наведен на его, указав объект срабатывают события мыши.  
  
```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPointerInactive::OnInactiveMouseMove](http://msdn.microsoft.com/library/windows/desktop/ms693374) в Windows SDK.  
  
##  <a name="oninactivesetcursor"></a>  IPointerInactiveImpl::OnInactiveSetCursor  
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
 Возвращает E_NOTIMPL.  
  
### <a name="remarks"></a>Примечания  
 См. в разделе [IPointerInactive::OnInactiveSetCursor](http://msdn.microsoft.com/library/windows/desktop/ms694336) в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
