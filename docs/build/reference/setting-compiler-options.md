---
title: "Настройка параметров компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiler options, setting
- cl.exe compiler, setting options
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbbc7111ceae2353e8bc9820ead319556ce0016b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="setting-compiler-options"></a>Настройка параметров компилятора
Параметры компиляторов C и C++ можно настраивать в среде разработки или в командной строке.  
  
## <a name="in-the-development-environment"></a>Настройка в среде разработки  
 Можно задать параметры компилятора для каждого проекта в его **страницы свойств** диалоговое окно. В левой области выберите **свойства конфигурации**, **C/C++** и выберите категорию параметров компилятора. В разделе для каждого параметра компилятора приводится описание способа задания и расположение параметра в среде разработки. В разделе [параметры компилятора](../../build/reference/compiler-options.md) полный список.  
  
## <a name="outside-the-development-environment"></a>Настройка вне среды разработки  
 Способы настройки параметров компилятора (CL.exe):  
  
-   [В командной строке](../../build/reference/compiler-command-line-syntax.md)  
  
-   [В командных файлах](../../build/reference/cl-command-files.md)  
  
-   [В переменной среды компилятора CL](../../build/reference/cl-environment-variables.md)  
  
 Параметры, заданные в переменной среды компилятора CL, используются при каждом вызове компилятора CL. Если командный файл указан в переменной среды компилятора CL или в командной строке, используются параметры, заданные в командном файле. В отличие от командной строки или переменной среды компилятора CL, командный файл позволяет использовать несколько строк для параметров и имен файлов.  
  
 Параметры компилятора обрабатываются "слева направо", и при обнаружении конфликта приоритет имеет последний (крайний справа) параметр. Переменная среды компилятора CL обрабатывается до обработки командной строки, поэтому в случае возникновения конфликтов между компилятором CL и командной строкой приоритет имеет командная строка.  
  
## <a name="additional-compiler-topics"></a>Дополнительные разделы, содержащие сведения о компиляторах  
  
-   [Быстрая компиляция](../../build/reference/fast-compilation.md)  
  
-   [Вызов компоновщика компилятором CL](../../build/reference/cl-invokes-the-linker.md)  
  
## <a name="see-also"></a>См. также  
 [Справочные сведения о построении C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)