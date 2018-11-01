---
title: /Zm (задание ограничения выделения памяти для предкомпилированного заголовка)
ms.date: 11/04/2016
f1_keywords:
- /zm
helpviewer_keywords:
- PCH files, memory allocation limit
- Zm compiler option [C++]
- /Zm compiler option [C++]
- precompiled header files, memory allocation limit
- Specify Precompiled Header Memory Allocation Limit compiler option
- cl.exe compiler, memory allocation limit
- .pch files, memory allocation limit
- memory allocation, Memory Allocation Limit compiler option
- -Zm compiler option [C++]
ms.assetid: 94c77d5e-6672-46a7-92e0-3f69e277727d
ms.openlocfilehash: ee42fc2d1065a755fa816a99563ccc9f0108e847
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50634802"
---
# <a name="zm-specify-precompiled-header-memory-allocation-limit"></a>/Zm (задание ограничения выделения памяти для предкомпилированного заголовка)

Этот параметр задает объем памяти, который выделяется компилятором для конструирования предкомпилированных заголовков.

## <a name="syntax"></a>Синтаксис

```
/Zmfactor
```

## <a name="arguments"></a>Аргументы

*Коэффициент*<br/>
Коэффициент масштабирования, определяющий объем памяти, используемый компилятором для конструирования предкомпилированных заголовков.

*Идентификации* аргумент представляет собой долю размер компилятора рабочего буфера, заданного по умолчанию. Значение по умолчанию *идентификации* — 100 (процентов), но можно указать большее или меньшее.

## <a name="remarks"></a>Примечания

В предыдущих версиях Visual C++ компилятор использовал несколько отдельных куч, размер каждой из которых был ограничен. В настоящее время компилятор динамически увеличивает кучи по мере необходимости вплоть до общего предела размера куч; буфер фиксированного размера требуется только для конструирования предкомпилированных заголовков. Следовательно **/Zm** параметр компилятора требуется редко.

Если компилятор не хватает пространства кучи и выдает [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md) сообщение об ошибке при использовании **/Zm** параметр компилятора, вы зарезервировали слишком много памяти. Рассмотрите возможность удаления **/Zm** параметр. Если компилятор выдает [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md) сообщение об ошибке, сопутствующего [C3859](../../error-messages/compiler-errors-2/compiler-error-c3859.md) сообщении указывается *идентификации* аргумент для использования при повторной компиляции с помощью **/Zm** параметр компилятора.

В следующей таблице показано как *идентификации* аргумент влияет на предел выделения памяти, если предполагается, что размер буфера предкомпилированных заголовков по умолчанию составляет 75 МБ.

|Значение атрибута *идентификации*|Предел выделения памяти|
|-----------------------|-----------------------------|
|10|7.5 МБ|
|100|75 МБ|
|200|150 МБ|
|1000|750 МБ|
|2000|1500 МБ|

## <a name="other-ways-to-set-the-memory-allocation-limit"></a>Другие способы установки предела выделения памяти

#### <a name="to-set-the-zm-compiler-option-in-the-visual-studio-development-environment"></a>Установка параметра компилятора /Zm в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. В области навигации выберите **свойства конфигурации**, **C/C++**, **командной строки**.

1. Введите **/Zm** параметр компилятора в **Дополнительные параметры** поле.

#### <a name="to-set-the-zm-compiler-option-programmatically"></a>Установка параметра компилятора /Zm программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)