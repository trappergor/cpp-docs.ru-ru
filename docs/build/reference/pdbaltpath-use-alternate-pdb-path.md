---
title: /PDBALTPATH (использовать альтернативный путь к PDB-файлу)
ms.date: 11/04/2016
f1_keywords:
- /pdbaltpath
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
ms.openlocfilehash: 22bc53858aca3b037655829bd7449049971ca79f
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57419197"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (использовать альтернативный путь к PDB-файлу)

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>Аргументы

*pdb_file_name*<br/>
Путь к файлу PDB и его имя.

## <a name="remarks"></a>Примечания

Этот параметр используется, чтобы указать альтернативное расположение для файла базы данных программы (PDB) в скомпилированном двоичном файле. В общем случае компоновщик записывает расположение файла PDB в создаваемых двоичных файлах. Этот параметр можно использовать для указания другого пути и имени файла PDB. Информация, предоставляемая с помощью параметра /PDBALTPATH, не изменяет фактическое расположение и имя файла PDB; изменяется лишь информация, записываемая компоновщиком в двоичный файл. Это позволяет указать путь, не зависящий от структуры файлов на компьютере, на котором выполняется сборка. Наиболее распространенные случаи применения этого параметра — указание сетевого пути или файла, не имеющего данных о пути.

Значение *pdb_file_name* может быть произвольной строкой, переменной среды или **% _PDB %**. Компоновщик расширяет переменную среды, такие как **% SystemRoot %**, чтобы его значение. Компоновщик определяет переменные среды **% _PDB %** и **% _EXT %**. **% _PDB %** расширяется до имени фактического файла PDB без включения данных пути и **% _EXT %** — это расширение создаваемого исполняемого файла.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)<br/>
[/PDBPATH](../../build/reference/pdbpath.md)
