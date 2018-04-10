---
title: -arch (ARM) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
ms.assetid: 4f1406ff-f174-487c-a126-8ab06cf447c1
caps.latest.revision: 5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 468401bcee2d627149175d022c420b8bb905c4ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="arch-arm"></a>/arch (ARM)
Указывает архитектуру для создания кода на платформе ARM. См. также [/arch (x86)](../../build/reference/arch-x86.md) и [/arch (x64)](../../build/reference/arch-x64.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/arch:[ARMv7VE|VFPv4]  
```  
  
## <a name="arguments"></a>Аргументы  
 **/arch:ARMv7VE**  
 Включает использование инструкций расширения виртуализации ARMv7VE.  
  
 **/arch:VFPv4**  
 Включает использование инструкций ARM VFPv4. Если этот параметр не указан, по умолчанию используется VFPv3.  
  
## <a name="remarks"></a>Примечания  
 `_M_ARM_FP` Макрос (только для ARM) указывает, что, если таковые имеются, **/arch** использовался параметр компилятора. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md).  
  
 При использовании [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) для компиляции, **/arch** не влияет на создание кода для управляемых функций. **/ arch** только влияет на создание кода для собственных функций.  
  
### <a name="to-set-the-archarmv7ve-or-archvfpv4-compiler-option-in-visual-studio"></a>Чтобы задать параметр компилятора /arch:ARMv7VE или /arch:VFPv4 в Visual Studio  
  
1.  Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **C/C++** папки.  
  
3.  Выберите **командной строки** страницу свойств.  
  
4.  В **Дополнительные параметры** добавьте `/arch:ARMv7VE` или `/arch:VFPv4`.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## <a name="see-also"></a>См. также  
 [/ arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)