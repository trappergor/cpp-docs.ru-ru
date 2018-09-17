---
title: -PDBPATH | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /pdbpath
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c9d93ef38ba444fd716bd3363a6605eae66dfec
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45699679"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>Параметры

*filename*<br/>
Имя файла .dll или .exe, для которого требуется найти соответствующий файл PDB.

**: VERBOSE**<br/>
(Необязательно) Сообщает все каталоги, где была предпринята попытка найти PDB-файл.

## <a name="remarks"></a>Примечания

/ PDBPATH выполняет поиск на компьютере по тем же путям, которые отладчик будет выполнять поиск PDB-файл и сообщит о соответствующих, если таковые имеются, PDB-файлы с файлом, указанным в *filename*.

При использовании отладчика Visual Studio, могут возникнуть проблемы из-за того, что отладчик использует PDB-файл для различных версий файла, который при отладке.

/ PDBPATH поиск PDB-файлы по следующим путям:

- Проверьте расположение, где находится исполняемый файл.

- Проверьте расположение PDB-файлов, записанных в исполняемый файл. Обычно это расположение во время образ был связан.

- Проверьте путь поиска, настроенные в интегрированной среде разработки Visual Studio.

- Проверьте по путям в _NT_SYMBOL_PATH и _NT_ALT_SYMBOL_PATH переменные среды.

- Проверьте в каталоге Windows.

## <a name="see-also"></a>См. также

[Параметры DUMPBIN](../../build/reference/dumpbin-options.md)<br/>
[/PDBALTPATH (использование альтернативного пути к файлу PDB)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)