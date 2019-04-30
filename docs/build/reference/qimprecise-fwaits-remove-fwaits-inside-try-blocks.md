---
title: /Qimprecise_fwaits (Удалить ожидания в блоке try)
ms.date: 11/04/2016
f1_keywords:
- /Qimprecise_fwaits
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
ms.openlocfilehash: 40683382686ea64a80563f3f29b7d3523f4144a8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319594"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Удалить ожидания в блоке try)

Удаляет `fwait` внутренние для команды `try` блокировать при использовании [/fp: except](fp-specify-floating-point-behavior.md) параметр компилятора.

## <a name="syntax"></a>Синтаксис

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Примечания

Этот параметр не действует при **/fp: except** не указан. При указании **/fp: except** параметр, компилятор вставит `fwait` команду рядом с каждой строкой кода в `try` блока. Таким образом компилятор может определить конкретной строки кода, которая вызвала исключение. **/ Qimprecise_fwaits** удаляет внутренней `fwait` инструкции, оставляя только ожиданий вокруг `try` блока. Это повышает производительность, но компилятор только будут иметь возможность выбрать, какой `try` блок вызывает исключение, а не строку.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /Q (низкоуровневые операции)](q-options-low-level-operations.md)<br/>
[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
