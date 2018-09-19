---
title: Функции без прототипа | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 34200b8c-5b52-4f0d-aff8-9f70d82868ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2c030bd99fc185b3c52535aecb45697672ef4c14
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717682"
---
# <a name="unprototyped-functions"></a>Функции без прототипа

Для функции без прототипа, вызывающая сторона передаст целочисленные значения как целые числа и значения с плавающей запятой двойной точности. Для значений с плавающей запятой только как в целочисленном регистре, так и в регистре с плавающей запятой будет содержать значение с плавающей запятой в случае, если вызываемый объект ожидает значение в целочисленные регистры.

```
func1();
func2() {   // RCX = 2, RDX = XMM1 = 1.0, and R8 = 7
   func1(2, 1.0, 7);
}
```

## <a name="see-also"></a>См. также

[Соглашение о вызовах](../build/calling-convention.md)