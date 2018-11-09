---
title: Флаги управления
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
ms.openlocfilehash: 45349099ed5c607468430d2f0a901c6374d88fc7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475742"
---
# <a name="control-flags"></a>Флаги управления

Отладочная версия библиотеки времени выполнения Microsoft C использует следующие флаги для управления выделением памяти в куче и процессом создания отчетов. Дополнительные сведения см. в статье [Методы отладки CRT](/visualstudio/debugger/crt-debugging-techniques).

|Flag|Описание:|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|Сопоставляет основные функции кучи и их отладочные версии|
|[_DEBUG](../c-runtime-library/debug.md)|Позволяет использовать отладочные версий функций среды выполнения|
|[_crtDbgFlag](../c-runtime-library/crtdbgflag.md)|Контролирует способ отслеживания выделения памяти отладочным диспетчером кучи|

Эти флаги можно определить с помощью параметра командной строки /D или с помощью директивы `#define`. Если этот флаг определяется с помощью директивы `#define`, она должна предшествовать оператору включения заголовочного файла, содержащего объявления подпрограмм.

## <a name="see-also"></a>См. также

[Глобальные переменные и стандартные типы](../c-runtime-library/global-variables-and-standard-types.md)