---
title: Входные LINK-файлы
ms.date: 11/04/2016
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
ms.openlocfilehash: 25d8e20903a97186e2c32a079fd74ece3626b7fa
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439338"
---
# <a name="link-input-files"></a>Входные LINK-файлы

Компоновщик предоставляет файлы, содержащие объекты, импорт и стандартные библиотеки, ресурсы, определения модулей и входные данные команды. LINK не использует расширения файлов, чтобы делать предположения о содержимом файла. Вместо этого LINK проверяет каждый входной файл для определения типа файла.

Объектные файлы в командной строке обрабатываются в том порядке, в котором они отображаются в командной строке. Поиск в библиотеках осуществляется в порядке командной строки, со следующими оговорками: символы, которые не разрешены при переводе в объектный файл из библиотеки, сначала ищутся в этой библиотеке, а затем из командной строки и директив [параметр/DEFAULTLIB (указание библиотеки по умолчанию)](defaultlib-specify-default-library.md) , а затем в любые библиотеки в начале командной строки.

> [!NOTE]
>  ССЫЛКА больше не принимает точку с запятой (или любой другой символ) в качестве начала комментария в файлах ответов и файлах упорядочения. Точки с запятой распознаются только в качестве начала комментариев в файлах определения модуля (DEF).

LINK использует следующие типы входных файлов:

- [OBJ-файлы](dot-obj-files-as-linker-input.md)

- [файлы NETMODULE](netmodule-files-as-linker-input.md)

- [LIB файлы](dot-lib-files-as-linker-input.md)

- [файлы exp](dot-exp-files-as-linker-input.md)

- [DEF, файлы](dot-def-files-as-linker-input.md)

- [PDB-файлы](dot-pdb-files-as-linker-input.md)

- [RES файлы](dot-res-files-as-linker-input.md)

- [exe, файлы](dot-exe-files-as-linker-input.md)

- [txt, файлы](dot-txt-files-as-linker-input.md)

- [ILK файлы](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
