---
title: -Gm (включение минимального перепостроения) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
dev_langs:
- C++
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e0b83c34b0ff8cacbca9d21a40c6c9572f516d1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (включение минимального перепостроения)
Включает минимальное перестроение, которое определяет, нужно ли заново компилировать исходные файлы C++, содержащие измененные определения классов C++ (хранимые в файлах заголовка [H]).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Gm  
```  
  
## <a name="remarks"></a>Примечания  
 Компилятор сохраняет информацию о зависимостях между исходными файлами и определениями классов в IDB-файле проекта при первом компилировании. (Сведения о зависимости указывают, какой файл источника зависит от какого определения класса, и какие h-файле определения расположен в). Последующие компиляции используют сведения, хранящиеся в IDB-файла для определения, является ли исходный файл должна быть скомпилирована, даже если он содержит измененный h-файл.  
  
> [!NOTE]
>  Минимальное перестроение полагается на определения классов, не изменяющиеся в файлах заголовка. Определения класса должны быть глобальными для всего проекта (должно быть только одно определение данного класса), поскольку сведения о зависимостях в файле IDB создаются для всего проекта в целом. Если в вашем проекте более одного определения для класса, отключите режим минимального перестроения.  
  
 Поскольку Инкрементный компоновщик не поддерживает метаданные Windows, включенные в OBJ-файлов с помощью [/ZW (компиляция среды выполнения Windows)](../../build/reference/zw-windows-runtime-compilation.md) параметр **/Gm** несовместим с  **/ Zw**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **создания кода** страницу свойств.  
  
4.  Изменить **включение минимального перепостроения** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)