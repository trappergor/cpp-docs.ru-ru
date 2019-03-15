---
title: Комментарии в файлах makefile
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
ms.openlocfilehash: c66819210d2112f9a68243ed4d3b34f491caae9d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57827513"
---
# <a name="comments-in-a-makefile"></a>Комментарии в файлах makefile

Перед комментарий со знака номера (#). NMAKE игнорирует текст из решетки на следующий символ новой строки. Примеры

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

Чтобы указать литерал решетки, укажите перед ним знак крышки (**^**), как показано ниже:

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>См. также

[Содержимое файла Makefile](contents-of-a-makefile.md)
