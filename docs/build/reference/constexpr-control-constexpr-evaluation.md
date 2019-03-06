---
title: /constexpr (управлять вычислением constexpr)
ms.date: 08/15/2017
f1_keywords:
- /constexpr
- -constexpr
helpviewer_keywords:
- /constexpr control constexpr evaluation [C++]
- -constexpr control constexpr evaluation [C++]
- constexpr control constexpr evaluation [C++]
ms.assetid: 76d56784-f5ad-401d-841d-09d1059e8b8c
ms.openlocfilehash: 49a9566ec0725b63330af3a41afb871c3be3cc27
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57414659"
---
# <a name="constexpr-control-constexpr-evaluation"></a>/constexpr (управлять вычислением constexpr)

Используйте **/constexpr** параметры компилятора, параметры управления **constexpr** оценки во время компиляции.

## <a name="syntax"></a>Синтаксис

> **/constexpr:Depth**<em>N</em>
>  **/constexpr:backtrace**<em>N</em>
>  **/constexpr:steps** <em>N</em>

## <a name="arguments"></a>Аргументы

**Глубина**<em>N</em> ограничение глубины рекурсивной **constexpr** вызов к функции *N* уровней. Значение по умолчанию — 512.

**backtrace**<em>N</em> Показать до *N* **constexpr** оценок в системе диагностики. Значение по умолчанию — 10.

**действия**<em>N</em> Terminate **constexpr** оценки после *N* действия. Значение по умолчанию равно 100 000.

## <a name="remarks"></a>Примечания

**/Constexpr** компилятора параметры управляют вычисление во время компиляции **constexpr** выражения. Чтобы запретить компилятору выполнять тратит слишком много времени на осуществляется по оценке продуктов, уровней рекурсии и глубина backtrace **constexpr** оценки. Дополнительные сведения о **constexpr** элемента языка, см. в разделе [constexpr (C++)](../../cpp/constexpr-cpp.md).

**/Constexpr** параметры будут доступны, начиная с Visual Studio 2015.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте свой проект **страницы свойств** диалоговое окно.

2. В разделе **свойства конфигурации**, разверните **C/C++** папку и выберите **командной строки** страницу свойств.

3. Введите любой **/constexpr** параметров компилятора в **Дополнительные параметры** поле. Выберите **ОК** или **применить** для сохранения изменений.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)
