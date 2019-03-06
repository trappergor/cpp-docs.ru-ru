---
title: Файлы определения модуля (DEF)
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: 041894fa88527061d90399540bc29762bff66f81
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424539"
---
# <a name="module-definition-def-files"></a>Файлы определения модуля (DEF)

Файлы определения модуля (DEF) предоставляют сведения о экспортов, атрибуты и другие сведения о программе для связывания для компоновщика. DEF-файл наиболее полезна в случаях, когда построение библиотеки DLL. Так как существуют [параметры компоновщика](../../build/reference/linker-options.md) , можно использовать вместо операторов определения модуля, DEF-файлы обычно не требуются. Можно также использовать [__declspec(dllexport)](../../build/exporting-from-a-dll-using-declspec-dllexport.md) как способ указать экспортируемые функции.

DEF-файл можно вызывать во время на фазе компоновщика с [/DEF (указание файла определения модуля)](../../build/reference/def-specify-module-definition-file.md) параметр компоновщика.

Если вы создаете файл .exe, не имеющего экспортов, с помощью DEF-файла сделает Загрузка файла в выходных данных большего размера и медленнее.

Например, см. в разделе [Экспорт из DLL с использованием DEF-файлы](../../build/exporting-from-a-dll-using-def-files.md).

См. Дополнительные сведения в следующих разделах:

- [Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)

- [EXPORTS](../../build/reference/exports.md)

- [HEAPSIZE](../../build/reference/heapsize.md)

- [LIBRARY](../../build/reference/library.md)

- [ИМЯ](../../build/reference/name-c-cpp.md)

- [РАЗДЕЛЫ](../../build/reference/sections-c-cpp.md)

- [STACKSIZE](../../build/reference/stacksize.md)

- [STUB](../../build/reference/stub.md)

- [ВЕРСИЯ](../../build/reference/version-c-cpp.md)

- [Зарезервированные слова](../../build/reference/reserved-words.md)

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](../../build/reference/c-cpp-building-reference.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
