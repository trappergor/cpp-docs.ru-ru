---
title: "-PDBPATH | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /pdbpath
dev_langs: C++
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0ccbcedbf9cdd376fa7d9bced5c9d49542cee9f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
 [/ PDBALTPATH (использовать альтернативный PDB путь к файлу)](../../build/reference/pdbaltpath-use-alternate-pdb-path.md)