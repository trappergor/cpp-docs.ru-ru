---
title: Константа IsBaseOfStrict::value | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict::value
dev_langs:
- C++
helpviewer_keywords:
- value constant
ms.assetid: 4a0cdab0-ba03-482b-babf-eeec519ba687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e7159e75b03c6440dfc5742de9f98d93da47d904
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42583858"
---
# <a name="isbaseofstrictvalue-constant"></a>Константа IsBaseOfStrict::value

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
static const bool value = __is_base_of(Base, Derived);
```

## <a name="remarks"></a>Примечания

Указывает, является ли один тип базовым для другого.

**значение** — **true** Если тип `Base` является базовым классом типа `Derived`, в противном случае это **false**.

## <a name="requirements"></a>Требования

**Заголовок:** internal.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="see-also"></a>См. также

[Структура IsBaseOfStrict](../windows/isbaseofstrict-structure.md)  
[Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)