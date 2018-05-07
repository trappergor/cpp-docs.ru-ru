---
title: Предупреждение (уровень 4) C4295 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 1/09/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4295
dev_langs:
- C++
helpviewer_keywords:
- C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 815a669bc359121b13b1d636009cad81dc332304
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4295"></a>Предупреждение компилятора (уровень 4) C4295
  
> "*массива*": массив слишком мал, чтобы включить знак завершения null  
  
Массив был инициализирован, но последний знак в массиве не является пустым; доступ к массиву как строка может привести к непредвиденным результатам.  
  
## <a name="example"></a>Пример  
  
Следующий пример приводит к возникновению ошибки C4295. Чтобы устранить эту проблему, можно объявить размер массива больше для хранения завершающий нуль-символ из инициализатора строки, или использовать список инициализаторов массива вносить намерения clear, что это массив `char`, не является строкой символом null.  
  
```C  
// C4295.c
// compile with: /W4


int main() {
   char a[3] = "abc";           // C4295
   char b[3] = {'d', 'e', 'f'}; // No warning
   a[0] = b[2];
}
```
