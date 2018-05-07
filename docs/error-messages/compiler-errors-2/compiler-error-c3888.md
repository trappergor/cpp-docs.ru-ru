---
title: Ошибка компилятора C3888 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c11c897f35a6c395c4bc6ee6a64be51fa810911b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3888"></a>Ошибка компилятора C3888
"имя": выражение константы, связанное с этими данными-членом литерала, не поддерживается в C++/CLI  
  
 Член данных *имя* , объявленный с помощью ключевого слова [literal](../../windows/literal-cpp-component-extensions.md) , инициализирован со значением, не поддерживаемым компилятором. Компилятор поддерживает только целочисленные константы, перечисления и строковые типы. Возможной причиной ошибки **C3888** может быть то, что член данных инициализирован с помощью байтового массива.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте, имеет ли объявленный член данных литерала поддерживаемый тип.  
  
## <a name="see-also"></a>См. также  
 [literal](../../windows/literal-cpp-component-extensions.md)