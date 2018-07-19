---
title: Создание встроенных текстовых | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ab1154935ac4eb8b0595c84ba8d75a9ca13e4d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32367502"
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