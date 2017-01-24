---
title: "/KEYCONTAINER (задание контейнера ключей для подписи сборки) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.KeyContainer"
  - "/keycontainer"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYCONTAINER - параметр компоновщика"
  - "KEYCONTAINER - параметр компоновщика"
  - "-KEYCONTAINER - параметр компоновщика"
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /KEYCONTAINER (задание контейнера ключей для подписи сборки)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYCONTAINER:name  
```  
  
## Заметки  
 где  
  
 *name*  
 Имя контейнера, содержащего ключ.  Если эта строка содержит пробел, следует заключать ее в двойные кавычки \(""""\).  
  
## Заметки  
 Компоновщик создает подписанную сборку, вставляя в манифест сборки открытый ключ и подписывая окончательную сборку закрытым ключом.  Чтобы создать файл ключа, введите в командной строке [sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file`.  Параметр **sn \-i** устанавливает пару ключей в контейнер.  
  
 При компиляции с параметром [\/LN](../../build/reference/ln-create-msil-module.md) имя файла ключа хранится в модуле и внедряется в создаваемую сборку либо при компиляции сборки, включающей явную ссылку на этот модуль посредством директивы [\#using](../../preprocessor/hash-using-directive-cpp.md), либо при компоновке с параметром [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Данные о шифровании можно также передать компилятору с помощью параметра [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md).  Если требуется частично подписанная сборка, следует использовать параметр [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md).  Дополнительные сведения о подписи сборки см. в разделе [Сборки со строгими именами \(подписывание сборок\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Ниже перечислены прочие параметры компоновщика, влияющие на создание сборок:  
  
-   [\/ASSEMBLYDEBUG](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
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