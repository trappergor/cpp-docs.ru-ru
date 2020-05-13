---
title: /GH (включить функцию-обработчик _pexit)
ms.date: 11/04/2016
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: 5382ba90f490aaa12e9e55767fdf15170a69ced5
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81749229"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH (включить функцию-обработчик _pexit)

Вызывает `_pexit` функцию в конце каждого метода или функции.

## <a name="syntax"></a>Синтаксис

```
/GH
```

## <a name="remarks"></a>Remarks

Функция `_pexit` не является частью какой-либо библиотеки, и `_pexit`это до вас, чтобы предоставить определение для .

Если вы не планируете явно звонить, `_pexit`вам не нужно предоставлять прототип. Функция должна отображаться так, как если бы у нее был следующий прототип, и она должна толкать содержимое всех регистров на входе и высвобожда неизмененное содержимое на выходе:

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit`похож на `_penter`; [например, например, написать функцию /Gh (Функция _penter функция крюка)](gh-enable-penter-hook-function.md) можно ознакомиться с изображением. `_pexit`

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Выберите страницу свойств **Командная строка** .

1. Введите параметр компилятора в поле **Дополнительные параметры** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[MSVC Компилятор Командно-линейный синтаксис](compiler-command-line-syntax.md)
