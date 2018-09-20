---
title: -Qimprecise_fwaits (удаление ожиданий в блоке Try) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Qimprecise_fwaits
dev_langs:
- C++
helpviewer_keywords:
- -Qimprecise_fwaits compiler option (C++)
- /Qimprecise_fwaits compiler option (C++)
ms.assetid: b1501f21-7e08-4fea-95e8-176ec03a635b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cad23ebdd2289791b50b0e956368b934fe0f1087
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385200"
---
# <a name="qimprecisefwaits-remove-fwaits-inside-try-blocks"></a>/Qimprecise_fwaits (Удалить ожидания в блоке try)

Удаляет `fwait` внутренние для команды `try` блокировать при использовании [/fp: except](../../build/reference/fp-specify-floating-point-behavior.md) параметр компилятора.

## <a name="syntax"></a>Синтаксис

```
/Qimprecise_fwaits
```

## <a name="remarks"></a>Примечания

Этот параметр не действует при **/fp: except** не указан. При указании **/fp: except** параметр, компилятор вставит `fwait` команду рядом с каждой строкой кода в `try` блока. Таким образом компилятор может определить конкретной строки кода, которая вызвала исключение. **/ Qimprecise_fwaits** удаляет внутренней `fwait` инструкции, оставляя только ожиданий вокруг `try` блока. Это повышает производительность, но компилятор только будут иметь возможность выбрать, какой `try` блок вызывает исключение, а не строку.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры /Q (низкоуровневые операции)](../../build/reference/q-options-low-level-operations.md)<br/>
[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)