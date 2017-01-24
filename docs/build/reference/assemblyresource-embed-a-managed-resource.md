---
title: "/ASSEMBLYRESOURCE (внедрение управляемого ресурса) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.EmbedManagedResourceFile"
  - "/ASSEMBLYRESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ASSEMBLYRESOURCE - параметр компоновщика"
  - "сборки [C++]"
  - "сборки [C++], компоновка файлов ресурсов"
  - "ASSEMBLYRESOURCE - параметр компоновщика"
  - "-ASSEMBLYRESOURCE - параметр компоновщика"
ms.assetid: 0ce6e1fb-921b-4b1b-a59c-d35388d789f2
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /ASSEMBLYRESOURCE (внедрение управляемого ресурса)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ASSEMBLYRESOURCE:filename[,[name][,PRIVATE]]  
```  
  
## Параметры  
 *filename*  
 Управляемый ресурс, который требуется внедрить в эту сборку.  
  
 *name*  
 Необязательно.  Логическое имя ресурса; это имя используется для загрузки ресурса.  По умолчанию используется имя файла.  
  
 Дополнительно можно указать, должен ли файл быть закрытым в манифесте сборки.  По умолчанию файл *name* в составе сборки является общедоступным.  
  
## Заметки  
 Используйте параметр \/ASSEMBLYRESOURCE для внедрения ресурса в сборку.  
  
 Ресурсы в сборке являются открытыми, если они создаются при помощи компоновщика.  Компоновщик не позволяет переименовывать ресурс в сборке.  
  
 Если файл *filename* является файлом ресурсов .NET Framework \(RESOURCES\), созданным, например, с помощью [генератора файлов ресурсов \(Resgen.exe\)](../Topic/Resgen.exe%20\(Resource%20File%20Generator\).md) или в среде разработки, то обратиться к нему можно с помощью членов пространства имен **System.Resources** \(дополнительные сведения см. в описании класса [System.Resources.ResourceManager](https://msdn.microsoft.com/en-us/library/system.resources.resourcemanager.aspx)\).  Для доступа к другим ресурсам во время выполнения можно использовать методы **GetManifestResource**\* класса **System.Reflection.Assembly**.  
  
 Ниже перечислены прочие параметры компоновщика, влияющие на создание сборок:  
  
-   [\/ASSEMBLYDEBUG](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Задание свойств проекта C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Выберите папку **Компоновщик**.  
  
3.  Выберите страницу свойств **Ввод**.  
  
4.  Измените свойство **Внедрение файла управляемого ресурса**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EmbedManagedResourceFile%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)