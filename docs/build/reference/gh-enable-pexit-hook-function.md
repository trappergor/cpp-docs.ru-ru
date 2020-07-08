---
title: /GH (включение функции-обработчика _pexit)
description: Описывает параметр компилятора/GH для задания локальной функции-обработчика _pexit.
ms.date: 07/06/2020
f1_keywords:
- _pexit
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
ms.openlocfilehash: b8fc355503055af8b928874ced39cb8224901d3e
ms.sourcegitcommit: 85d96eeb1ce41d9e1dea947f65ded672e146238b
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2020
ms.locfileid: "86058611"
---
# <a name="gh-enable-_pexit-hook-function"></a>/GH (включение функции-обработчика _pexit)

Вызывает `_pexit` функцию в конце каждого метода или функции.

## <a name="syntax"></a>Синтаксис

> **`/GH`**

## <a name="remarks"></a>Примечания

`_pexit`Функция не является частью какой бы то ни было библиотеки. Вы можете предоставить определение для `_pexit` .

Если вы не планируете явно вызывать `_pexit` , вам не нужно предоставлять прототип. Функция должна отправить содержимое всех регистров на вход и открыть неизмененное содержимое при выходе. Оно должно выглядеть так, как если бы оно имело следующий прототип:

```cpp
void __declspec(naked) __cdecl _pexit( void );
```

Это объявление недоступно для 64-разрядных проектов.

`_pexit`функция аналогична `_penter` функции; см. раздел [ `/Gh` (Enable _Penter функцию-ловушке)](gh-enable-penter-hook-function.md) в качестве примера того, как написать `_penter` функцию.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте страницу свойств **конфигурации**  >  **C/C++**  >  **Командная строка** .

1. В поле **Дополнительные параметры** введите параметр компилятора.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)<br/>
[`/Gh`(Включить функцию-обработчик _penter)](gh-enable-penter-hook-function.md)
