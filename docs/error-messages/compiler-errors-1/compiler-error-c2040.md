---
title: "Ошибка компилятора C2040 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2040
dev_langs:
- C++
helpviewer_keywords:
- C2040
ms.assetid: 74ca3592-1469-4965-ab34-a4815e2fbefe
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3504c8e18637ef907d5ab9c941ef7ad550daedf0
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2040"></a>Ошибка компилятора C2040
operator: identifier1 отличается по уровням косвенного обращения от identifier2  
  
 Выражение, включающее заданные операнды, содержит несовместимые или неявно преобразованные типы операндов. Если оба операнда арифметические или неарифметические (например, массив или указатель), они используются без изменения. Если один из операндов арифметический, а другой — нет, арифметический операнд преобразуется в неарифметический.  
  
 В этом примере показано возникновение ошибки C2040 и приводятся сведения по ее устранению.  
  
```  
// C2040.cpp  
// Compile by using: cl /c /W3 C2040.cpp  
bool test() {  
   char c = '3';  
   return c == "3"; // C2446, C2040  
   // return c == '3'; // OK  
}  
```
