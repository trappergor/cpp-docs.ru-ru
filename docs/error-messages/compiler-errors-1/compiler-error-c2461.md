---
title: "Ошибка компилятора C2461 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2461
dev_langs: C++
helpviewer_keywords: C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e5e1593e37bd3a02897d023e308593e23d3d73b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2461"></a>Ошибка компилятора C2461
  
> "*класс*": в синтаксисе конструктора отсутствуют формальные параметры  
  
 Конструктор класса не указаны формальные параметры. В объявлении конструктора необходимо указать список формальных параметров. Список может быть пустым.  
  
Чтобы устранить эту проблему, добавьте пару скобок после объявления *класса*:: **класса*.  
  
## <a name="example"></a>Пример  
  
Ниже приведен пример Устранение C2461:  
  
```cpp  
// C2461.cpp  
// compile with: /c  
class C {  
   C::C;     // C2461  
   C::C();   // OK  
};  
```