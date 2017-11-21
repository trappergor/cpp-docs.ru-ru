---
title: "-FI (имя принудительно включаемого файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCNMakeTool.ForcedIncludes
- VC.Project.VCCLCompilerTool.ForcedIncludeFiles
- VC.Project.VCCLWCECompilerTool.ForcedIncludeFiles
- /fi
dev_langs: C++
helpviewer_keywords:
- FI compiler option [C++]
- -FI compiler option [C++]
- /FI compiler option [C++]
- preprocess header file compiler option [C++]
ms.assetid: 07e79577-8152-4df9-a64c-aae08c603397
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1309f822ae8f7ab7e4735525439f9d3529754001
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fi-name-forced-include-file"></a>/FI (имя принудительно включаемого файла)
Вызывает препроцессор обработать указанный файл заголовка.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/FI[ ]pathname  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр действует так же, как при указании файла с использованием двойных кавычек в `#include` директив в первой строке каждого исходного файла, указанного в командной строке, в переменной среды компилятора CL или в командном файле. При использовании нескольких **/FI** элементы, файлы будут включены в том порядке, они обрабатываются CL.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **принудительно включать** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ForcedIncludeFiles%2A>.  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Указание пути](../../build/reference/specifying-the-pathname.md)