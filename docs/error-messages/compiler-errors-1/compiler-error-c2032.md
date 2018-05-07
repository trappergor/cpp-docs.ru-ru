---
title: Ошибка компилятора C2032 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1db268222f3b9f7ca6f9ce297680866185e6661d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2032"></a>Ошибка компилятора C2032
«Идентификатор»: функция не может быть членом структуры или объединения «structorunion»  
  
 Структура или объединение содержит функцию-член, который допустим в C++, но не в C. Чтобы устранить эту ошибку, либо компилировать как программы на языке C++, либо удалить функцию-член.  
  
 Следующий пример приводит к возникновению ошибки C2032:  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 Возможное решение  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```