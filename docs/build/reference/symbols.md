---
title: "/SYMBOLS | Microsoft Docs"
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
  - "/symbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/SYMBOLS - параметр программа dumpbin"
  - "открытые символы"
  - "таблицы символов"
  - "SYMBOLS - параметр (программа dumpbin)"
  - "-SYMBOLS - параметр (программа dumpbin)"
  - "символы, таблица COFF-символов - отображение"
  - "символы, дамп"
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /SYMBOLS
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/SYMBOLS  
```  
  
 При выборе этого параметра отображается таблица символов COFF.  Таблицы символов есть во всех объектных файлах.  Таблица символов COFF присутствует в файле образа только в том случае, если он был скомпонован с параметром \/DEBUG.  
  
 Далее приведено описание сведений, выводимых при использовании параметра \/SYMBOLS.  Дополнительные сведения о значении информации, выводимой при использовании параметра \/SYMBOLS, можно найти в файле winnt.h \(IMAGE\_SYMBOL и IMAGE\_AUX\_SYMBOL\) или документации COFF.  
  
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
  
## Заметки  
 В приведенном ниже описании строк, начинающихся с номера символа, описываются столбцы, содержащие сведения, представляющие интерес для пользователей:  
  
-   Первое трехзначное число — это индекс или номер символа.  
  
-   Если в третьем столбце стоит SECT*x*, то символ определен в соответствующей секции объектного файла.  Если там стоит UNDEF, то символ не определен в этом объектном файле и должен разрешаться извне.  
  
-   Пятый столбец \(Static, External\) позволяет определить, будет ли символ видим только внутри этого объектного файла, или же он будет общедоступен \(видим извне\).  Статический символ \_sym не будет скомпонован с общедоступным символом \_sym; это два разных экземпляра функций с именем \_sym.  
  
 Последний столбец в нумерованной строке содержит как декорированное, так и недекорированное имя символа.  
  
 В файлах, созданных с использованием параметра компилятора [\/GL](../../build/reference/gl-whole-program-optimization.md), может использоваться только параметр DUMPBIN [\/HEADERS](../../build/reference/headers.md).  
  
## См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)