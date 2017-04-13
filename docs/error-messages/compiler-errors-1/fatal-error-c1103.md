---
title: "Неустранимая ошибка C1103 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
caps.latest.revision: 6
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
ms.openlocfilehash: e750c21ab6f9d3882413a83731c0fa2787f8fe47
ms.lasthandoff: 04/12/2017

---
# <a name="fatal-error-c1103"></a>Неустранимая ошибка C1103
неустранимая ошибка при импорте progid: "сообщение"  
  
 Компилятор обнаружил проблему при импорте библиотеки типов.  Например, нельзя указать библиотеку типов с помощью progid и в то же время указать `no_registry`.  
  
 Дополнительные сведения см. в разделе [директива #import](../../preprocessor/hash-import-directive-cpp.md).  
  
 Следующий пример приводит к возникновению ошибки C1103:  
  
```  
// C1103.cpp  
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```
