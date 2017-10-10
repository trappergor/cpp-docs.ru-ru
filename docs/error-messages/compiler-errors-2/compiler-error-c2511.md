---
title: "Ошибка компилятора C2511 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 1ba01f808fb4dd618291777c1da7490b3b95af3c
ms.contentlocale: ru-ru
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2511"></a>Ошибка компилятора C2511
«Идентификатор»: перегруженная функция-член не найден в «класс»  
  
 Версия функции не объявлено с указанными параметрами.  Возможные причины:  
  
1.  Функции переданы неверные параметры.  
  
2.  Передача параметров в неправильном порядке.  
  
3.  Неверное написание имен параметров.  
  
 Следующий пример приводит к возникновению ошибки C2511:  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```
