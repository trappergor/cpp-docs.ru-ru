---
title: ". OBJ-файлы в качестве входных данных компоновщика | Документы Microsoft"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a2896822e97bdbb5ffdf8f869e67beadc1675b7
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="obj-files-as-linker-input"></a>OBJ-файлы в качестве входных файлов компоновщика

Инструмент-компоновщик (ссылка. (EXE) принимает OBJ-файлы, которые в общих объекта файла формат COFF.

## <a name="remarks"></a>Примечания

Корпорация Майкрософт предоставляет полное описание формате. Дополнительные сведения см. в разделе [формата PE](https://msdn.microsoft.com/library/windows/desktop/ms680547).

## <a name="unicode-support"></a>Поддержка Юникода

Начиная с Visual Studio 2005, компилятор Microsoft Visual C++ поддерживает символы Юникода в идентификаторах в соответствии с определением ISO/IEC C и C++ стандартов. Предыдущие версии компилятора поддерживается только символы ASCII в качестве идентификаторов. Поддержка Юникода в именах функций, классов и статических переменных, компилятор и компоновщик используют кодировку Юникод UTF-8 для символов COFF в OBJ-файлы. Кодировка UTF-8 восходящая совместим с кодировкой ASCII, используемой в более ранних версиях Visual Studio.

Дополнительные сведения о компиляторе и компоновщике см. в разделе [поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md). Дополнительные сведения о стандарте Юникод см. в разделе [Юникода](http://go.microsoft.com/fwlink/p/?linkid=37123) организации.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](../../build/reference/link-input-files.md)  
[Параметры компоновщика](../../build/reference/linker-options.md)  
[Поддержка Юникода](../../text/support-for-unicode.md)  
[Поддержка Юникода в компиляторе и компоновщике](../../build/reference/unicode-support-in-the-compiler-and-linker.md)  
[Стандарт Юникод](http://go.microsoft.com/fwlink/p/?linkid=37123)  
[Формат PE](https://msdn.microsoft.com/library/windows/desktop/ms680547)  
