---
title: Правила пакетного режима | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b002b17fcc70ff4e374fb0630e9c18a52cbfc4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361448"
---
# <a name="batch-mode-rules"></a>Правила пакетного режима
```  
{frompath}.fromext{topath}.toext::  
   commands  
```  
  
 Правила вывода пакетного режима обеспечивает только один вызов правила вывода, когда N команд пройдут через это правило. Без использования правил вывода пакетного режима это требует N команд для вызова. N — число зависимых компонентов, которые запускают правила вывода.  
  
 Makefile-файлы, содержащие правила вывода пакетного режима необходимо использовать NMAKE 1.62 или более поздней версии. Чтобы проверить версию NMAKE, запустите макрос _NMAKE_VER, доступный в NMAKE версии 1.62 или более поздней версии. Этот макрос возвращает строку, представляющую версию продукта Visual C++.  
  
 Единственным синтаксическим отличием от стандартных правил вывода является то, что правила вывода пакетного режима заканчивается двойное двоеточие (:).  
  
> [!NOTE]
>  Средство вызова должен быть способен обрабатывать несколько файлов. Правила вывода пакетного режима должны использовать `$<` макрос для доступа к зависимые файлы.  
  
 Правила вывода пакетного режима можно ускорить процесс построения. Проще указать файлы для компилятора в пакете, так как драйвер компилятора вызывается только один раз. Например компилятор C и C++ работает быстрее при обработке набора файлов, так как он может оставаться в памяти во время процесса.  
  
 В следующем примере показано, как использовать правила вывода пакетного режима:  
  
```  
#  
# sample makefile to illustrate batch-mode inference rules  
#  
O = .  
S = .  
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj  
CFLAGS = -nologo  
  
all : $(Objs)  
  
!ifdef NOBatch  
{$S}.cpp{$O}.obj:  
!else  
{$S}.cpp{$O}.obj::  
!endif  
   $(CC) $(CFLAGS) -Fd$O\ -c $<  
  
$(Objs) :  
  
#end of makefile  
```  
  
 NMAKE выводятся следующие данные без правила вывода пакетного режима:  
  
```  
E:\tmp> nmake -f test.mak -a NOBatch=1  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
        cl -nologo -Fd.\ -c .\foo1.cpp  
foo1.cpp  
        cl -nologo -Fd.\ -c .\foo2.cpp  
foo2.cpp  
        cl -nologo -Fd.\ -c .\foo3.cpp  
foo3.cpp  
        cl -nologo -Fd.\ -c .\foo4.cpp  
foo4.cpp  
```  
  
 С помощью правила вывода пакетного режима (NMAKE) выводит следующее:  
  
```  
E:\tmp> nmake -f test.mak -a  
  
Microsoft (R) Program Maintenance Utility   Version 7.00.0000  
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.  
  
        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp  
foo1.cpp  
foo2.cpp  
foo3.cpp  
foo4.cpp  
Generating Code...  
```  
  
## <a name="see-also"></a>См. также  
 [Правила вывода](../build/inference-rules.md)