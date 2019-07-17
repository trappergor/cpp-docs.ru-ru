---
title: /DEPENDENTS
ms.date: 07/15/2019
f1_keywords:
- /dependents
helpviewer_keywords:
- -DEPENDENTS dumpbin option
- /DEPENDENTS dumpbin option
- DEPENDENTS dumpbin option
ms.assetid: 9b31da2a-75ac-4bbf-a3f1-adf8b0ecbbb4
ms.openlocfilehash: 88f0062a6bbca3f9199a12f739c2ade5f9d912cd
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299747"
---
# <a name="dependents"></a>/DEPENDENTS

Создает дамп имен библиотек DLL, из которых изображение импортирует функции. Вы можете использовать этот список, чтобы определить, какие библиотеки DLL следует распространить вместе с приложением, или найти имя отсутствующей зависимости.

## <a name="syntax"></a>Синтаксис

> **/DEPENDENTS**

Этот параметр применяется ко всем исполняемым файлам, указанным в командной строке. Он не принимает никаких аргументов.

## <a name="remarks"></a>Примечания

Параметр **/депендентс** добавляет имена библиотек DLL, из которых изображение импортирует функции в выходные данные. Этот параметр не выводит имена импортированных функций. Чтобы просмотреть имена импортированных функций, используйте параметр [/Imports](imports-dumpbin.md) .

С файлами, созданными с использованием параметра компилятора [/GL](gl-whole-program-optimization.md), можно использовать только параметр DUMPBIN [/HEADERS](headers.md).

## <a name="example"></a>Пример

В этом примере показаны выходные данные DUMPBIN параметра **/депендентс** на клиентском исполняемом файле, [встроенном в пошаговом руководстве: Создайте и используйте собственную библиотеку](../walkthrough-creating-and-using-a-dynamic-link-library-cpp.md)динамической компоновки:

```cmd
C:\Users\username\Source\Repos\MathClient\Debug>dumpbin /DEPENDENTS MathClient.exe
Microsoft (R) COFF/PE Dumper Version 14.16.27032.1
Copyright (C) Microsoft Corporation.  All rights reserved.


Dump of file MathClient1322.exe

File Type: EXECUTABLE IMAGE

  Image has the following dependencies:

    MathLibrary.dll
    MSVCP140D.dll
    VCRUNTIME140D.dll
    ucrtbased.dll
    KERNEL32.dll

  Summary

        1000 .00cfg
        1000 .data
        2000 .idata
        1000 .msvcjmc
        3000 .rdata
        1000 .reloc
        1000 .rsrc
        8000 .text
       10000 .textbss
```

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](dumpbin-options.md)
