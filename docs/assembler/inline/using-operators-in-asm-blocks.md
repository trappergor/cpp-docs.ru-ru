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
ms.openlocfilehash: cdcfee20cfdc5a6dc315d00ef024d1616900a2e8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87191109"
---
# <a name="using-operators-in-__asm-blocks"></a>Использование операторов в блоках __asm

**Блок, относящийся только к системам Microsoft**

**`__asm`** Блок не может использовать специальные операторы C или C++, например **<<** оператор. Однако операторы, совместно используемые C и MASM, такие как оператор, считаются операторами \* языка ассемблера. Например, за пределами **`__asm`** блока квадратные скобки (**[]**) обрабатываются как вложенные индексы массива, которые в языке C автоматически масштабируются до размера элемента в массиве. Внутри **`__asm`** блока они отображаются в виде оператора MASM index, который возвращает немасштабированное смещение в байтах от любого объекта данных или метки (не только для массива). В следующем примере кода демонстрируется различие.

```cpp
int array[10];

__asm mov array[6], bx ;  Store BX at array+6 (not scaled)

array[6] = 0;         /* Store 0 at array+24 (scaled) */
```

Первая ссылка на `array` не масштабируется, вторая — масштабируется. Обратите внимание, что оператор **Type** можно использовать для достижения масштабирования на основе константы. Например, следующие инструкции эквивалентны.

```cpp
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24

array[6] = 0;                   /* Store 0 at array + 24 */
```

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
