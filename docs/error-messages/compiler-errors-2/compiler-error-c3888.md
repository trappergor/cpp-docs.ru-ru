---
title: "Ошибка компилятора C3888 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3888
dev_langs:
- C++
helpviewer_keywords:
- C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 4b85385c97f5873c1b370cd72f0866439263f787
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-error-c3888"></a>Ошибка компилятора C3888
"имя": выражение константы, связанное с этими данными-членом литерала, не поддерживается в C++/CLI  
  
 *Имя* данные-член, объявленный с [литерала](../../windows/literal-cpp-component-extensions.md) ключевое слово инициализируется со значением, компилятор не поддерживает. Компилятор поддерживает только целочисленные константы, перечисления и строковые типы. Возможной причиной ошибки **C3888** может быть то, что член данных инициализирован с помощью байтового массива.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте, имеет ли объявленный член данных литерала поддерживаемый тип.  
  
## <a name="see-also"></a>См. также  
 [литерал](../../windows/literal-cpp-component-extensions.md)
