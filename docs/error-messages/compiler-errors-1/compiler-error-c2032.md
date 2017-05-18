---
title: "Ошибка компилятора C2032 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2032
dev_langs:
- C++
helpviewer_keywords:
- C2032
ms.assetid: 625d7c83-70b6-42c2-a558-81fbc0026324
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: f1079979099dbf3b12e81a9b736faa40e8e4d8d8
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2032"></a>Ошибка компилятора C2032
«Идентификатор»: функция не может быть членом структуры или объединения «structorunion»  
  
 Структура или объединение содержит функцию-член, который допустим в C++, но не в C. Чтобы устранить эту ошибку, компилируется как программы на языке C++ или удалить функцию-член.  
  
 Следующий пример приводит к возникновению ошибки C2032:  
  
```  
// C2032.c  
struct z {  
   int i;  
   void func();   // C2032  
};  
```  
  
 Возможное решение:  
  
```  
// C2032b.c  
// compile with: /c  
struct z {  
   int i;  
};  
```
