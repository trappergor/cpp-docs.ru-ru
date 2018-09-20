---
title: Isbaseofstrict-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 52db5abd0487624f52f692e785007adaf9eac7ee
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46428269"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template <
   typename Base,
   typename Derived
>

struct IsBaseOfStrict;
template <
   typename Base
>
struct IsBaseOfStrict<Base, Base>;
```

### <a name="parameters"></a>Параметры

*Base*<br/>
Базовый тип.

*Производные*<br/>
Производный тип.

## <a name="remarks"></a>Примечания

Проверяет, является ли один тип базовым для другого.

Первый шаблон проверяет, является ли тип, производный от базового типа, который может дать **true** или **false**. Второй шаблон проверяет, является ли тип является производным от самого себя, которая всегда создает **false**.

## <a name="members"></a>Участники

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Константа IsBaseOfStrict::value](../windows/isbaseofstrict-value-constant.md)|Указывает, является ли один тип базовым для другого.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`IsBaseOfStrict`

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)