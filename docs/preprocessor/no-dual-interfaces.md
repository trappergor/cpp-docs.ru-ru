---
title: no_dual_interfaces
ms.date: 11/04/2016
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: ae75bc2e974f374768f1a9e5a0e1ced61e9904b0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023806"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**Конкретных C++**

Изменяет способ, которым компилятор создает функции оболочки для методов сдвоенных интерфейсов.

## <a name="syntax"></a>Синтаксис

```
no_dual_interfaces
```

## <a name="remarks"></a>Примечания

Как правило, программа-оболочка вызывает метод через таблицу виртуальных функций интерфейса. С помощью **no_dual_interfaces**, вместо этого вызывает оболочки `IDispatch::Invoke` для вызова метода.

**КОНЕЦ конкретных C++**

## <a name="see-also"></a>См. также

[атрибуты #import](../preprocessor/hash-import-attributes-cpp.md)<br/>
[директива #import](../preprocessor/hash-import-directive-cpp.md)