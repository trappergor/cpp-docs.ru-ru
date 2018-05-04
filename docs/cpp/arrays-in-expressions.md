---
title: Массивы в выражениях | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- expressions [C++], arrays in
- arrays [C++], in expressions
ms.assetid: 6e5a795b-d6bd-4e39-b313-6a20d47c4d4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e3e57a97d9be3ef6245c09c6112caf72318fe784
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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