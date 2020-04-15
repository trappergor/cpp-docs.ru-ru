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
ms.openlocfilehash: aec71d4622821618f377953d36a9676e2233eefc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328206"
---
# <a name="link-input-files"></a>Входные LINK-файлы

Вы предоставляете связующее звено файлами, содержащими объекты, библиотеки импорта и стандартных, ресурсы, определения модулей и ввод команд. LINK не использует расширения файлов для предположения о содержимом файла. Вместо этого LINK изучает каждый файл ввода, чтобы определить, что это за файл.

Файлы объектов на командной строке обрабатываются в порядке, в каком они отображаются на командной строке. Библиотеки также ищутся в порядке командной строки со следующим предостережением: символы, которые не решены при внеся файл объекта из библиотеки, сначала ищутся в этой библиотеке, а затем следующие библиотеки из командной строки и [/DEFAULTLIB (Specify Default Library)](defaultlib-specify-default-library.md) директивы, а затем в любых библиотеках в начале командной строки.

> [!NOTE]
> LINK больше не принимает запятую (или любого другого персонажа) в качестве начала комментария в файлах ответа и файлах заказов. Семиколонны распознаются только как начало комментариев в файлах определения модуля (.def).

LINK использует следующие типы входных файлов:

- [.OBJ-файлы](dot-obj-files-as-linker-input.md)

- [файлы .netmodule](netmodule-files-as-linker-input.md)

- [LIB-файлы](dot-lib-files-as-linker-input.md)

- [файлы .exp](dot-exp-files-as-linker-input.md)

- [файлы .def](dot-def-files-as-linker-input.md)

- [PDB-файлы](dot-pdb-files-as-linker-input.md)

- [файлы .res](dot-res-files-as-linker-input.md)

- [файлы .exe](dot-exe-files-as-linker-input.md)

- [TXT-файлы](dot-txt-files-as-linker-input.md)

- [ILK-файлы](dot-ilk-files-as-linker-input.md)

## <a name="see-also"></a>См. также раздел

[Справочник по компоновщику MSVC](linking.md)<br/>
[Варианты MSVC Linker](linker-options.md)
