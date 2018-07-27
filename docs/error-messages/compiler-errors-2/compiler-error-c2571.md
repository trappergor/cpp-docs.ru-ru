---
title: Ошибка компилятора C2571 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96dea582cf5d1211d57eac94a7f70458a51542ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230778"
---
# <a name="compiler-error-c2571"></a>Ошибка компилятора C2571
«функция»: виртуальная функция не может быть в объединении «объединение»  
  
 Виртуальная функция объявляется объединение. Можно объявить виртуальной функции только в классе или структуре.  Возможные решения:  
  
1.  Преобразуйте объединение в классе или структуре.  
  
2.  Не делайте функцию виртуальной.  
  
 Следующий пример приводит к возникновению ошибки C2571:  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```