---
title: "Предупреждение (уровень 4) C4295 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 1/09/2018
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4295
dev_langs: C++
helpviewer_keywords: C4295
ms.assetid: 20dbff85-9f62-4ca3-8fe9-079d4512006d
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 56ffdce8c2790a3944a8f79753177bc80e249778
ms.sourcegitcommit: bc086a7acbe2d9fd77d115f269cc2a0dbeeb5b88
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/10/2018
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
