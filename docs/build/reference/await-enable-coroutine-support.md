---
title: / await (Включение поддержки сопрограмм)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: c0c8c0183c356900ba8f95d39e427d56eb1ec96b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295010"
---
# <a name="await-enable-coroutine-support"></a>/ await (Включение поддержки сопрограмм)

Используйте **/ await** параметр компилятора, чтобы включить поддержку компилятора для сопрограммы.

## <a name="syntax"></a>Синтаксис

> / await

## <a name="remarks"></a>Примечания

**/ Await** параметр компилятора включает поддержку компилятора для C++ сопрограммы и ключевые слова **co_await**, **co_yield**, и **co_return**. По умолчанию она отключена. Сведения о поддержке сопрограммы в Visual Studio, см. в разделе [блоге команды разработчиков Visual Studio](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Дополнительные сведения о предложении standard сопрограммы см. в разделе [N4628 рабочего проекта, технические спецификации для расширения C++ для сопрограммы](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf).

**/ Await** параметр доступно в Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте свой проект **страницы свойств** диалоговое окно.

1. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **командной строки** страницу свойств.

1. Введите **/ await** параметр компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
