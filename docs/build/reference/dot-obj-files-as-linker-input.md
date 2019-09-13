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
ms.openlocfilehash: 3e02ccc09ae8c9c2f3df88bc1767ff0188baa1f4
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492939"
---
# <a name="obj-files-as-linker-input"></a>OBJ-файлы в качестве входных файлов компоновщика

Инструмент компоновщика (ссылка. EXE) принимает OBJ-файлы, которые находятся в формате COFF.

## <a name="remarks"></a>Примечания

Корпорация Майкрософт предоставляет полное описание формата общего объектного файла. Дополнительные сведения см. в разделе [Формат PE](/windows/win32/Debug/pe-format).

## <a name="unicode-support"></a>Поддержка Юникода

Начиная с Visual Studio 2005 компилятор Microsoft КОМПИЛЯТОРОМ MSVC поддерживает символы Юникода в идентификаторах, как определено стандартом ISO/IEC C и C++ стандартами. Предыдущие версии компилятора поддерживали только символы ASCII в идентификаторах. Для поддержки Юникода в именах функций, классов и статических элементов компилятор и компоновщик используют кодировку Юникод UTF-8 для символов COFF в OBJ-файлах. Кодировка UTF-8 обеспечивает обратную совместимость с кодировкой ASCII, используемой в более ранних версиях Visual Studio.

Дополнительные сведения о компиляторе и компоновщике см. в разделе [Поддержка Юникода в компиляторе и компоновщике](unicode-support-in-the-compiler-and-linker.md). Дополнительные сведения о стандарте Unicode см. в разделе Организация [Юникода](https://www.unicode.org/) .

## <a name="see-also"></a>См. также

[Входные LINK-файлы](link-input-files.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)<br/>
[Поддержка Юникода](../../text/support-for-unicode.md)<br/>
[Поддержка Юникода в компиляторе и компоновщике](unicode-support-in-the-compiler-and-linker.md)<br/>
[Стандарт Юникод](https://www.unicode.org/)<br/>
[Формат PE](/windows/win32/Debug/pe-format)
