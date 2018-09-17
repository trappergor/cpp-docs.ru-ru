---
title: -GX (Включить обработку исключений) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gx
dev_langs:
- C++
helpviewer_keywords:
- exception handling, enabling
- /GX compiler option [C++]
- -GX compiler option [C++]
- cl.exe compiler, exception handling
- enable exception handling compiler option [C++]
- GX compiler option [C++]
ms.assetid: 933b43ba-de77-4ff8-a48b-7074de90bc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 095db3db73f2be4012efe39f3b8cd8e645ad46c3
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718342"
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