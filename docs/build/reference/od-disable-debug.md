---
title: -Od (Выключение (отладчика)) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /od
dev_langs:
- C++
helpviewer_keywords:
- no optimizations
- fast compiling
- /Od compiler option [C++]
- disable optimizations
- Od compiler option [C++]
- -Od compiler option [C++]
- disable (debug) compiler option [C++]
ms.assetid: b1ac31b7-e086-4eeb-be5e-488f7513f5f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47e287a9991f8192f16ec2f93e4068dc797ff72a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="od-disable-debug"></a>/Od (Выключение (отладчика))
Отключает все оптимизации в программе и ускоряет компиляцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Od  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр используется по умолчанию. Поскольку **/Od** отключает перемещение кода он упрощает процесс отладки. Дополнительные сведения о параметрах компилятора для отладки см. в разделе [/Z7, / Zi, /ZI (формат отладочной информации)](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **оптимизации** страницу свойств.  
  
4.  Изменить **оптимизации** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры /O (оптимизация кода)](../../build/reference/o-options-optimize-code.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/Z7, /Zi, /ZI (формат отладочной информации)](../../build/reference/z7-zi-zi-debug-information-format.md)