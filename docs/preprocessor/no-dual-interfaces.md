---
title: no_dual_interfaces | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- no_dual_interfaces
dev_langs:
- C++
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6dcf63933a54983fcf98e35acce533670dc74ed4
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50070963"
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