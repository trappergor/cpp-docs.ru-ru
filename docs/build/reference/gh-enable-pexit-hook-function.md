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
ms.openlocfilehash: 077096cc296f2aa2128127493a84a91da9a067c5
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57822175"
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
void __declspec(naked) __cdecl _pexit( void );
```

`_pexit` аналогичен `_penter`; см. в разделе [/Gh (Включение _penter функции-ловушки)](gh-enable-penter-hook-function.md) пример создания `_pexit` функции.

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
