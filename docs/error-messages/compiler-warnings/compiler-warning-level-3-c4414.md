---
title: Предупреждение компилятора (уровень 3) C4414
ms.date: 11/04/2016
f1_keywords:
- C4414
helpviewer_keywords:
- C4414
ms.assetid: bc81d3ad-55dc-4a6b-a6f2-ec0ef38347df
ms.openlocfilehash: 4625f6bdb4aa6fe86ca881a8e36e5673e55ccb87
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185598"
---
# <a name="compiler-warning-level-3-c4414"></a>Предупреждение компилятора (уровень 3) C4414

"функция": короткий переход к функции преобразован в NEAR

Короткие переходы создают компактную инструкцию, которая подключается к адресу в ограниченном диапазоне от инструкции. Инструкция включает короткое смещение, представляющее расстояние между переходом и целевым адресом, определением функции. Во время связывания функция может быть перемещена или подвергаться оптимизации во время компоновки, что приводит к тому, что функция перемещается из диапазона, доступного из короткого смещения. Компилятор должен создать специальную запись для перехода, которая требует, чтобы инструкция переход была либо NEAR, либо более ДАЛЬНЕй. Компилятор выполнил преобразование.

Например, следующий код создает C4414:

```cpp
// C4414.cpp
// compile with: /W3 /c
// processor: x86
int DoParityEven();
int DoParityOdd();
unsigned char global;
int __declspec(naked) DoParityEither()
{
   __asm
   {
      test global,0
      jpe SHORT DoParityEven  // C4414
      jmp SHORT DoParityOdd   // C4414
   }
}
```
