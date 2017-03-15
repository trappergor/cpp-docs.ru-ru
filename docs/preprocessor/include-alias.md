---
title: "include_alias | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.include_alias"
  - "include_alias_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "include_alias - прагма"
  - "прагмы, include_alias"
ms.assetid: 3256d589-12b3-4af0-a586-199e96eabacc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# include_alias
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Указывает, что в качестве псевдонима для *длинного\_имени\_файла* должно использоваться *краткое\_имя\_файла*.  
  
## Синтаксис  
  
```  
  
      #pragma include_alias( "  
      long_filename  
      ", "  
      short_filename  
      " )  
#pragma include_alias( <long_filename>, <short_filename> )  
```  
  
## Заметки  
 Некоторые файловые системы поддерживают более длинные имена файлов заголовков, чем допускается ограничением файловой системы FAT \(8 символов в имени файла и 3 символа в расширении\).  Компилятор не может просто усечь более длинные имена до этого стандарта, поскольку первые восемь символов в длинных именах файлов заголовков могут быть неуникальными.  Когда компилятор встречает строку *длинное\_имя\_файла*, он подставляет вместо нее строку *краткое\_имя\_файла* и выполняет поиск файла заголовка с *кратким\_именем\_файла*.  Эта директива pragma должна располагаться до соответствующей директивы `#include`.  Например:  
  
```  
// First eight characters of these two files not unique.  
#pragma include_alias( "AppleSystemHeaderQuickdraw.h", "quickdra.h" )  
#pragma include_alias( "AppleSystemHeaderFruit.h", "fruit.h" )  
  
#pragma include_alias( "GraphicsMenu.h", "gramenu.h" )  
  
#include "AppleSystemHeaderQuickdraw.h"  
#include "AppleSystemHeaderFruit.h"  
#include "GraphicsMenu.h"  
```  
  
 Псевдоним должен точно соответствовать заданному имени как по написанию, так и по регистру. а также по использованию двойных кавычек и угловых скобок.  Директива \#pragma **include\_alias** никак не проверяет имена файлов, а лишь сопоставляет строки в них.  Рассмотрим директивы в следующем примере:  
  
```  
#pragma include_alias("mymath.h", "math.h")  
#include "./mymath.h"  
#include "sys/mymath.h"  
```  
  
 В этом примере псевдоним не назначается \(подстановка не выполняется\), поскольку строки файлов заголовков совпадают не полностью.  Кроме того, подстановка не выполняется в именах файлов заголовков, которые используются в качестве аргументов к параметрам компилятора, а также в директиве **hdrstop**.  Например, представим, что исходный файл содержит следующую директиву:  
  
```  
#include <AppleSystemHeaderStop.h>  
```  
  
 В этом случае должен использоваться следующий параметр компилятора:  
  
```  
/YcAppleSystemHeaderStop.h  
```  
  
 С помощью директивы \#pragma **include\_alias** можно сопоставить любую пару имен файлов заголовков.  Например:  
  
```  
#pragma include_alias( "api.h", "c:\version1.0\api.h" )  
#pragma include_alias( <stdio.h>, <newstdio.h> )  
#include "api.h"  
#include <stdio.h>  
```  
  
 Не смешивайте имена файлов в двойных кавычках с именами файлов, заключенными в угловые скобки.  Например, в двух приведенных выше директивах **\#pragma include\_alias** компилятор не будет выполнять подстановку для следующих директив `#include`:  
  
```  
#include <api.h>  
#include "stdio.h"  
```  
  
 Кроме того, следующая директива вызовет ошибку:  
  
```  
#pragma include_alias(<header.h>, "header.h")  // Error  
```  
  
 Обратите внимание на то, что в сообщениях об ошибках и в значении предопределенного макроса **\_\_FILE\_\_** используется имя файла после выполнения подстановки.  Например, после применения следующих директив:  
  
```  
#pragma include_alias( "VeryLongFileName.H", "myfile.h" )  
#include "VeryLongFileName.H"  
```  
  
 в результате ошибки в файле VERYLONGFILENAME.H будет выведено следующее сообщение:  
  
```  
myfile.h(15) : error C2059 : syntax error  
```  
  
 Также обратите внимание, что транзитивность не поддерживается.  Рассмотрим следующий пример:  
  
```  
#pragma include_alias( "one.h", "two.h" )  
#pragma include_alias( "two.h", "three.h" )  
#include "one.h"  
```  
  
 В этом случае компилятор будет искать файл TWO.H, а не THREE.H.  
  
## См. также  
 [Директивы Pragma и ключевое слово \_\_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)