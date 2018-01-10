---
title: "Использование операторов в блоках __asm | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- brackets [ ]
- brackets [ ], __asm blocks
- __asm keyword [C++], operators
- square brackets [ ], __asm blocks
- operators [C++], using in __asm blocks
- square brackets [ ]
ms.assetid: a26ccfd4-40ae-4a61-952f-c417982aa8dd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ca8ac739793c81ef18f8657cbf53c9cb018b3e38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-operators-in-asm-blocks"></a>Использование операторов в блоках __asm
## <a name="microsoft-specific"></a>Блок, относящийся только к системам Microsoft  
 `__asm` Блок не может использовать специальные операторы C или C++, такие как ** << ** оператор. Однако операторы, общие для C и MASM, такие как \* оператор, интерпретируются как операторы языка ассемблера. Например, вне `__asm` блокировать квадратные скобки (**[]**) интерпретируются как включающие нижние индексы массива, которые C автоматически масштабируется до размера элемента в массиве. Внутри блока `__asm` они отображаются как оператор индекса MASM, который создает немасштабируемое смещение в байтах из любого объекта данных или метки (а не просто массива). В следующем примере кода демонстрируется различие.  
  
```  
int array[10];  
  
__asm mov array[6], bx ;  Store BX at array+6 (not scaled)  
  
array[6] = 0;         /* Store 0 at array+24 (scaled) */  
```  
  
 Первая ссылка на `array` не масштабируется, вторая — масштабируется. Обратите внимание, что можно использовать **тип** оператор, чтобы выполнить масштабирование на основе константы. Например, указанные ниже операторы эквивалентны.  
  
```  
__asm mov array[6 * TYPE int], 0 ; Store 0 at array + 24  
  
array[6] = 0;                   /* Store 0 at array + 24 */  
```  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Использование C или C++ в блоках __asm](../../assembler/inline/using-c-or-cpp-in-asm-blocks.md)