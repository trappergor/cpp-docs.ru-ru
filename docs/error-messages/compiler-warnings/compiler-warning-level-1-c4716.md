---
title: "Предупреждение (уровень 1) C4716 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4716
dev_langs: C++
helpviewer_keywords: C4716
ms.assetid: d95ecfe5-870f-461f-a746-7913af98414b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2d8ded9465251b5c9f0adddbebe1738fa519097c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4716"></a>Предупреждение компилятора (уровень 1) C4716
Функция "функция" должна возвращать значение  
  
 Данная функция не было получено значение.  
  
 Только функции с возвращаемым типом void может использовать команду возвращения без возвращаемого значения.  
  
 При вызове этой функции возвращается неопределенное значение.  
  
 Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить такое поведение, используйте [#pragma warning](../../preprocessor/warning.md).  
  
 Следующий пример приводит к возникновению ошибки C4716:  
  
```  
// C4716.cpp  
// compile with: /c /W1  
// C4716 expected  
#pragma warning(default:4716)  
int test() {  
   // uncomment the following line to resolve  
   // return 0;  
}  
```