---
title: Правила пакетного режима
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 38402e7b8a937cebb823ce13fa1ac01fc1099878
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328414"
---
# <a name="batch-mode-rules"></a>Правила пакетного режима

```
{frompath}.fromext{topath}.toext::
   commands
```

Правила выводов пакетного режима предоставляют только один вызов правила выводов, когда команды N проходят через это правило выводов. Без правил размыва пакетного режима потребуется вызов команд N. N — это количество иждивенцев, которые запускают правило выводов.

Makefiles, содержащие правила выводов пакетного режима, должны использовать версию NMAKE 1.62 или выше. Чтобы проверить версию NMAKE, запустите _NMAKE_VER макрос, доступный с версией NMAKE 1.62 или выше. Этот макрос возвращает строку, представляющую версию продукта Visual C'.

Единственное синтаксисическое отличие от стандартного правила выводов состоит в том, что правило выводов пакетного режима прекращается с двойной толстой кишки (:::).

> [!NOTE]
> Вызов инструмента должен быть в состоянии обрабатывать несколько файлов. Правило выводов пакетного режима `$<` должно использоваться в качестве макроса для доступа к зависимым файлам.

Правила выводов пакетного режима могут ускорить процесс сборки. Быстрее поставлять файлы компилятору в пакете, так как драйвер компилятора вызывается только один раз. Например, компилятор C и C's работает лучше при обработке набора файлов, поскольку он может оставаться резидентом памяти во время процесса.

Ниже приводится следующий пример, как использовать правила размыва пакетного режима:

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

NMAKE производит следующие выходные данные без правил вывода пакетного режима:

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

NMAKE производит следующий результат с правилами выводов пакетного режима:

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

## <a name="see-also"></a>См. также раздел

[Правила выводов](inference-rules.md)
