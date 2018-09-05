---
title: Использование операторов в блоках __asm | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8731169013cba50e01c36aa721859e136938f015
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43676914"
---
# <a name="using-operators-in-asm-blocks"></a>Использование операторов в блоках __asm

**Блок, относящийся только к системам Microsoft**

`__asm` Блок не может использовать специальные операторы C или C++, такие как **<<** оператор. Однако операторы, общие для C и MASM, такие как \* оператор, интерпретируются как операторы языка ассемблера. Например, за пределами `__asm` block, квадратные скобки (**[]**) интерпретируются как включающие нижние индексы массива, которые C автоматически масштабируется до размера элемента в массиве. Внутри блока `__asm` они отображаются как оператор индекса MASM, который создает немасштабируемое смещение в байтах из любого объекта данных или метки (а не просто массива). В следующем примере кода демонстрируется различие.

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

Первая ссылка на `array` не масштабируется, вторая — масштабируется. Обратите внимание, что можно использовать **тип** оператор, чтобы выполнить масштабирование на основе константы. Например, указанные ниже операторы эквивалентны.

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>