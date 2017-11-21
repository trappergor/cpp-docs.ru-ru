---
title: "-Fo (имя объектного файла) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Fo
- VC.Project.VCCLCompilerTool.ObjectFile
- VC.Project.VCCLWCECompilerTool.ObjectFile
dev_langs: C++
helpviewer_keywords:
- Fo compiler option [C++]
- object files, naming
- /Fo compiler option [C++]
- -Fo compiler option [C++]
ms.assetid: 0e6d593e-4e7f-4990-9e6e-92e1dcbcf6e6
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba311166de220cc19403fd9d5eb10ae84bffb58e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fo-object-file-name"></a>/Fo (имя объектного файла)
Указывает имя файла или каталога объектного файла (OBJ), которое следует использовать вместо имени по умолчанию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Fopathname  
```  
  
## <a name="remarks"></a>Примечания  
 Если этот параметр не используется, объектный файл использует базовое имя исходного файла и расширение OBJ.. Можно использовать любое имя и расширение, но Рекомендуемое соглашение заключается в использовании. obj.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Откройте страницу свойств **Выходные файлы** .  
  
4.  Изменить **имя объектного файла** свойство.  В среде разработки объектный файл должен иметь расширение. obj.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ObjectFile%2A>.  
  
## <a name="example"></a>Пример  
 Следующая команда создает объектный файл с именем this.obj: в существующем каталоге \OBJECT на диске B.  
  
```  
CL /FoB:\OBJECT\ THIS.C  
```  
  
## <a name="see-also"></a>См. также  
 [Выходного файла (/ F) параметры](../../build/reference/output-file-f-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Указание пути](../../build/reference/specifying-the-pathname.md)