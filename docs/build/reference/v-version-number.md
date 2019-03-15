---
title: /V (номер версии)
ms.date: 11/04/2016
f1_keywords:
- /v
helpviewer_keywords:
- embedding version strings
- /V compiler option [C++]
- version numbers, specifying for .obj
- V compiler option [C++]
- -V compiler option [C++]
ms.assetid: 3e93fb7a-5dfd-49a6-bd49-3dca8052e0f3
ms.openlocfilehash: 7bebd3ab9677bb340203bbf857e4ee9f287e36e6
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57817612"
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

**/V** параметр является устаревшим, начиная с Visual Studio 2005; **/V** был главным образом используется для поддержки сборку драйверов виртуальных устройств (VxD) и создание файлов VxD больше не поддерживается с помощью набора инструментов Visual C++. Список параметров компилятора, см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](compiler-options-listed-by-category.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
