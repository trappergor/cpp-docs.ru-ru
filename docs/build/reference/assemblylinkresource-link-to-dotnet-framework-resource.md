---
title: "-ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /ASSEMBLYLINKRESOURCE
- VC.Project.VCLinkerTool.AssemblyLinkResource
dev_langs: C++
helpviewer_keywords:
- -ASSEMBLYLINKRESOURCE linker option
- ASSEMBLYLINKRESOURCE linker option
- /ASSEMBLYLINKRESOURCE linker option
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a6a5ab1211cf3a1d5c834c0d32f1840db1bc2bf1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="assemblylinkresource-link-to-net-framework-resource"></a>Параметр /ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework)
```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 *filename*  
 Файл ресурсов .NET Framework, ссылку на который необходимо создать из сборки.  
  
## <a name="remarks"></a>Примечания  
 Параметр/assemblylinkresource создает ссылку на ресурс .NET Framework в выходном файле; файл ресурса не помещается в выходной файл. [/ ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) внедряет файл ресурсов в выходной файл.  
  
 Связанные ресурсы являются открытыми в сборке, если при создании компоновщик.  
  
 / Параметр ASSEMBLYLINKRESOURCE нужно будет добавить компиляции [/CLR](../../build/reference/clr-common-language-runtime-compilation.md); [/LN](../../build/reference/ln-create-msil-module.md) или [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) не допускается в этом случае.  
  
 Если *filename* является файлом ресурсов .NET Framework, созданным, например, с [Resgen.exe](/dotnet/framework/tools/resgen-exe-resource-file-generator) или в среде разработки, он может осуществляться с помощью членов **System.Resources** пространства имен. Дополнительные сведения см. в разделе [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx). Другие ресурсы, используйте **GetManifestResource** \* методы в **System.Reflection.Assembly** класса доступа к ресурсам во время выполнения.  
  
 *Имя файла* может иметь любой формат. Например может потребоваться сделать собственную библиотеку DLL частью сборки, чтобы он мог установлена в глобальный кэш сборок и доступна из управляемого кода в сборке.  
  
 Доступны следующие параметры компоновщика, влияющие на создание сборки.  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)