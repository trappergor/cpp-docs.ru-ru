---
title: "Образец файла makefile для PCH | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
ms.assetid: daf68983-77dc-45db-8701-aa89ad18910d
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Образец файла makefile для PCH
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

В следующем файле makefile использованы макросы и структура команд потока управления \!IF, \!ELSE, \!ENDIF для упрощения адаптации к проекту.  
  
```  
# Makefile : Illustrates the effective use of precompiled  
#            headers in a project  
# Usage:     NMAKE option  
# option:    DEBUG=[0|1]  
#            (DEBUG not defined is equivalent to DEBUG=0)  
#  
OBJS = myapp.obj applib.obj  
# List all stable header files in the STABLEHDRS macro.  
STABLEHDRS = stable.h another.h  
# List the final header file to be precompiled here:  
BOUNDRY = stable.h  
# List header files under development here:  
UNSTABLEHDRS = unstable.h  
# List all compiler options common to both debug and final  
# versions of your code here:  
CLFLAGS = /c /W3  
# List all linker options common to both debug and final  
# versions of your code here:  
LINKFLAGS = /NOD /ONERROR:NOEXE  
!IF "$(DEBUG)" == "1"  
CLFLAGS   = /D_DEBUG $(CLFLAGS) /Od /Zi /f  
LINKFLAGS = $(LINKFLAGS) /COD  
LIBS      = slibce  
!ELSE  
CLFLAGS   = $(CLFLAGS) /Oselg /Gs  
LINKFLAGS = $(LINKFLAGS)  
LIBS      = slibce  
!ENDIF  
myapp.exe: $(OBJS)  
    link $(LINKFLAGS) @<<  
$(OBJS), myapp, NUL, $(LIBS), NUL;  
<<  
# Compile myapp  
myapp.obj  : myapp.cpp $(UNSTABLEHDRS)  stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    myapp.cpp  
# Compile applib  
applib.obj : applib.cpp $(UNSTABLEHDRS) stable.pch  
    $(CPP) $(CLFLAGS) /Yu$(BOUNDRY)    applib.cpp  
# Compile headers  
stable.pch : $(STABLEHDRS)  
    $(CPP) $(CLFLAGS) /Yc$(BOUNDRY)    applib.cpp myapp.cpp  
```  
  
 Помимо макросов STABLEHDRS, BOUNDRY и UNSTABLEHDRS, показанных на схеме "Структура файла makefile, использующего предварительно скомпилированный файл заголовка" в [PCH\-файлы в процессе построения](../Topic/PCH%20Files%20in%20the%20Build%20Process.md), этот файл makefile предоставляет макросы CLFLAGS и LINKFLAGS.  Вы можете использовать эти макросы для перечисления параметров компилятора, применимых в зависимости от того, какую версию исполнимого файла программы вы создаете: отладочную или окончательную.  Есть также макрос LIBS, в котором перечислены библиотеки, необходимые вашему проекту.  
  
 Файл makefile также использует \!IF, \!ELSE, \!ENDIF для выявления, определен ли символ DEBUG в командной строке NMAKE:  
  
```  
NMAKE DEBUG=[1|0]  
```  
  
 Эта функция позволяет использовать тот же файл makefile при разработке и в окончательной версии программы — для окончательной версии используйте DEBUG\=0.  Следующие командные строки эквивалентны:  
  
```  
NMAKE   
NMAKE DEBUG=0  
```  
  
 Подробнее о файлах makefile см. в [Справочнике по программе NMAKE](../../build/nmake-reference.md).  Также см. [Параметры компилятора](../../build/reference/compiler-options.md) и [Параметры компоновщика](../../build/reference/linker-options.md).  
  
## См. также  
 [Использование предкомпилированных заголовков в проекте](../../build/reference/using-precompiled-headers-in-a-project.md)