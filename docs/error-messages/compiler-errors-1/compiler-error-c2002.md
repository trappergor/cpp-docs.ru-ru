---
title: Ошибка компилятора C2002 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01124fc839d6e788ff2dccae325f01f7d4337f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
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