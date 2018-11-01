---
title: DerefHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 7e9de446fdf18b3cf92cc438e421287c8fcfc29f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50450206"
---
# <a name="derefhelper-structure"></a>DerefHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>Параметры

*T*<br/>
Параметр шаблона.

## <a name="remarks"></a>Примечания

Представляет разыменованный указатель на параметр шаблона `T*`.

**DerefHelper** используется в выражении, например: `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`DerefType`|Идентификатор для разыменованного параметра шаблона `T*`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DerefHelper`

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)