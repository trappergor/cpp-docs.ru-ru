---
title: "-Tc, - Tp-TC, - TP (определение типа исходного файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.CompileAs
- VC.Project.VCCLCompilerTool.CompileAs
- /Tp
- /tc
dev_langs: C++
helpviewer_keywords:
- Tp compiler option [C++]
- /Tc compiler option [C++]
- -Tc compiler option [C++]
- source files, specifying to compiler
- Tc compiler option [C++]
- /Tp compiler option [C++]
- -Tp compiler option [C++]
ms.assetid: 7d9d0a65-338b-427c-8b48-fff30e2f9d2b
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3b7508bf3ff65e27cab3260577d2831de00eb2b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="tc-tp-tc-tp-specify-source-file-type"></a>Параметры /Tc, /Tp, /TC, /TP (определение типа исходного файла)
**/Tc** параметр указывает, что `filename` является исходным файлом C, даже если он не имеет расширения c. **/Tp** параметр указывает, что `filename` является исходным файлом C++, даже если он не имеет расширения .cpp или .cxx. Пробел между параметром и `filename` является необязательным. Каждый параметр определяет только один файл; Чтобы указать дополнительные файлы, повторите параметр.  
  
 **/TC** и **/TP** представляют собой глобальные варианты **/Tc** и **/Tp**. Они указывают на компилятор будет рассматривать все файлы с именем в командной строке, как исходные файлы C (**/TC**) или исходные файлы C++ (**/TP**), независимо от расположения в командной строке с параметром. Эти глобальные параметры можно переопределить на один файл с помощью параметра **/Tc** или **/Tp**.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Tcfilename  
/Tpfilename  
/TC  
/TP  
```  
  
## <a name="arguments"></a>Аргументы  
 `filename`  
 Исходный файл C или C++.  
  
## <a name="remarks"></a>Примечания  
 По умолчанию то подразумевается, что файлы с расширением C исходные файлы и файлы с расширением CPP или .cxx расширения, исходные файлы C++.  
  
 При любом **TC** или **Tc** параметр указан, Любая спецификация [/Zc: wchar_t (wchar_t – это собственный тип)](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) параметр учитывается.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **компилировать как** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileAs%2A>.  
  
## <a name="examples"></a>Примеры  
 Следующая команда CL указывает, что MAIN.c, TEST.prg и COLLATE.prg все исходные файлы C. CL не распознает PRINT.prg.  
  
```  
CL MAIN.C /TcTEST.PRG /TcCOLLATE.PRG PRINT.PRG  
```  
  
 Следующая команда CL указывает, что TEST1.c, TEST2.cxx, TEST3.huh и TEST4.o компилируются как файлы C++ и TEST5.z компилируется как файл C.  
  
```  
CL TEST1.C TEST2.CXX TEST3.HUH TEST4.O /Tc TEST5.Z /TP  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)