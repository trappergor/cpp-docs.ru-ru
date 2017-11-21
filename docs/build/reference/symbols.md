---
title: "-SYMBOLS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /symbols
dev_langs: C++
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 360f26de5043eae7f5cdb4688612f95b96be8fbd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="symbols"></a>/SYMBOLS
```  
/SYMBOLS  
```  
  
 Этот параметр отображает таблица символов COFF. Таблицы символов есть во всех объектных файлах. Таблица символов COFF появляется в файл изображения, только в том случае, если он связан с параметром/Debug.  
  
 Ниже приведено описание для/Symbols выходных данных. Дополнительные сведения о значении/Symbols выходных данных можно найти путем поиска в winnt.h (IMAGE_SYMBOL и IMAGE_AUX_SYMBOL) или документации COFF.  
  
 Рассмотрим следующий пример дампа:  
  
```  
Dump of file main.obj  
File Type: COFF OBJECT  
  
COFF    SYMBOL    TABLE  
000    00000000   DEBUG      notype      Filename      | .file  
      main.cpp  
002   000B1FDB   ABS      notype      Static      | @comp.id  
003   00000000   SECT1      notype      Static      | .drectve  
      Section length       26, #relocs   0, #linenums    0, checksum 722C964F  
005   00000000   SECT2      notype      Static      | .text  
      Section length      23, #relocs      1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)  
007   00000000   SECT2      notype ()   External      | _main  
008   00000000   UNDEF      notype ()   External      | ?MyDump@@YAXXZ (void __cdecl MyDump(void))  
  
String Table Size = 0x10 bytes  
  
Summary  
  
      26 .drectve  
      23 .text  
```  
  
## <a name="remarks"></a>Примечания  
 Следующие описания для строки, которые начинаются с номера символа, описываются столбцы, содержащие сведения, представляющие интерес для пользователей:  
  
-   Первое число из трех цифр является индекс или номер символа.  
  
-   Если третий столбец содержит РАЗДЕЛ*x*, символ определен в этом разделе файла объекта. Но если UNDEF, не определен в этом объекте и должны быть разрешены в другом месте.  
  
-   Пятый столбец (Static, External) сообщает символ видим только в рамках этого объекта, или же оно является общей (видимым извне). Статический символ _sym не будет скомпонован с общедоступным символом _sym; Это будут два разных экземпляра функций с именем _sym.  
  
 Последний столбец в нумерованной строке является имя символа, внутренних и внешних.  
  
 Только [/Headers](../../build/reference/headers.md) параметр программы DUMPBIN доступна для использования в файлах, созданных с помощью [/GL](../../build/reference/gl-whole-program-optimization.md) параметр компилятора.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)