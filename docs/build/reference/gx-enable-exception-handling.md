---
title: /GX (включить обработку исключений)
ms.date: 11/19/2019
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
ms.openlocfilehash: 171ff0d0dfb1dec41bae5f6be63c941802c402a4
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245090"
---
# <a name="gx-enable-exception-handling"></a>/GX (включить обработку исключений)

Устаревшее. Включает синхронную обработку исключений с помощью предположения, что функции, объявленные с помощью `extern "C"` никогда не создают исключение.

## <a name="syntax"></a>Синтаксис

```
/GX
```

## <a name="remarks"></a>Примечания

Функция **/GX** устарела. Вместо этого используйте эквивалентный параметр [/EHsc](eh-exception-handling-model.md) . Список устаревших параметров компилятора см. в разделе " **устаревшие и удаленные параметры компилятора** " раздела [параметры компилятора, упорядоченные по категориям](compiler-options-listed-by-category.md).

По умолчанию параметр **/EHsc**, эквивалентный параметром **/GX**, действует при компиляции с помощью среды разработки Visual Studio. При использовании программ командной строки обработка исключений не указывается. Это эквивалентно **/ГКС-** .

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. В области навигации выберите **Свойства конфигурации**, **C/C++** , **Командная строка**.

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также:

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/EH (модель обработки исключений)](eh-exception-handling-model.md)
