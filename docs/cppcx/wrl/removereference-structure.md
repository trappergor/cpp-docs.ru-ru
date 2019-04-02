---
title: RemoveReference - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RemoveReference
helpviewer_keywords:
- RemoveReference structure
ms.assetid: 43ff91bb-815a-440e-b9fb-7dcbb7c863af
ms.openlocfilehash: 7364fd3a123336bd2419006a9de9d7880f12e538
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58786076"
---
# <a name="removereference-structure"></a>RemoveReference - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<class T>
struct RemoveReference;

template<class T>
struct RemoveReference<T&>;

template<class T>
struct RemoveReference<T&&>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Класс.

## <a name="remarks"></a>Примечания

Удаляет ссылка или rvalue признака из параметра шаблона указанного класса.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`Type`|Синоним для параметра-шаблона класса.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`RemoveReference`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)