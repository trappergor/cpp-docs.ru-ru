---
title: -Fp (имя. PCH-файл) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.PrecompiledHeaderFile
- /fp
- VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 80f59477695b83b33dd3cfa2b37837c5b52c8002
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376336"
---
# <a name="fp-name-pch-file"></a>/Fp (имя PCH-файла)
Предоставляет имя пути для предкомпилированного заголовка вместо использования имени пути по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
> **/ Fp**_pathname_  
  
## <a name="remarks"></a>Примечания  
 Этот параметр используется с [/Yc (создать файл предкомпилированного заголовка)](../../build/reference/yc-create-precompiled-header-file.md) или [/Yu (использование предкомпилированных заголовков)](../../build/reference/yu-use-precompiled-header-file.md) для предоставления имени пути предкомпилированного заголовка вместо использования имени пути по умолчанию. Можно также использовать **/FP** с **/Yc** позволяет указать использование файла предкомпилированного заголовка, который отличается от **/Yc *** filename* аргумент и из базового имени исходного файла.  
  
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