---
title: /Ge (включить проверку стека)
ms.date: 11/04/2016
f1_keywords:
- /ge
helpviewer_keywords:
- -Ge compiler option [C++]
- enable stack probes
- /Ge compiler option [C++]
- stack, stack probes
- stack probes
- stack checking calls
- Ge compiler option [C++]
ms.assetid: 4b54deae-4e3c-4bfa-95f3-ba23590f7258
ms.openlocfilehash: a785ec041370e0bcbb2ce8b698bfba89235a0a0c
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57812139"
---
# <a name="ge-enable-stack-probes"></a>/Ge (включить проверку стека)

Включает стековые зонды для каждого вызова функции, в которой требуется хранилище для локальных переменных.

## <a name="syntax"></a>Синтаксис

```
/Ge
```

## <a name="remarks"></a>Примечания

Этот механизм полезен в том случае, если перезаписи функций проверки стека. Рекомендуется использовать [/Gh (Включение _penter функции-ловушки)](gh-enable-penter-hook-function.md) вместо перезаписи проверки стека.

[/ GS (элемент управления стека проверки вызывает)](gs-control-stack-checking-calls.md) имеет тот же эффект.

**/GE** является устаревшим, начиная с Visual Studio 2005, компилятор автоматически создает проверка стека. Список параметров компилятора, см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](compiler-options-listed-by-category.md).

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
