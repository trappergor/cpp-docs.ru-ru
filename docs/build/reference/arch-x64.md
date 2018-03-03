---
title: "-arch (x64) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: ecda22bf-5bed-43f4-99fb-88aedd83d9d8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27a453601988c22ed03ae9cb267480d88d6a1cc0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="arch-x64"></a>/arch (x64)
Задает архитектуру для создания кода на платформе x64. См. также [/arch (x86)](../../build/reference/arch-x86.md) и [/arch (ARM)](../../build/reference/arch-arm.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/arch:[AVX|AVX2]  
```  
  
## <a name="arguments"></a>Аргументы  
 **/ arch: AVX**  
 Позволяет использовать инструкции Intel AVX.  
  
 **/ arch: avx2**  
 Позволяет использовать инструкции Intel AVX 2.  
  
## <a name="remarks"></a>Примечания  
 **/ arch** только влияет на создание кода для собственных функций. При использовании [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) для компиляции, **/arch** не влияет на создание кода для управляемых функций.  
  
 `__AVX__` Определен символ препроцессора при **/arch: AVX** указан параметр компилятора. `__AVX2__` Определен символ препроцессора при **/arch: avx2** указан параметр компилятора. Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md). **/Arch: avx2** параметр впервые появился в Visual Studio 2013 с обновлением 2 версии 12.0.34567.1.  
  
### <a name="to-set-the-archavx-or-archavx2-compiler-option-in-visual-studio"></a>Установка параметра компилятора /arch:AVX или /arch:AVX2 в Visual Studio  
  
1.  Откройте **страницы свойств** диалоговое окно для проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Выберите **свойства конфигурации**, **C/C++** папки.  
  
3.  Выберите **создания кода** страницу свойств.  
  
4.  В **включить расширенный набор инструкций** раскрывающегося списка выберите **Advanced Vector Extensions (/ arch: AVX)** или **Advanced Vector Extensions 2 (/ arch: AVX2)**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableEnhancedInstructionSet%2A>.  
  
## <a name="see-also"></a>См. также  
 [/ arch (минимальная архитектура ЦП)](../../build/reference/arch-minimum-cpu-architecture.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)