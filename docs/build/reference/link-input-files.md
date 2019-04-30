---
title: Входные LINK-файлы
ms.date: 11/04/2016
f1_keywords:
- link
helpviewer_keywords:
- files [C++], LINK
- module definition files
- resources [C++], linker files
- LINK tool [C++], input files
- module definition files, linker files
- input files [C++], LINK
- linker [C++], input files
- import libraries [C++], linker files
- command input to linker files [C++]
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
ms.openlocfilehash: 48ad9423ae35c22a97a873fe6a2a0479c12ab33b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291513"
---
# <a name="link-input-files"></a>Входные LINK-файлы

Компоновщик предоставить файлы, содержащие объекты, импортировать и стандартные библиотеки, ресурсов, определения модуля и ввод команд. ССЫЛКА не использует расширения файлов для делать предположения о содержимом файла. Вместо этого ссылка анализирует каждый входной файл, чтобы определить, какого рода файл.

Объектные файлы в командной строке, обрабатываются в порядке их следования в командной строке. Библиотеки осуществляется в порядке командной строки, а также с использованием следующих механизмов: Неразрешенные символы при переводе в объектный файл из библиотеки ищутся в эту библиотеку во-первых, а затем перечисленные ниже библиотеки из командной строки и [/DEFAULTLIB (укажите библиотеку по умолчанию)](defaultlib-specify-default-library.md) директивы, а затем на библиотеки в начале командной строки.

> [!NOTE]
>  ССЫЛКА больше не принимает точку с запятой (или любой другой символ) как начало комментария в файлы ответов и упорядочение файлов. Точка с запятой, распознаются только как начало комментариев в файлах определения модуля (.def).

СВЯЗИ используются следующие типы входных файлов:

- [OBJ-файлы](dot-obj-files-as-linker-input.md)

- [NETMODULE-файлы](netmodule-files-as-linker-input.md)

- [LIB-файлы](dot-lib-files-as-linker-input.md)

- [EXP-файлы](dot-exp-files-as-linker-input.md)

- [DEF-файлы](dot-def-files-as-linker-input.md)

- [PDB-файлы](dot-pdb-files-as-linker-input.md)

- [RES-файлы](dot-res-files-as-linker-input.md)

- [файлы .exe](dot-exe-files-as-linker-input.md)

- [TXT-файлов](dot-txt-files-as-linker-input.md)

- [ILK-файлы](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
