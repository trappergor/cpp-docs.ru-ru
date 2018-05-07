---
title: Ошибка компилятора C3626 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ede2ec42b3afc581126d2591cba072817dcc8748
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3626"></a>Ошибка компилятора C3626
«ключевое_слово»: ключевое слово «__event» можно использовать только на интерфейсы COM, функции-члены и члены данных, которые являются указателями на делегаты  
  
 Ключевое слово был использован неправильно.  
  
 Следующий пример приводит к возникновению ошибки C3626:  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```