---
title: OBJ-файлы в качестве входных файлов компоновщика
ms.date: 12/29/2017
helpviewer_keywords:
- linker [C++], OBJ files as input
- object files, linker output
- OMF object files
- LINK tool [C++], .obj files
- COFF files
- OBJ files as linker input
- .obj files as linker input
ms.openlocfilehash: 36f41077fcba6b093865625d426b8009f6185e7b
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450576"
---
# <a name="obj-files-as-linker-input"></a>OBJ-файлы в качестве входных файлов компоновщика

Компоновщик (ссылка. (EXE) принимает OBJ-файлы, которые находятся в общих объекта файла формат COFF.

## <a name="remarks"></a>Примечания

Корпорация Майкрософт предоставляет полное описание в формате. Дополнительные сведения см. в разделе [формата PE](/windows/desktop/Debug/pe-format).

## <a name="unicode-support"></a>Поддержка Юникода

Начиная с Visual Studio 2005, компилятор Microsoft MSVC поддерживает символы Юникода в идентификаторах в соответствии с определением ISO/IEC C и стандартов C++. Предыдущие версии компилятора поддерживали только символы ASCII в идентификаторах. Реализована поддержка Юникода в именах функций, классов и статических элементов, компилятор и компоновщик используют кодировку Юникода UTF-8 для символов COFF в OBJ-файлы. Кодировка UTF-8 восходящая совместим с кодировкой ASCII, используемой в более ранних версиях Visual Studio.

Дополнительные сведения о компиляторе и компоновщике см. в разделе [поддержка Юникода в компиляторе и компоновщике](unicode-support-in-the-compiler-and-linker.md). Дополнительные сведения о стандарте Юникода, см. в разделе [Юникода](https://www.unicode.org/) организации.

## <a name="see-also"></a>См. также

[Входные LINK-файлы](link-input-files.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[Поддержка Юникода](../../text/support-for-unicode.md)<br/>
[Поддержка Юникода в компиляторе и компоновщике](unicode-support-in-the-compiler-and-linker.md)<br/>
[Стандарт Юникод](https://www.unicode.org/)<br/>
[Формат PE](/windows/desktop/Debug/pe-format)
