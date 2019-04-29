---
title: EXP-файлы в качестве входных файлов компоновщика
ms.date: 11/04/2016
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
ms.openlocfilehash: 0f2f5c22752d6d938700228fc208c21b8f32cc7b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62293671"
---
# <a name="exp-files-as-linker-input"></a>EXP-файлы в качестве входных файлов компоновщика

Файлы экспорта (EXP) содержат сведения о экспортируемые элементы функции и данные. Когда LIB создает библиотеку импорта, она также создает файл EXP. EXP-файл используется при связывании это программа, которая экспортирует и импортирует из другой программы, прямо или косвенно. При компоновке с EXP-файл, LINK не создает библиотеку импорта, так как предполагается, что LIB уже создана. Дополнительные сведения о EXP-файлы и библиотеки импорта, см. в разделе [работа с библиотеками, импортировать и экспортировать файлы](working-with-import-libraries-and-export-files.md).

## <a name="see-also"></a>См. также

[Входные LINK-файлы](link-input-files.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
