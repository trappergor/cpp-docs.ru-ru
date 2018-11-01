---
title: /Gm (включение минимального перепостроения)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
ms.openlocfilehash: 2a5bc4008ab9376367b3a32040c2a4a70147187f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570408"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (включение минимального перепостроения)

Включает минимальное перестроение, которое определяет, нужно ли заново компилировать исходные файлы C++, содержащие измененные определения классов C++ (хранимые в файлах заголовка [H]).

## <a name="syntax"></a>Синтаксис

```
/Gm
```

## <a name="remarks"></a>Примечания

Компилятор сохраняет информацию о зависимостях между исходными файлами и определениями классов в IDB-файле проекта при первом компилировании. (Сведения о зависимости указывают, какой файл источника зависит от какого определения класса и в каком h-файле определения находится в.) Последующие компиляции используют сведения, хранящиеся в файле IDB для определения, является ли исходный файл должен быть скомпилирован, даже если он содержит измененный h-файл.

> [!NOTE]
>  Минимальное перестроение полагается на определения классов, не изменяющиеся в файлах заголовка. Определения класса должны быть глобальными для всего проекта (должно быть только одно определение данного класса), поскольку сведения о зависимостях в файле IDB создаются для всего проекта в целом. Если в вашем проекте более одного определения для класса, отключите режим минимального перестроения.

Так как Инкрементный компоновщик не поддерживает метаданные Windows, входящие в OBJ-файлов с помощью [/ZW (компиляция среды выполнения Windows)](../../build/reference/zw-windows-runtime-compilation.md) параметр, **/Gm** не совместим с  **/ Zw**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **создание кода** страницу свойств.

1. Изменить **включение минимального перепостроения** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)