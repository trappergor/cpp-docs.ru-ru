---
title: Командный файл BSCMAKE (файл отклика) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- BSCMAKE, response file
- BSCMAKE, command file
- response files, BSCMAKE
- command files, BSCMAKE
- response files
- command files
ms.assetid: abdffeea-35c7-4f2d-8c17-7d0d80bac314
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a879306078c52e0ad11d29f1786a2e55c2480d2f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369569"
---
# <a name="bscmake-command-file-response-file"></a>Командный файл BSCMAKE (файл отклика)
Чтобы обеспечить часть или все данные в файле команд в командной строке. Укажите командный файл, используя следующий синтаксис:  
  
```  
BSCMAKE @filename  
```  
  
 Допускается только один командный файл. Можно указать путь с *filename*. Перед *filename* с символа (@). BSCMAKE не предполагает расширение. Можно указать дополнительные *sbrfiles* в командной строке после *filename*. Командного файла является текстовый файл, содержащий входные данные для BSCMAKE в том же порядке, как его следует указать в командной строке. Аргументы командной строки нужно разделяйте один или несколько пробелов, табуляции и символы новой строки.  
  
 Следующая команда вызывает использование командный файл BSCMAKE:  
  
```  
BSCMAKE @prog1.txt  
```  
  
 Ниже приведен пример командного файла.  
  
```  
/n /v /o main.bsc /El  
/S (  
toolbox.h  
verdate.h c:\src\inc\screen.h  
)  
file1.sbr file2.sbr file3.sbr file4.sbr  
```  
  
## <a name="see-also"></a>См. также  
 [Справочник ВSCMAKE](../../build/reference/bscmake-reference.md)