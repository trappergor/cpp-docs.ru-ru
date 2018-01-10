---
title: "Вызов компоновщика компилятором CL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: cl
dev_langs: C++
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 32a3bdd1e227b894ca5a32ddfaa8c46a478a19f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cl-invokes-the-linker"></a>Вызов компоновщика компилятором CL
CL автоматически вызывает компоновщик после компиляции, если не используется параметр/c. CL передает компоновщику имена OBJ-файлов, созданных во время компиляции и имена других файлов, указанных в командной строке. Компоновщик использует параметры, перечисленные в переменной среды LINK. Чтобы задать параметры в командной строке компилятора CL, можно использовать параметр/LINK. Параметр/LINK варианты переопределяют параметры в переменной среды LINK. Параметры в следующей таблице, отключают компоновку.  
  
|Параметр|Описание:|  
|------------|-----------------|  
|/c|Компиляция без связывания|  
|-/P E, /EP,|Предварительная обработка без компиляции или связывания|  
|/Zg|Создание прототипов функций|  
|/Zs|Проверка синтаксиса|  
  
 Дополнительные сведения о связывании см. в разделе [параметры компоновщика](../../build/reference/linker-options.md).  
  
## <a name="example"></a>Пример  
 Предположим, что выполняется компиляция трех исходных файлов: MAIN.c, MOD1.c и MOD2.c. Каждый файл содержит вызов функции, определенной в другой файл:  
  
-   MAIN.c вызывает функцию `func1` в MOD1.c и функцией `func2` в MOD2.c.  
  
-   MOD1.c вызывает функции стандартной библиотеки `printf_s` и `scanf_s`.  
  
-   MOD2.c вызывает графические функции с именем `myline` и `mycircle`, которые определены в библиотеке с именем MYGRAPH.lib.  
  
 Для построения этой программы, скомпилируйте со следующей командной строкой:  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 Сначала CL компилирует исходные файлы C и создает файлы объектов MAIN.obj файле MOD1.obj и файле MOD2.obj. Компилятор размещает имя стандартной библиотеки в каждый OBJ-файле. Дополнительные сведения см. в разделе [использование библиотеки времени выполнения](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 CL передает компоновщику имена OBJ-файлов, вместе с именем MYGRAPH.lib. При разрешении внешних ссылок следующим образом:  
  
1.  В файле MAIN.obj ссылка `func1` разрешается с использованием определения в файле MOD1.obj; ссылка на `func2` разрешается с использованием определения в файле MOD2.obj.  
  
2.  В файле MOD1.obj, ссылки на `printf_s` и `scanf_s` разрешаются с помощью определений в библиотеке, компоновщик обнаруживает в файле MOD1.obj.  
  
3.  В файле MOD2.obj, ссылки на `myline` и `mycircle` разрешаются с помощью определений в MYGRAPH.lib.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)