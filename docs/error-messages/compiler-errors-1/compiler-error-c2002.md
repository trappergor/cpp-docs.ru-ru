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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d8f6fc5983a462850581f69ca32dd7c305f9e847
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

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
