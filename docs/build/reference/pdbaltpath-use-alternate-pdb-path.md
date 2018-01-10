---
title: "-PDBALTPATH (использовать альтернативный PDB путь к файлу) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /pdbaltpath
dev_langs: C++
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9053bc206a465eb32d8007fb8d58d13d45eb4a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH (использовать альтернативный путь к PDB-файлу)
```  
/PDBALTPATH:pdb_file_name  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *pdb_file_name*  
 Путь к файлу PDB и его имя.  
  
## <a name="remarks"></a>Примечания  
 Этот параметр используется, чтобы указать альтернативное расположение для файла базы данных программы (PDB) в скомпилированном двоичном файле. В общем случае компоновщик записывает расположение файла PDB в создаваемых двоичных файлах. Этот параметр можно использовать для указания другого пути и имени файла PDB. Информация, предоставляемая с помощью параметра /PDBALTPATH, не изменяет фактическое расположение и имя файла PDB; изменяется лишь информация, записываемая компоновщиком в двоичный файл. Это позволяет указать путь, не зависящий от структуры файлов на компьютере, на котором выполняется сборка. Наиболее распространенные случаи применения этого параметра — указание сетевого пути или файла, не имеющего данных о пути.  
  
 Значение *pdb_file_name* может быть произвольной строкой, переменной среды или **% _PDB %**. Компоновщик расширяет переменную среды, такую как **% SystemRoot %**, чтобы его значение. Компоновщик определяет переменные среды **% _PDB %** и **% _EXT %**. **% _PDB %** разворачивается в имя файла фактического файла PDB без включения данных пути и **% _EXT %** — это расширение создаваемого исполняемого файла.  
  
## <a name="see-also"></a>См. также  
 [Параметры DUMPBIN](../../build/reference/dumpbin-options.md)   
 [/ PDBPATH](../../build/reference/pdbpath.md)