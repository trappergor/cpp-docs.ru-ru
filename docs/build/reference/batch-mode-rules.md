---
title: Правила пакетного режима
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: f01866e347b2734b5adfd111e3ae9de4f9edcf9f
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826346"
---
# <a name="batch-mode-rules"></a>Правила пакетного режима

```
{frompath}.fromext{topath}.toext::
   commands
```

Правила вывода пакетного режима обеспечивает только один вызов правила вывода, когда N команд пройдут через это правило. Без правила вывода пакетного режима его необходимо N команд для вызова. N — количество зависимых элементов, которые активируют правила вывода.

Файлы makefile, содержащие правила вывода пакетного режима необходимо использовать NMAKE 1.62 или более поздней версии. Чтобы проверить версию NMAKE, запустите макрос _NMAKE_VER, доступный в NMAKE версии 1.62 или более поздней версии. Этот макрос возвращает строку, представляющую версию продукта Visual C++.

Только синтаксические отличия от стандартных правил вывода является то, что правила вывода пакетного режима заканчивается двойное двоеточие (:).

> [!NOTE]
>  Вызываемое средство необходимо иметь возможность обрабатывать несколько файлов. Правила вывода пакетного режима должны использовать `$<` макрос для доступа к зависимых файлов.

Правила вывода пакетного режима может ускорить процесс сборки. Это быстрее предоставить файлы для компилятора в пакете, так как драйвер компилятора вызывается только один раз. Например компилятор C и C++ работает быстрее при обработке набора файлов, так как он может оставаться в памяти во время процесса.

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

NMAKE создает следующие выходные данные без правила вывода пакетного режима:

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

NMAKE выдает следующий результат с помощью правила вывода пакетного режима:

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

[Правила вывода](inference-rules.md)
