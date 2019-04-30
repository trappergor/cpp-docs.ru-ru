---
title: Предупреждение компилятора (уровень 1) C4325
ms.date: 08/27/2018
f1_keywords:
- C4325
helpviewer_keywords:
- C4325
ms.assetid: 8127a08c-d626-481b-aa7b-04a3fdc9a9ec
ms.openlocfilehash: 293cbbcfe134f6cb4f5e1bf924be7c03fa278833
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408541"
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

- .text

- .const

- .sconst

- .rdata

- .srdata

Дополнительные разделы могут быть добавлены позже.

## <a name="see-also"></a>См. также

[section](../../preprocessor/section.md)