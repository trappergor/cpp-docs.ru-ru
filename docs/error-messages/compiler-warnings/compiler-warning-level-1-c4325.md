---
title: Предупреждение компилятора (уровень 1) C4325 | Документация Майкрософт
ms.custom: ''
ms.date: 08/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4325
dev_langs:
- C++
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd265938afb51cc402dc84f38b7e95188c6292a7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43197489"
---
# <a name="compiler-warning-level-1-c4325"></a>Предупреждение компилятора (уровень 1) C4325

> атрибуты для стандартного раздела "*разделе*" игнорируется

## <a name="remarks"></a>Примечания

Не может изменять атрибуты из стандартного раздела. Пример:

```cpp
#pragma section(".sdata", long)
```

Перезаписывается `.sdata` стандартного раздела, который использует **короткие** тип данных с **long** тип данных.

Включают стандартные разделы, атрибуты которого не может быть изменен,

- .Data

- .sdata

- .BSS

- .SBSS

- .Text

- .const

- .sconst

- .rdata

- .srdata

Дополнительные разделы могут быть добавлены позже.

## <a name="see-also"></a>См. также

[section](../../preprocessor/section.md)