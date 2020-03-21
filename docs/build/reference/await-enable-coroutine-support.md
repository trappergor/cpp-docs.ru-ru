---
title: /await (включение поддержки соподпрограмм)
ms.date: 08/15/2017
f1_keywords:
- /await
- -await
helpviewer_keywords:
- /await enable coroutine support [C++]
- -await enable coroutine support [C++]
- await enable coroutine support [C++]
ms.assetid: 302c8e69-09b6-4c58-bcdd-0a6a8713a8df
ms.openlocfilehash: eeab3f4a1afc73e341f04222a55c8ce429490742
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80078445"
---
# <a name="await-enable-coroutine-support"></a>/await (включение поддержки соподпрограмм)

Используйте параметр компилятора **/await** , чтобы включить поддержку компилятора для соподпрограмм.

## <a name="syntax"></a>Синтаксис

> /await

## <a name="remarks"></a>Примечания

Параметр компилятора **/await** обеспечивает поддержку компилятора для C++ соподпрограмм и ключевых слов **co_await**, **co_yield**и **co_return**. По умолчанию она отключена. Сведения о поддержке соподпрограмм в Visual Studio см. в [блоге группы разработчиков Visual Studio](https://blogs.msdn.microsoft.com/vcblog/category/coroutine/). Дополнительные сведения о стандартном предложении «коподпрограмми» см. в разделе [N4628 Working C++ Черновое техническое описание расширений для соподпрограмм](https://wg21.link/n4628).

Параметр **/await** доступен начиная с Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **страницы свойств** проекта.

1. В разделе **Свойства конфигурации**разверните папку **C/C++**  и выберите страницу свойств **Командная строка** .

1. В поле **Дополнительные параметры** введите параметр компилятора **/await** . Нажмите кнопку **ОК** или **Применить** , чтобы сохранить изменения.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также:

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
