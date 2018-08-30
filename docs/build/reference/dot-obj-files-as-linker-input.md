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
ms.openlocfilehash: ffbc1d7fc7f74121c37c9e80a538ec60f2265701
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219566"
---
# <a name="obj-files-as-linker-input"></a>OBJ-файлы в качестве входных файлов компоновщика

Компоновщик (ссылка. (EXE) принимает OBJ-файлы, которые находятся в общих объекта файла формат COFF.

## <a name="remarks"></a>Примечания

Корпорация Майкрософт предоставляет полное описание в формате. Дополнительные сведения см. в разделе [формата PE](/windows/desktop/Debug/pe-format).

## <a name="unicode-support"></a>Поддержка Юникода

Начиная с Visual Studio 2005, компилятор Microsoft Visual C++ поддерживает символы Юникода в идентификаторах в соответствии с определением ISO/IEC C и стандартов C++. Предыдущие версии компилятора поддерживали только символы ASCII в идентификаторах. Реализована поддержка Юникода в именах функций, классов и статических элементов, компилятор и компоновщик используют кодировку Юникода UTF-8 для символов COFF в OBJ-файлы. Кодировка UTF-8 восходящая совместим с кодировкой ASCII, используемой в более ранних версиях Visual Studio.

Дополнительные сведения о компиляторе и компоновщике см. в разделе [поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Дополнительные сведения о стандарте Юникода, см. в разделе [Юникода](http://go.microsoft.com/fwlink/p/?linkid=37123) организации.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)  
[Поддержка Юникода](../../text/support-for-unicode.md)  
[Поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Стандарт Юникод](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[Формат PE](/windows/desktop/Debug/pe-format)  
