---
title: "Параметр /ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework) | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ASSEMBLYLINKRESOURCE"
  - "VC.Project.VCLinkerTool.AssemblyLinkResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYLINKRESOURCE - параметр компоновщика"
  - "ASSEMBLYLINKRESOURCE - параметр компоновщика"
  - "-ASSEMBLYLINKRESOURCE - параметр компоновщика"
ms.assetid: 8b6ad184-1b33-47a4-8513-4803cf915b64
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Параметр /ASSEMBLYLINKRESOURCE (ссылка на ресурс .NET Framework)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYLINKRESOURCE:filename  
```  
  
## Заметки  
 Здесь:  
  
 *filename*  
 Файл ресурсов платформы .NET Framework, ссылку на который из сборки необходимо создать.  
  
## Заметки  
 Параметр \/ASSEMBLYLINKRESOURCE создает ссылку на ресурс .NET Framework в выходном файле; исходный файл не вставляется в выходной файл.  Параметр [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md) используется для внедрения файла ресурсов в выходной файл.  
  
 При создании сборки с помощью компоновщика связанные ресурсы являются открытыми.  
  
 При использовании параметра \/ASSEMBLYLINKRESOURCE необходимо выполнять компиляцию с параметром [\/clr](../../build/reference/clr-common-language-runtime-compilation.md). Использование параметра [\/LN](../../build/reference/ln-create-msil-module.md) или [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md) в этом случае не допускается.  
  
 Если параметр *filename* определяет файл ресурсов .NET Framework, созданный, например, с помощью программы [Resgen.exe](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) или среды разработки, обращение к этому файлу осуществляется в пространстве имен **System.Resources**.  Дополнительные сведения см. в описании класса [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx).  Для обращения к любым другим ресурсам во время выполнения используйте методы **GetManifestResource**\* класса **System.Reflection.Assembly**.  
  
 Файл *filename* может иметь любой формат.  Например, можно включить в состав сборки неуправляемую библиотеку DLL. Это позволит установить ее в глобальный кэш сборок и обеспечить доступ к ней из управляемого кода сборки.  
  
 Ниже перечислены прочие параметры компоновщика, влияющие на создание сборок:  
  
-   [\/ASSEMBLYDEBUG](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Командная строка**.  
  
4.  Введите параметр в поле **Дополнительные параметры**.  
  
### Установка данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)