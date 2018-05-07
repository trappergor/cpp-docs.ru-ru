---
title: . EXP-файлы в качестве входных данных компоновщика | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f9b5c118e81372bd57810a9472526909ed21f765
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="exp-files-as-linker-input"></a>EXP-файлы в качестве входных файлов компоновщика
Файлы экспорта (EXP) содержат сведения о экспортируемые элементы функции и данные. Когда LIB создает библиотеку импорта, она также создает файл EXP. EXP-файл используется при компоновке программы, экспорт и импорт из другой программы, прямо или косвенно. При компоновке с EXP-файл, СВЯЗИ не создает библиотеку импорта, поскольку предполагается, что LIB уже создан. Дополнительные сведения о EXP файлы и библиотеки импорта в разделе [работа с библиотеками, импортировать и экспортировать файлы](../../build/reference/working-with-import-libraries-and-export-files.md).  
  
## <a name="see-also"></a>См. также  
 [Входные LINK-файлы](../../build/reference/link-input-files.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)