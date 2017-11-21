---
title: "Ошибка компилятора C2861 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2861
dev_langs: C++
helpviewer_keywords: C2861
ms.assetid: 012bb44d-6c9b-4def-b54e-b19f1f8ddd1b
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 18c51d01b8f273d4546f3411405fe511e31799ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2861"></a>Ошибка компилятора C2861
«имя функции»: функция-член интерфейса не может быть определен  
  
 Компилятор обнаружил ключевое слово интерфейса или вывести структуры в форме интерфейса, но найти член определение функции.  Интерфейс не может содержать определение функции-члена.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C2861:  
  
```  
// C2861.cpp  
// compile with: /c  
#include <objbase.h>   // required for IUnknown definition  
[ object, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IMyInterface : IUnknown {  
   HRESULT mf(int a);  
};  
  
HRESULT IMyInterface::mf(int a) {}   // C2861  
  
```