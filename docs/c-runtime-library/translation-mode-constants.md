---
title: "Константы режима трансляции | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_O_BINARY"
  - "_O_TEXT"
  - "_O_RAW"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_O_BINARY - константа"
  - "_O_RAW - константа"
  - "_O_TEXT - константа"
  - "O_BINARY - константа"
  - "O_RAW - константа"
  - "O_TEXT - константа"
  - "константы перевода"
  - "режимы перевода (файловый ввод и вывод)"
  - "преобразование, константы"
  - "преобразование, режимы"
ms.assetid: a5993bf4-7e7a-47f9-83c3-e46332b85579
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Константы режима трансляции
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
#include <fcntl.h>  
  
```  
  
## Заметки  
 Константы `_O_BINARY` и `_O_TEXT` определяют режим преобразования файлов \(`_open` и `_sopen`\) или режим преобразования потоков \(`_setmode`\).  
  
 Допустимые значения:  
  
 `_O_TEXT`  
 Открывает файл в текстовом \(преобразованном\) режиме.  Сочетания возврат каретки \- перевод строки \(CR\-LF\) транслируются в один символ перевода строки на входе.  Символы перевода строки транслируются в сочетания CR\-LF на выходе.  Также CTRL\+Z интерпретируется как символ конца файла на входе.  В файлах, открытых для чтения и чтения или записи, `fopen` проверяет наличие CTRL\+Z в конце файла и удаляет его, если это возможно.  Это делается потому, что использование функций `fseek` и `ftell` для перемещения в файле, который заканчивается CTRL\+Z, может вызвать неправильное поведение `fseek` ближе к концу файла.  
  
 `_O_BINARY`  
 Открывает файл в бинарном \(непреобразованном\) режиме.  Вышеописанные преобразования отключены.  
  
 `_O_RAW`  
 Эквивалентно `_O_BINARY`.  Поддерживается для обеспечения совместимости с C 2.0.  
  
 \(Дополнительные сведения см. в разделе [Тестовый и бинарный режимы файлового ввода\-вывода](../c-runtime-library/text-and-binary-mode-file-i-o.md) и [Трансляция файлов](../c-runtime-library/file-translation-constants.md).  
  
## См. также  
 [\_open, \_wopen](../c-runtime-library/reference/open-wopen.md)   
 [\_pipe](../c-runtime-library/reference/pipe.md)   
 [\_sopen, \_wsopen](../c-runtime-library/reference/sopen-wsopen.md)   
 [\_setmode](../c-runtime-library/reference/setmode.md)   
 [Глобальные константы](../c-runtime-library/global-constants.md)