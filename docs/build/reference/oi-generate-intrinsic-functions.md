---
title: -Oi (Создание встроенных функций) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableIntrinsicFunctions
- /oi
- VC.Project.VCCLWCECompilerTool.EnableIntrinsicFunctions
dev_langs:
- C++
helpviewer_keywords:
- Oi compiler option [C++]
- intrinsic functions, generate
- /Oi compiler option [C++]
- -Oi compiler option [C++]
- generate intrinsic functions compiler option [C++]
ms.assetid: fa4a3bf6-0ed8-481b-91c0-add7636132b4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 527f326d629bc8d41efcd73a938994570bed4d2e
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725924"
---
# <a name="oi-generate-intrinsic-functions"></a>/Oi (создание встроенных функций)

Заменяет вызов некоторых функций с формами внутренние или в противном случае специальные функции, помочь вашему приложению работать быстрее.

## <a name="syntax"></a>Синтаксис

```
/Oi[-]
```

## <a name="remarks"></a>Примечания

Программы, использующие встроенные функции выполняются быстрее, поскольку они не имеют рабочей нагрузке вызовов функций, но может быть больше из-за создания дополнительного кода.

См. в разделе [внутренние](../../preprocessor/intrinsic.md) Дополнительные сведения о функциях, имеющих встроенные формы.

**/Oi** — только запрос компилятору заменить вызовы некоторых функций встроенные функции; компилятор может вызвать функцию (и не заменять вызов функции с встроенная) Если это приведет к повышению производительности.

**x86 конкретных**

Встроенные функции с плавающей запятой не выполнять каких-либо специальных проверок на входных значениях так работать в ограниченные диапазоны входных данных и обработки различных исключений и граничных условий, чем библиотечные процедуры с тем же именем. С помощью встроенных форм подразумевает обработки исключений IEEE и потерь из `_matherr` и `errno` функции; второе означает потерю ANSI-совместимости. Тем не менее встроенные формы может значительно ускорить интенсивные с плавающей точкой программы и для многих программ вопросах соответствия, запятой.

Можно использовать [Za](../../build/reference/za-ze-disable-language-extensions.md) параметр компилятора, чтобы отключить создание true встроенных параметров с плавающей запятой. В этом случае функции будут создаваться как библиотечные процедуры, которые передают аргументы напрямую в микросхему операций с плавающей запятой, а не в стек программы.

**КОНЕЦ x86 конкретных**

Можно также использовать [внутренние](../../preprocessor/intrinsic.md) создание встроенных функций или [функции (C/C++)](../../preprocessor/function-c-cpp.md) чтобы явно принудительно задать вызов функции.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **оптимизации** страницу свойств.

1. Изменить **включить встроенные функции** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableIntrinsicFunctions%2A>.

## <a name="see-also"></a>См. также

[Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)
[параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)<br/>
[Встроенные инструкции компилятора](../../intrinsics/compiler-intrinsics.md)