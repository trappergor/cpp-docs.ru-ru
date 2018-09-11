---
title: . OBJ-файлы в качестве входных данных компоновщика | Документация Майкрософт
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bd1fbd635b1d3d3a5f9963edaa9f22e22472dad1
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691755"
---
# <a name="obj-files-as-linker-input"></a>OBJ-файлы в качестве входных файлов компоновщика

Компоновщик (ссылка. (EXE) принимает OBJ-файлы, которые находятся в общих объекта файла формат COFF.

## <a name="remarks"></a>Примечания

Корпорация Майкрософт предоставляет полное описание в формате. Дополнительные сведения см. в разделе [формата PE](/windows/desktop/Debug/pe-format).

## <a name="unicode-support"></a>Поддержка Юникода

Начиная с Visual Studio 2005, компилятор Microsoft Visual C++ поддерживает символы Юникода в идентификаторах в соответствии с определением ISO/IEC C и стандартов C++. Предыдущие версии компилятора поддерживали только символы ASCII в идентификаторах. Реализована поддержка Юникода в именах функций, классов и статических элементов, компилятор и компоновщик используют кодировку Юникода UTF-8 для символов COFF в OBJ-файлы. Кодировка UTF-8 восходящая совместим с кодировкой ASCII, используемой в более ранних версиях Visual Studio.

Дополнительные сведения о компиляторе и компоновщике см. в разделе [поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Дополнительные сведения о стандарте Юникода, см. в разделе [Юникода](http://www.unicode.org/) организации.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)  
[Поддержка Юникода](../../text/support-for-unicode.md)  
[Поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Стандарт Юникод](http://www.unicode.org/)  
[Формат PE](/windows/desktop/Debug/pe-format)  
