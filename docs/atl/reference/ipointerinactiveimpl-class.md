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
ms.openlocfilehash: f44bcdedc718ce4d6459fea7f8581273e49caa10
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097566"
---
# <a name="ipointerinactiveimpl-class"></a>Класс IPointerInactiveImpl

Этот класс реализует `IUnknown` и [IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) методы интерфейса.

> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.

## <a name="syntax"></a>Синтаксис

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>Параметры

*T*<br/>
Ваш класс, производный от `IPointerInactiveImpl`.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Извлекает текущую политику активации для объекта. Реализация ATL возвращает E_NOTIMPL.|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Уведомляет объект, указатель мыши наведен на его, указав объект срабатывают события мыши. Реализация ATL возвращает E_NOTIMPL.|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Задает указатель мыши для неактивного объекта. Реализация ATL возвращает E_NOTIMPL.|

## <a name="remarks"></a>Примечания

Неактивные объекта — это просто загрузке или выполнении. В отличие от активного объекта неактивные объекта не может принимать сообщения клавиатуры и мыши Windows. Таким образом Неактивные объекты используют меньше ресурсов и обычно более эффективны.

[IPointerInactive](/windows/desktop/api/ocidl/nn-ocidl-ipointerinactive) интерфейс позволяет объекту для поддержки минимальный уровень взаимодействия с мышью, оставаясь неактивной. Эта функция особенно полезна для элементов управления.

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

См. в разделе [IPointerInactive::GetActivationPolicy](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) в Windows SDK.

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

См. в разделе [IPointerInactive::OnInactiveMouseMove](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) в Windows SDK.

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

См. в разделе [IPointerInactive::OnInactiveSetCursor](/windows/desktop/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor) в Windows SDK.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../../atl/atl-class-overview.md)
