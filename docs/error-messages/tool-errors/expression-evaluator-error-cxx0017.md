---
title: "Ошибка вычислителя выражений CXX0017 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0017
dev_langs: C++
helpviewer_keywords:
- CAN0017
- CXX0017
ms.assetid: af74db02-a64d-49ca-8363-3e044a107580
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e769e9886168c9f19ad110c48d848a9b84ab8aac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0017"></a>Ошибка вычислителя выражений CXX0017
символ не найден  
  
 Не удалось найти символ, указанный в выражении.  
  
 Одной из возможных причин этой ошибки является несоответствие регистров в имени символа. Поскольку C и C++ регистр языков, имени символа должен передаваться в том же регистре, в котором он определен в источнике.  
  
 Эта ошибка может возникать при попытке приведения переменной в целях отслеживания в ходе отладки. `typedef` Объявляет новое имя для типа, но не определяет новый тип. При использовании приведения в отладчике требуется имя определенного типа.  
  
 Эта ошибка идентична ошибке CAN0017.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Возможные способы устранения этой ошибки  
  
1.  Убедитесь, что символ уже объявлен в том месте программы, где он используется.  
  
2.  Использовать фактическое имя типа приведении переменных в отладчике, а не `typedef`-определенное имя.