---
title: /GX (включить обработку исключений)
ms.date: 11/04/2016
f1_keywords:
- /gx
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
ms.openlocfilehash: 4ac2b86c19845a092c743c484ad48d0cd0b6fb35
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57416037"
---
# <a name="gx-enable-exception-handling"></a>/GX (включить обработку исключений)

Не рекомендуется. Включает синхронную обработку исключений с помощью предполагается, что функции, объявленные с помощью `extern "C"` не создают исключений.

## <a name="syntax"></a>Синтаксис

```
/GX
```

## <a name="remarks"></a>Примечания

**/GX** является устаревшим. Использовать эквивалентное [/EHsc](../../build/reference/eh-exception-handling-model.md) вместо него. Список параметров компилятора, см. в разделе **нерекомендуемые и удаленные параметры компилятора** статьи [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).

По умолчанию **/EHsc**, эквивалентные значению **/GX**, при компиляции с помощью среды разработки Visual Studio. При использовании программы командной строки, указывается без обработки исключений. Это является эквивалентом **/GX-**.

Дополнительные сведения см. в разделе [обработка исключений C++](../../cpp/cpp-exception-handling.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. В области навигации выберите **свойства конфигурации**, **C/C++**, **командной строки**.

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[/EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md)
