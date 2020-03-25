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
ms.openlocfilehash: b6ac9f7174baf1e0ebe41181c6a6f43e7bb3f5d1
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169101"
---
# <a name="using-operators-in-__asm-blocks"></a>Использование операторов в блоках __asm

**Блок, относящийся только к системам Microsoft**

Блок `__asm` не может использовать C или C++ конкретные операторы, такие как оператор **<<** . Однако операторы, совместно используемые C и MASM, такие как оператор \*, считаются операторами языка ассемблера. Например, за пределами блока `__asm` квадратные скобки ( **[]** ) обрабатываются как вложенные индексы массива, которые в языке C автоматически масштабируются до размера элемента в массиве. Внутри блока `__asm` они отображаются как оператор индекса MASM, который создает немасштабируемое смещение в байтах из любого объекта данных или метки (а не просто массива). В следующем примере кода демонстрируется различие.

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

## <a name="see-also"></a>См. также раздел

[Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)<br/>
