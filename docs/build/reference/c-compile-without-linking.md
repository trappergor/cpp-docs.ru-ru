---
title: "-c (компиляция без связывания) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /c
dev_langs: C++
helpviewer_keywords:
- suppress link
- cl.exe compiler, compiling without linking
- -c compiler option [C++]
- c compiler option [C++]
- /c compiler option [C++]
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a8f10aef6c2907d0730d358a6471c17bfd6a4cf8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="c-compile-without-linking"></a>Параметр /c (компиляция без связывания)
Запрет автоматического вызова к СВЯЗИ.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/c  
```  
  
## <a name="remarks"></a>Примечания  
 Компиляция с **/c** создает только OBJ-файлы. Связь необходимо вызвать явным образом с необходимые файлы и параметры для выполнения этапа связывания сборки.  
  
 Все внутренние проект, созданный в среде разработки используется **/c** параметр по умолчанию.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
-   Этот параметр не доступен в среде разработки.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   Сведения об установке этого параметра компилятора программными средствами см. в разделе <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда создает объектные файлы FIRST.obj и SECOND.obj. THIRD.obj учитывается.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 Чтобы создать исполняемый файл, следует вызвать программу LINK:  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)