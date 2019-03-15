---
title: /Fx (объединение подставляемого кода)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExpandAttributedSource
- /Fx
- VC.Project.VCCLCompilerTool.ExpandAttributedSource
helpviewer_keywords:
- Fx compiler option [C++]
- -Fx compiler option [C++]
- injected code
- merging injected code
- /Fx compiler option [C++]
ms.assetid: 14f0e301-3bab-45a3-bbdf-e7ce66f20560
ms.openlocfilehash: f1a266eee4edc524fbbe49bdef31a8235f62bd3c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818145"
---
# <a name="fx-merge-injected-code"></a>/Fx (объединение подставляемого кода)

Создает копию всех исходных файлов с подставляемым кодом, объединенным с исходным кодом.

## <a name="syntax"></a>Синтаксис

```
/Fx
```

## <a name="remarks"></a>Примечания

Чтобы отделить объединенный исходный файл от оригинального исходного файла, **/Fx** добавляет расширение MRG между именем файла и его расширением. Например, файл с именем MyCode.cpp, который включает код с атрибутами и собран с помощью с **/Fx** , порождает файл с именем MyCode.mrg.cpp, который содержит следующий код:

```
//+++ Start Injected Code
[no_injected_text(true)];      // Suppress injected text, it has
                               // already been injected
#pragma warning(disable: 4543) // Suppress warnings about skipping
                               // injected text
#pragma warning(disable: 4199) // Suppress warnings from attribute
                               // providers
//--- End Injected Code
```

В MRG-файле код, подставленный из-за наличия атрибута, будет отделен следующим образом:

```
//+++ Start Injected Code
...
//--- End Injected Code
```

Атрибут [no_injected_text](../../windows/no-injected-text.md) встроен в MRG-файл, что допускает компиляцию MRG-файла без повторной подстановки текста.

Обратите внимание, что исходный MRG-файл предназначен для представления исходного кода, подставленного компилятором. MRG-файл может компилироваться или запускаться отличным от оригинального исходного файла образом.

Макросы не будут развернуты в MRG-файле.

Если программа включает файл заголовка, который использует подставляемый код, **/Fx** создает файл с расширением .mrg.h для этого заголовка. **/Fx** не выполняет объединение для включаемых файлов, которые не используют подставляемый код.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Откройте страницу свойств **Выходные файлы** .

1. Измените свойство **Раскрывать атрибуты исходного кода** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExpandAttributedSource%2A>.

## <a name="see-also"></a>См. также

[Параметры выходного файла (/F)](output-file-f-options.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
