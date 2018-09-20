---
title: Issame-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
dev_langs:
- C++
helpviewer_keywords:
- IsSame structure
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b7d1879217ac43e2d7d3714f491f44b8245f4f27
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390530"
---
# <a name="issame-structure"></a>IsSame - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename T1,
   typename T2
>
struct IsSame;
template <
   typename T1
>
struct IsSame<T1, T1>;
```

### <a name="parameters"></a>Параметры

*T1*<br/>
Тип.

*T2*<br/>
Другой тип.

## <a name="remarks"></a>Примечания

Определяет, совпадают ли указанные типы друг с другом.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Константа IsSame::value](../windows/issame-value-constant.md)|Указывает, совпадают ли заданные типы друг с другом.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IsSame`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)