---
title: PDB-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 23974a9e20f8259c3a38af15664d328ded7ff7d6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628904"
---
# <a name="pdb-files-as-linker-input"></a>PDB-файлы в качестве входных файлов компоновщика

Объект, имя базы данных программы (PDB) содержат файлы (OBJ), скомпилированные с помощью параметра/Zi. Вы не укажете имя PDB-файла объекта в компоновщик; ССЫЛКА использует внедренное имя для поиска PDB-ФАЙЛ, при необходимости. Это также относится к отлаживаемых объектов, содержащихся в библиотеке. PDB-ФАЙЛ для отлаживаемой библиотеки должен быть доступен в компоновщик вместе с библиотекой.

ССЫЛКА для хранения отладочная информация для файла .exe или DLL-файл также используется PDB-файла. PDB-ФАЙЛ программы обусловлено выходной файл и входной файл, ссылка обновляет PDB при перестроением программы.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)