---
title: "Предупреждение (уровень 1) C4190 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4190
dev_langs:
- C++
helpviewer_keywords:
- C4190
ms.assetid: a4d0ad93-a19a-4063-addd-36d605831567
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
ms.sourcegitcommit: 4ac033535632e94a365aa8dafd849f2ab28a3af7
ms.openlocfilehash: bf45c0737f52da93f93c1f95d313771f0e92a10e
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4190"></a>Предупреждение (уровень 1) C4190 компилятора
«identifier1» используется компоновка c. указано, но возвращаемый тип UDT «идентификатор2» несовместим с C  
  
 Функция или указатель функции имеет возвращаемый тип UDT (определяемый пользователем тип, являющийся класса, структуры, перечисления или объединения) и `extern` компоновка «C». Это допустимо при:  
  
-   Все вызовы этой функции происходят из C++.  
  
-   Определение функции находится в C++.  
  
## <a name="example"></a>Пример  
  
```cpp  
// C4190.cpp  
// compile with: /W1 /LD  
struct X  
{  
   int i;  
   X ();  
   virtual ~X ();  
};  
  
extern "C" X func ();   // C4190  
```
