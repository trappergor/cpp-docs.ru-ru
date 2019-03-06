---
title: /PDBPATH
ms.date: 11/04/2016
f1_keywords:
- /pdbpath
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
ms.openlocfilehash: e59f36905bcb9eb379e2bc17c9041b81fd98a535
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57420041"
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
