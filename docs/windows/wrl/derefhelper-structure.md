---
title: DerefHelper - структура
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 7709ae63e4d49e25aec83a069ad1ac614bfbd953
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336487"
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

|Имя|Описание:|
|----------|-----------------|
|`DerefType`|Идентификатор для разыменованного параметра шаблона `T*`.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`DerefHelper`

## <a name="requirements"></a>Требования

**Заголовок:** async.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](microsoft-wrl-details-namespace.md)