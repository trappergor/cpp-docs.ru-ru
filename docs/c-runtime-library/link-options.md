---
title: Параметры ссылок
ms.date: 11/04/2016
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- legacy_stdio_float_rounding.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
ms.openlocfilehash: ea71faab639a8c0a09d6e332618dd7e09159a4e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351101"
---
# <a name="link-options"></a>Параметры ссылок

Каталог библиотек CRT содержит ряд небольших файлов объектов, которые обеспечивают работу определенных функций CRT без изменения кода. Они называются "параметрами ссылок", так как для их использования нужно только добавить эти параметры в командную строку постановщика.

Версии этих объектов в чистом режиме среды CLR отмечены как нерекомендуемые для использования в Visual Studio 2015 и не поддерживаются в Visual Studio 2017. Используйте обычные версии для машинного кода и кода /clr.

|Машинный код и /clr|Чистый режим|Описание|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|Устанавливает в качестве режима преобразования файлов по умолчанию двоичный режим. См. раздел [_fmode](../c-runtime-library/fmode.md).|
|chkstk.obj|Недоступно|Обеспечивает поддержку проверки и распределения стека, если CRT не используется.|
|commode.obj|pcommode.obj|Присваивает глобальному флагу фиксации значение "commit". См. раздел [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) и [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|
|exe_initialize_mta.lib|Недоступно|Инициализирует подразделение MTA во время запуска EXE-файла, который позволяет использовать COM-объекты в глобальных интеллектуальных указателях. Так как этот параметр выдает ссылку на подразделение MTA во время завершения работы, не используйте его для библиотек DLL. Ссылка эквивалентна включению combase.h и определению _EXE_INITIALIZE_MTA. |
|fp10.obj|Недоступно|Изменяет управление точностью по умолчанию на 64 бита. См. раздел [Поддержка чисел с плавающей запятой](../c-runtime-library/floating-point-support.md).|
|invalidcontinue.obj|pinvalidcontinue.obj|Определяет обработчик недопустимых параметров по умолчанию, который не делает ничего, т. е. недопустимые параметры, передаваемые в функции CRT, получают значение errno и возвращают ошибку.|
|legacy_stdio_float_rounding.obj|Недоступно|Исправлена печать значений плавающей точки (например, при использовании [printf)](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)с помощью Windows 10 19041 Universal C Runtime. Теперь он правильно раундов точно представлены плавающие точки номера, и уважает плавающей точки округления просил [fesetenv](../c-runtime-library/reference/fesetenv1.md). Это обновление поведения доступно в версии Visual Studio 2019 16.2 и позже. Наследие поведение используется в более ранних версиях Visual Studio, или, предоставляя эту ссылку вариант.|
|loosefpmath.obj|Недоступно|Гарантирует, что код с плавающей точкой кода допускает нестандартные значения.|
|newmode.obj|pnewmode.obj|Заставляет [malloc](../c-runtime-library/reference/malloc.md) в случае ошибки вызывать новый обработчик. См. разделы [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md) и [realloc](../c-runtime-library/reference/realloc.md).|
|noarg.obj|pnoarg.obj|Отключает обработку аргументов argc и argv.|
|nochkclr.obj|Недоступно|Не выполняет никаких действий. Удалите из проекта.|
|noenv.obj|pnoenv.obj|Отключает создание кэшированной среды для CRT.|
|nothrownew.obj|pnothrownew.obj|Позволяет использовать внеочередную версию новых функций в CRT. См. раздел [Операторы new и delete](../cpp/new-and-delete-operators.md).|
|setargv.obj|psetargv.obj|Включает расширение аргументов заполнителей в командной строке. См. раздел [Расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).|
|threadlocale.obj|pthreadlocale.obj|Включает языковой стандарт отдельного потока для всех новых потоков по умолчанию.|
|wsetargv.obj|pwsetargv.obj|Включает расширение аргументов заполнителей в командной строке. См. раздел [Расширение аргументов заполнителей](../c-language/expanding-wildcard-arguments.md).|

## <a name="see-also"></a>См. также раздел

- [Особенности библиотеки CRT](../c-runtime-library/crt-library-features.md)
