---
title: "Создание встроенных текстовых | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 174160657e5494f5566fd0828815b3c0f1b3d601
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="creating-inline-file-text"></a>Создание встроенных текстовых стилей
Встроенные файлы являются постоянными или временными.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## <a name="remarks"></a>Примечания  
 Укажите *inlinetext* в первой строке после команды. Отметить конец строки при помощи двойные угловые скобки (<<) в начале отдельной строке. Файл содержит все *inlinetext* перед разделяющими скобками. *Inlinetext* может иметь расширения макроса и подстановки, но не директивы или комментарии makefile. Пробелы, знаки табуляции и символы новой строки обрабатываются буквально.  
  
 Временный файл существует в течение всего сеанса и могут быть использованы другими командами. Укажите **Сохранить** после закрывающие угловые скобки, чтобы сохранить файл после сессии NMAKE; безымянный файл сохраняется на диске с именем созданного файла. Укажите **NOKEEP** или ничего для временного файла. **Сохранить** и **NOKEEP** не учитывается регистр.  
  
## <a name="see-also"></a>См. также  
 [Подставляемые файлы в Makefile](../build/inline-files-in-a-makefile.md)