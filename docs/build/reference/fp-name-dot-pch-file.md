---
title: "-Fp (имя. PCH-файл) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
dev_langs: C++
helpviewer_keywords:
- Fp compiler option [C++]
- -Fp compiler option [C++]
- naming precompiler header files
- PCH files, naming
- names [C++], PCH
- .pch files, naming
- precompiled header files, naming
- /Fp compiler option [C++]
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 77ba54705ec4037f1c98a2ae1832dddcc551956e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fp-name-pch-file"></a>/Fp (имя PCH-файла)
Предоставляет имя пути для предкомпилированного заголовка вместо использования имени пути по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
> **/ Fp**_pathname_  
  
## <a name="remarks"></a>Примечания  
 Этот параметр используется с [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md) или [/Yu (использование предкомпилированных заголовков)](../../build/reference/yu-use-precompiled-header-file.md) для предоставления имени пути предкомпилированного заголовка вместо использования имени пути по умолчанию. Можно также использовать **/FP** с **/Yc** позволяет указать использование файла предкомпилированного заголовка, который отличается от **/Yc***filename* аргументов и из базового имени исходного файла.  
  
 Если не указать расширение как часть имени пути, предполагается расширение PCH. Если задан каталог без имени файла, имя файла по умолчанию является VC*x*0.pch, где *x* – основная используемая версия Visual C++.  
  
 Можно также использовать **/FP** вариант с **/Yu**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **предварительно скомпилированные заголовки** страницу свойств.  
  
4.  Изменить **файл предкомпилированного заголовка** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile%2A>.  
  
## <a name="example"></a>Пример  
 Если требуется создать файл предкомпилированного заголовка для отладочной версии программы и компиляции заголовочные файлы и исходный код, можно определить команду таких как:  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## <a name="example"></a>Пример  
 Следующая команда задает использование файла предкомпилированного заголовка с именем MYPCH.pch. Компилятор предполагает, что исходный код в PROG.cpp было предварительно скомпилировано через MYAPP.h и что предварительно скомпилированный код содержится в файле MYPCH.pch. Она использует содержимое файла MYPCH.pch и компилирует остаток PROG.cpp для создания OBJ-файл. В этом примере получается файл с именем PROG.exe.  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Указание пути](../../build/reference/specifying-the-pathname.md)