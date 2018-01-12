---
title: "Команды в файле Makefile | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: commands, makefiles
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5361012fd388f49d8eb956ec1a4fa1bdd53a2dcc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="commands-in-a-makefile"></a>Команды в файле makefile
Описание блока или определение правила указывает блок команд для выполнения, если зависимость является устаревшей. NMAKE отображается каждая команда перед запуском, если/s, **. АВТОМАТИЧЕСКАЯ**, **! CMDSWITCHES**, или использовать @. NMAKE ищет поиск правила вывода, если блок описания должен следовать блок команд.  
  
 Блок команд содержит одну или несколько команд, каждое на отдельной строке. Пустая строка не должно быть между зависимость или правило и блок команд. Однако возможны строку, содержащую только пробелы или знаки табуляции; Такая строка интерпретируется как пустая команда, и ошибка не возникает. Между строками команд можно вставлять пустые строки.  
  
 Командная строка начинается с одного или нескольких пробелов или знаков табуляции. Обратная косая черта (\) и символа новой строки интерпретируется как пробел в команде. Используйте обратную косую черту в конце строки для переноса команды на следующую строку. NMAKE интерпретирует обратная косая черта буквально любой символ, включая пробел или символ табуляции, за обратной косой черты.  
  
 Команды перед точкой с запятой (;) могут отображаться на правило строки или определение зависимостей, независимо от того, имеется ли блок команд:  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## <a name="what-do-you-want-to-know-more-about"></a>Дополнительные сведения  
 [Модификаторы команд](../build/command-modifiers.md)  
  
 [Обозначение компонентов](../build/filename-parts-syntax.md)  
  
 [Встроенные файлы в makefile](../build/inline-files-in-a-makefile.md)  
  
## <a name="see-also"></a>См. также  
 [Справочник по программе NMAKE](../build/nmake-reference.md)