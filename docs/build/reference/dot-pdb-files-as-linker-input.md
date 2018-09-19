---
title: . PDB-файлы в качестве входных данных компоновщика | Документация Майкрософт
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
ms.openlocfilehash: d6b728903d2a270efc6b3eb736e45540651dae8c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706190"
---
# <a name="pdb-files-as-linker-input"></a>PDB-файлы в качестве входных файлов компоновщика

Объект, имя базы данных программы (PDB) содержат файлы (OBJ), скомпилированные с помощью параметра/Zi. Вы не укажете имя PDB-файла объекта в компоновщик; ССЫЛКА использует внедренное имя для поиска PDB-ФАЙЛ, при необходимости. Это также относится к отлаживаемых объектов, содержащихся в библиотеке. PDB-ФАЙЛ для отлаживаемой библиотеки должен быть доступен в компоновщик вместе с библиотекой.

ССЫЛКА для хранения отладочная информация для файла .exe или DLL-файл также используется PDB-файла. PDB-ФАЙЛ программы обусловлено выходной файл и входной файл, ссылка обновляет PDB при перестроением программы.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)