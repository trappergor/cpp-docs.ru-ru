---
title: . PDB-файлы в качестве входных данных компоновщика | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f6707be955b5c4a332d1162f53b1cb854391a2ce
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="pdb-files-as-linker-input"></a>PDB-файлы в качестве входных файлов компоновщика
Объект, имя базы данных программы (PDB) содержит файлы (.obj), скомпилированные с помощью параметра/Zi. Не следует указывать имя файла PDB объекта компоновщику; СВЯЗЬ используется внедренное имя для поиска PDB-ФАЙЛ, если это требуется. Это также относится к отлаживаемым объектам, содержащимся в библиотеке. PDB-ФАЙЛ для отлаживаемой библиотеки должен быть доступен компоновщику вместе с библиотекой.  
  
 ССЫЛКА для хранения сведения об отладке для файла .exe или DLL-файл также используется PDB-ФАЙЛ. PDB-файла программы в том, выходной файл и входной файл, LINK обновляет PDB при перестраивает программы.  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)