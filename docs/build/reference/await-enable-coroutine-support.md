---
title: -await (Включение поддержки сопрограмм) | Документация Майкрософт
ms.custom: ''
ms.date: 08/15/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /await
- -await
dev_langs:
- C++
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5da401f940a39c135ba0b64571b6330a42fed796
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725521"
---
# <a name="await-enable-coroutine-support"></a>/ await (Включение поддержки сопрограмм)

Используйте **/ await** параметр компилятора, чтобы включить поддержку компилятора для сопрограммы.

## <a name="syntax"></a>Синтаксис

> / await

## <a name="remarks"></a>Примечания

**/ Await** параметр компилятора включает поддержку компилятора для соподпрограмм C++ и ключевые слова **co_await**, **co_yield**, и **co_return**. По умолчанию она отключена. Сведения о поддержке сопрограммы в Visual Studio, см. в разделе [блоге команды разработчиков Visual Studio](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Дополнительные сведения о предложении standard сопрограммы см. в разделе [N4628 рабочего проекта, технические спецификации для расширения C++ для сопрограммы](http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2016/n4628.pdf).

**/ Await** параметр доступно в Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте свой проект **страницы свойств** диалоговое окно.

2. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **командной строки** страницу свойств.

3. Введите **/ await** параметр компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)