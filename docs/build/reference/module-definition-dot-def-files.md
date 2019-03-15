---
title: Файлы определения модуля (DEF)
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: 0047f24722644cd9a68bbbf827ced26ad085d4c1
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812243"
---
# <a name="module-definition-def-files"></a>Файлы определения модуля (DEF)

Файлы определения модуля (DEF) предоставляют сведения о экспортов, атрибуты и другие сведения о программе для связывания для компоновщика. DEF-файл наиболее полезна в случаях, когда построение библиотеки DLL. Так как существуют [параметры компоновщика MSVC](linker-options.md) , можно использовать вместо операторов определения модуля, DEF-файлы обычно не требуются. Можно также использовать [__declspec(dllexport)](../exporting-from-a-dll-using-declspec-dllexport.md) как способ указать экспортируемые функции.

DEF-файл можно вызывать во время на фазе компоновщика с [/DEF (указание файла определения модуля)](def-specify-module-definition-file.md) параметр компоновщика.

Если вы создаете файл .exe, не имеющего экспортов, с помощью DEF-файла сделает Загрузка файла в выходных данных большего размера и медленнее.

Например, см. в разделе [Экспорт из DLL с использованием DEF-файлы](../exporting-from-a-dll-using-def-files.md).

См. Дополнительные сведения в следующих разделах:

- [Правила для операторов определения модуля](rules-for-module-definition-statements.md)

- [EXPORTS](exports.md)

- [HEAPSIZE](heapsize.md)

- [LIBRARY](library.md)

- [ИМЯ](name-c-cpp.md)

- [РАЗДЕЛЫ](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [STUB](stub.md)

- [ВЕРСИЯ](version-c-cpp.md)

- [Зарезервированные слова](reserved-words.md)

## <a name="see-also"></a>См. также

[Справочные сведения о сборке C/C++](c-cpp-building-reference.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
