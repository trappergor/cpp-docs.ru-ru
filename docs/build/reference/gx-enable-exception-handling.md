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
ms.openlocfilehash: 43be8f6d0f080f0d85568ce5b089751fc68f0e8e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292007"
---
# <a name="gx-enable-exception-handling"></a>/GX (включить обработку исключений)

Не рекомендуется. Включает синхронную обработку исключений с помощью предполагается, что функции, объявленные с помощью `extern "C"` не создают исключений.

## <a name="syntax"></a>Синтаксис

```
/GX
```

## <a name="remarks"></a>Примечания

**/GX** является устаревшим. Использовать эквивалентное [/EHsc](eh-exception-handling-model.md) вместо него. Список параметров компилятора, см. в разделе **нерекомендуемые и удаленные параметры компилятора** статьи [параметры компилятора, упорядоченные по категориям](compiler-options-listed-by-category.md).

По умолчанию **/EHsc**, эквивалентные значению **/GX**, при компиляции с помощью среды разработки Visual Studio. При использовании программы командной строки, указывается без обработки исключений. Это является эквивалентом **/GX-**.

Дополнительные сведения см. в разделе [обработка исключений C++](../../cpp/cpp-exception-handling.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. В области навигации выберите **свойства конфигурации**, **C/C++**, **командной строки**.

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[/EH (модель обработки исключений)](eh-exception-handling-model.md)
