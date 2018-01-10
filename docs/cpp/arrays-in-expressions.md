---
title: "Массивы в выражениях | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 29f6e16e665d8076ed5a1fe593e1bb9437f1406a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="arrays-in-expressions"></a>Массивы в выражениях
При идентификатор типа массива находится в выражении, отличный от `sizeof`, взятия адреса (**&**), или инициализации ссылки, он преобразуется в указатель на первый элемент массива. Пример:  
  
```  
char szError1[] = "Error: Disk drive not ready.";  
char *psz = szError1;  
```  
  
 Указатель `psz` указывает на первый элемент массива `szError1`. Обратите внимание, что массивы, в отличие от указателей, не являются изменяемыми l-значениями. Таким образом, следующее присвоение незаконно.  
  
```  
szError1 = psz;  
```  
  
## <a name="see-also"></a>См. также  
 [Массивы](../cpp/arrays-cpp.md)