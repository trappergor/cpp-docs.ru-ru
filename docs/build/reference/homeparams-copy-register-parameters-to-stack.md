---
title: /homeparams (копирование параметров регистров в стек)
ms.date: 12/17/2018
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: ffb5ca602feb7a369bb31d0277834786d66ac12a
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627483"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (копирование параметров регистров в стек)

Принудительная параметров, переданных в регистрах, также их расположения в стеке при вхождении входа функции.

## <a name="syntax"></a>Синтаксис

> **/homeparams**

## <a name="remarks"></a>Примечания

Этот параметр доступен только в машинном коде и кросс компиляторов, предназначенных для x64.

X64 соглашение о вызовах требует стекового пространства, выделяемого для всех параметров, даже для параметров, передаваемых в регистрах. Дополнительные сведения см. в разделе [передача параметров](../../build/x64-calling-convention.md#parameter-passing). По умолчанию параметров регистра не копируется в пространство стека, выделенную для них в сборках выпуска. Это затрудняет для отладки оптимизированного версию выпуска программы.

Для сборок выпуска, можно использовать **/homeparams** вариант, чтобы заставить компилятор для копирования Регистрация параметров в стек, чтобы убедиться, что можно выполнять отладку приложения. **/ homeparams** подразумевает, что недостаток производительности, поскольку она требует дополнительного цикла, для загрузки параметров регистров в стек.

В отладочных сборках стек всегда заполняется параметров, передаваемых в регистрах.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте **свойства конфигурации** > **C/C++** > **командной строки** страницу свойств.

1. Введите параметр компилятора в **Дополнительные параметры** поле.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)