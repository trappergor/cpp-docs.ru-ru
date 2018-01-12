---
title: "Ошибка компилятора C2758 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2758
dev_langs: C++
helpviewer_keywords: C2758
ms.assetid: 1d273034-194c-4926-9869-142d1b219cbe
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2a67a978883153e0de81e864bf01e8cf9ee2e13c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2758"></a>Ошибка компилятора C2758
member: требуется инициализация члена ссылочного типа  
  
 Ошибка компилятора C2758 возникает, если конструктор не инициализирует член ссылочного типа в списке инициализаторов. Компилятор оставляет член неопределенным. Переменные ссылочного члена должны инициализироваться при объявлении или получать значение в списке инициализации конструктора.  
  
 Следующий пример приводит к возникновению ошибки C2758:  
  
```  
// C2758.cpp  
// Compile by using: cl /W3 /c C2758.cpp  
struct A {  
   const int i;  
  
   A(int n) { };   // C2758  
   // try the following line instead  
   // A(int n) : i{n} {};  
};  
```