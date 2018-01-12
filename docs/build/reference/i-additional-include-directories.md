---
title: "-I (Дополнительные каталоги включения) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.AdditionalIncludeDirectories
- VC.Project.VCCLCompilerTool.AdditionalIncludeDirectories
- /I
- VC.Project.VCNMakeTool.IncludeSearchPath
dev_langs: C++
helpviewer_keywords:
- /I compiler option [C++]
- Additional Include Directories compiler option
- I compiler option [C++]
- -I compiler option [C++]
- set include directories
- include directories, compiler option [C++]
ms.assetid: 3e9add2a-5ed8-4d15-ad79-5b411e313a49
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bfbf962a92af22d3e724c592fec6cf812b610dc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="i-additional-include-directories"></a>/I (дополнительные каталоги включения)
Добавляет каталог в список каталогов для поиска включаемых файлов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/I[ ]directory  
```  
  
## <a name="arguments"></a>Аргументы  
 `directory`  
 Каталог для добавления в список каталогов для поиска включаемых файлов.  
  
## <a name="remarks"></a>Примечания  
 Чтобы добавить несколько каталогов, используйте этот параметр более одного раза. Поиск каталогов выполняется только в том случае, пока найден указанного включаемого файла.  
  
 Этот параметр можно использовать с игнорировать стандартные пути включения ([/X (игнорировать стандартные пути включения)](../../build/reference/x-ignore-standard-include-paths.md)) параметра.  
  
 Компилятор выполняет поиск каталогов в следующем порядке:  
  
1.  Каталоги, содержащие исходный файл.  
  
2.  Каталоги, заданные с помощью **/i** параметр, в том порядке, в котором их находит CL.  
  
3.  Каталоги, заданные в **INCLUDE** переменной среды.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **Общие** страницу свойств.  
  
4.  Изменить **Дополнительные каталоги включаемых файлов** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalIncludeDirectories%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда выполняет поиск включаемых файлов, запрошенных файлом MAIN.c, в следующем порядке: сначала в каталоге, содержащем MAIN.c, затем в каталоге \INCLUDE, а затем в каталоге \MY\INCLUDE и наконец в каталогах, назначенных для ВКЛЮЧЕНИЯ переменная среды.  
  
```  
CL /I \INCLUDE /I\MY\INCLUDE MAIN.C  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)