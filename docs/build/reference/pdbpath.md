---
title: -PDBPATH | Документы Microsoft
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
ms.openlocfilehash: 274c4a3742d99b1e4702ed332206b78dacebccbd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="pdbpath"></a>/PDBPATH
```  
/PDBPATH[:VERBOSE] filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Имя файла .dll или .exe, для которого требуется найти соответствующий файл PDB.  
  
 VERBOSE (необязательно)  
 Сообщает все каталоги, где была предпринята попытка найти PDB-файл.  
  
## <a name="remarks"></a>Примечания  
 / PDBPATH поиск производится на компьютере по тем же путям, отладчик может найти PDB-файл и сообщает соответствующие, если таковые имеются, PDB-файлы для файла, указанного в *filename*.  
  
 При использовании отладчика Visual Studio, проблема может возникнуть из-за того, что отладчик использует PDB-файл для различных версий файла, для которого выполняется отладка.  
  
 / PDBPATH поиск PDB-файлов по следующим путям:  
  
-   Проверьте расположение, где находится исполняемый файл.  
  
-   Проверьте расположение PDB-ФАЙЛ, записанных в исполняемый файл. Обычно это расположение во время образ был связан.  
  
-   Проверьте путь поиска, настроенные в Интегрированной среде разработки Visual Studio.  
  
-   Проверьте по путям в _NT_SYMBOL_PATH и _NT_ALT_SYMBOL_PATH переменные среды.  
  
-   Проверьте в каталоге Windows.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)   
 [/PDBALTPATH (использование альтернативного пути к файлу PDB)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)