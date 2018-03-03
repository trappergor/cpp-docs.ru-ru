---
title: "-U, -u (Отмена определения символа) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLWCECompilerTool.UndefinePreprocessorDefinitions
- VC.Project.VCCLCompilerTool.UndefineAllPreprocessorDefinitions
- /u
- VC.Project.VCCLWCECompilerTool.UndefineAllPreprocessorDefinitions
dev_langs:
- C++
helpviewer_keywords:
- -U compiler option [C++]
- Undefine Symbols compiler option
- /U compiler option [C++]
- U compiler option [C++]
ms.assetid: 7bc0474f-6d1f-419b-807d-0d8816763b2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 18fdaf0c2cb980f1ed19fdfc0577769a9985cf85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="u-u-undefine-symbols"></a>Параметры /U и /u (отмена определения символа)
**/U** параметр компилятора отменяет определение заданного символа препроцессора. **/U** параметр компилятора определений символов характерные для Майкрософт, которые компилятор определяет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/U[ ]symbol  
/u  
```  
  
## <a name="arguments"></a>Аргументы  
 `symbol`  
 Символ препроцессора, чтобы отменить определение.  
  
## <a name="remarks"></a>Примечания  
 Ни **/U** или **/u** может отменить определение символа, созданного с помощью **#define** директивы.  
  
 **/U** может отменить определение символа, который ранее был определен с помощью **/D** параметр.  
  
 По умолчанию компилятор определяет следующие символы для систем Microsoft.  
  
|Символ|Функция|  
|------------|--------------|  
|_CHAR_UNSIGNED|Тип char по умолчанию не подписан. Определяется, если [/j.](../../build/reference/j-default-char-type-is-unsigned.md) параметра.|  
|_CPPRTTI|Определяется для кода, компилируемого с [/GR](../../build/reference/gr-enable-run-time-type-information.md) параметр.|  
|_CPPUNWIND|Определяется для кода, компилируемого с [/EHsc](../../build/reference/eh-exception-handling-model.md) параметр.|  
|_DLL|Определяется, если [/MD](../../build/reference/md-mt-ld-use-run-time-library.md) параметра.|  
|_M_IX86|По умолчанию, определенные в 600 x86 целевых объектов.|  
|_MSC_VER|Для получения дополнительной информации см. [Predefined Macros](../../preprocessor/predefined-macros.md).|  
|_WIN32|Определяется для приложений WIN32. Определяется всегда.|  
|_MT|Определяется, если [/MD или/MT](../../build/reference/md-mt-ld-use-run-time-library.md) параметра.|  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **отменить определения препроцессора** или **отменить все определения препроцессора** свойства.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. описания свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefineAllPreprocessorDefinitions%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UndefinePreprocessorDefinitions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/J (по умолчанию является тип unsigned char)](../../build/reference/j-default-char-type-is-unsigned.md)   
 [/GR (предоставление информации о типах времени выполнения)](../../build/reference/gr-enable-run-time-type-information.md)   
 [Параметр /EH (модель обработки исключений)](../../build/reference/eh-exception-handling-model.md)   
 [/ MD, / MT, /LD (использование библиотеки времени выполнения)](../../build/reference/md-mt-ld-use-run-time-library.md)