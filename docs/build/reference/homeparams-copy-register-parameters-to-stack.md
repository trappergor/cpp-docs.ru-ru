---
title: /homeparams (копирование параметров регистров в стек)
ms.date: 11/04/2016
f1_keywords:
- /homeparams
helpviewer_keywords:
- /homeparams compiler option [C++]
- -homeparams compiler option [C++]
ms.assetid: 51067de4-24f7-436b-b8d9-bc867a7d53aa
ms.openlocfilehash: 952a38d2ab1268ee3dc1fda0899a3ba047281b44
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518460"
---
# <a name="homeparams-copy-register-parameters-to-stack"></a>/homeparams (копирование параметров регистров в стек)

Принудительная запись параметров, переданных в регистрах, в соответствующие места в стеке при вхождении в функцию.

## <a name="syntax"></a>Синтаксис

```
/homeparams
```

## <a name="remarks"></a>Примечания

Этот параметр компилятора предназначен только для x64 компиляторы (собственные и кросс-компиляция).

При передаче параметров в x x64 компиляции, соглашения о вызовах требуется пространство стека для параметров, даже для параметров, передаваемых в регистрах. Дополнительные сведения см. в разделе [передача параметров](../../build/parameter-passing.md). Тем не менее по умолчанию в сборке выпуска параметров регистра не записывается в стек, в пространство, который был задан для параметров. Это затрудняет для отладки сборки оптимизированного (выпуска) программы.

Для сборки выпуска, используйте **/homeparams** чтобы убедиться, что можно выполнять отладку приложения. **/ homeparams** подразумевает, что недостаток производительности, поскольку он требует цикла для загрузки параметров регистров в стек.

В отладочном построении стек всегда заполняется параметров, передаваемых в регистрах.

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