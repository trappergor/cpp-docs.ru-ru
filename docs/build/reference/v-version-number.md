---
title: -V (номер версии) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /v
dev_langs:
- C++
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c4ad42a72a874537a6307cfc547852f812f4aaaa
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707971"
---
# <a name="v-version-number"></a>/V (номер версии)

Не рекомендуется. Внедряет строку текста в OBJ-файле.

## <a name="syntax"></a>Синтаксис

```
/Vstring
```

## <a name="arguments"></a>Аргументы

*string*<br/>
Строка, указывающая номер версии или уведомление об авторских правах для внедрения в OBJ-файле.

## <a name="remarks"></a>Примечания

Метка stringcan OBJ-файл с номером версии или уведомление об авторских правах. Любые пробелы или символы табуляции должны заключаться в двойные кавычки (""), если они являются частью строки. Обратная косая черта (\\) должен предшествовать все двойные кавычки, если они являются частью строки. Пробел между **/V** и `string` является необязательным.

Можно также использовать [комментарий (C/C++)](../../preprocessor/comment-c-cpp.md) с аргументом типа комментария компилятора для размещения имя и номер версии компилятора в OBJ-файле.

**/V** параметр является устаревшим, начиная с Visual Studio 2005; **/V** был главным образом используется для поддержки сборку драйверов виртуальных устройств (VxD) и создание файлов VxD больше не поддерживается с помощью набора инструментов Visual C++. Список параметров компилятора, см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)