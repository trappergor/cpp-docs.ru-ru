---
title: "Ошибка компилятора C2002 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2cbd21c27cff3effad69b19f42eeaecacf20d6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2002"></a>Ошибка компилятора C2002
Недопустимая константа Юникода  
  
 Недопустимая константа многобайтовых символов.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Расширенная символьная константа содержит большее число байтов, чем ожидалось.  
  
2.  Стандартный заголовок STDDEF.h не включается.  
  
3.  Расширенные символы не могут соединяться с обычными строковыми литералами.  
  
4.  Расширенная символьная константа должна стоять символ «L»:  
  
    ```  
    L'mbconst'  
    ```  
  
5.  В Microsoft C++ текстовые аргументы директивы препроцессора должен быть ASCII. Например, директива `#pragma message(L"string")`, является недопустимым.