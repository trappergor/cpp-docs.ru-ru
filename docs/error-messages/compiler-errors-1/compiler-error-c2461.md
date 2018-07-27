---
title: Ошибка компилятора C2461 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2461
dev_langs:
- C++
helpviewer_keywords:
- C2461
ms.assetid: e64ba651-f441-4fdb-b5cb-4209bbbe4db4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47aee3122dad3e875cf58d5a41bcadda297e1463
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197641"
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