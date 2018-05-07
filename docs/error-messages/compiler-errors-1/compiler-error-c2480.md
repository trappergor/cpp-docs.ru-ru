---
title: Ошибка компилятора C2480 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2480
dev_langs:
- C++
helpviewer_keywords:
- C2480
ms.assetid: 1a58d1c2-971b-4084-96fa-f94aa51c02f1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 987cefa42b3f3f8d9588e446ca181c0b7cd48f8c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2480"></a>Ошибка компилятора C2480
«Идентификатор»: «thread» допускается только для статических элементов данных  
  
 Нельзя использовать `thread` атрибут с автоматической переменной, нестатический элемент данных, параметр функции или в объявлениях или определениях функций.  
  
 Используйте `thread` для глобальных переменных, статические данные-члены и локальные статические переменные только атрибут.  
  
 Следующий пример приводит к возникновению ошибки C2480:  
  
```  
// C2480.cpp  
// compile with: /c  
__declspec( thread ) void func();   // C2480  
__declspec( thread ) static int i;   // OK  
```