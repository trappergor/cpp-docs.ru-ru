---
title: -GH (включить код обработчик _pexit) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _pexit
dev_langs:
- C++
helpviewer_keywords:
- /Gh compiler option [C++]
- Gh compiler option [C++]
- _pexit function
- -Gh compiler option [C++]
ms.assetid: 93181453-2676-42e5-bf63-3b19e07299b6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 489ff00571c79d89c9e807f0d8796989e7a0f84f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714992"
---
# <a name="gh-enable-pexit-hook-function"></a>/GH (включить функцию-обработчик _pexit)

Вызовы `_pexit` функции в конце каждого метода или функции.

## <a name="syntax"></a>Синтаксис

```
/GH
```

## <a name="remarks"></a>Примечания

`_pexit` Функция не является частью любой библиотеки, и это необходимо указать определение `_pexit`.

Если вы не планируете явным образом вызвать `_pexit`, не нужно предоставлять прототип. Функция должна выглядеть так, как если бы она имела следующий прототип, и он должен отправка содержимого регистров на запись и отображение без изменений содержимого при выходе:

```
void __declspec(naked) _cdecl _pexit( void );
```

`_pexit` аналогичен `_penter`; см. в разделе [/Gh (Включение _penter функции-ловушки)](../../build/reference/gh-enable-penter-hook-function.md) пример создания `_pexit` функции.

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