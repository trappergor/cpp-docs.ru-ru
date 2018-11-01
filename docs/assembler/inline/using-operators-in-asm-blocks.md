---
title: Использование операторов в блоках __asm
ms.date: 08/30/2018
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
ms.openlocfilehash: a871c19942252bf6a1a4901f8854b7b759700cd9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432803"
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