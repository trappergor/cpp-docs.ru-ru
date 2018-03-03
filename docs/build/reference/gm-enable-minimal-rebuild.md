---
title: "-Gm (включение минимального перепостроения) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bc9ff065de2b83d50b6fa905fcc6d1123dbe829
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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