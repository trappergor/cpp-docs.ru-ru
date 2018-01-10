---
title: "Предупреждение (уровень 4) C4295 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
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
ms.openlocfilehash: 1424302c5c109ff79f35c922d1e5051b15655554
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4295"></a>Предупреждение компилятора (уровень 4) C4295
  
> "*массива*": массив слишком мал, чтобы включить знак завершения null  
  
 Массив был инициализирован, но последний знак в массиве не является пустым; доступ к массиву может привести к непредвиденным результатам.  
  
## <a name="example"></a>Пример  
  
 Следующий пример приводит к возникновению ошибки C4295. Чтобы устранить эту проблему, можно объявить размер массива больше для хранения завершающей null из инициализатора.  
  
```C  
// C4295.c  
// compile with: /W4  
  
int main() {  
   char a[3] = "abc";   // C4295  
}  
```