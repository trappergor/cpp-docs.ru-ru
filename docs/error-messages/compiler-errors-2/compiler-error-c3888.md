---
title: "Ошибка компилятора C3888 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3888
dev_langs: C++
helpviewer_keywords: C3888
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 26e55c8a675ada3fd2e88976bc9d9a51cfa8b751
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3888"></a>Ошибка компилятора C3888
"имя": выражение константы, связанное с этими данными-членом литерала, не поддерживается в C++/CLI  
  
 Член данных *имя* , объявленный с помощью ключевого слова [literal](../../windows/literal-cpp-component-extensions.md) , инициализирован со значением, не поддерживаемым компилятором. Компилятор поддерживает только целочисленные константы, перечисления и строковые типы. Возможной причиной ошибки **C3888** может быть то, что член данных инициализирован с помощью байтового массива.  
  
### <a name="to-correct-this-error"></a>Исправление ошибки  
  
1.  Проверьте, имеет ли объявленный член данных литерала поддерживаемый тип.  
  
## <a name="see-also"></a>См. также  
 [literal](../../windows/literal-cpp-component-extensions.md)