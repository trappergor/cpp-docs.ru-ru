---
title: "/DELAYSIGN (частичное подписание сборки) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delaysign"
  - "VC.Project.VCLinkerTool.DelaySign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYSIGN - параметр компоновщика"
  - "DELAYSIGN - параметр компоновщика"
  - "-DELAYSIGN - параметр компоновщика"
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /DELAYSIGN (частичное подписание сборки)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYSIGN[:NO]  
```  
  
## Заметки  
 где  
  
 NO  
 Указывает, что сборка не может быть частично подписана.  
  
## Заметки  
 Используйте **\/DELAYSIGN**, если необходимо только разместить открытый ключ в сборке.  По умолчанию используется **\/DELAYSIGN:NO**.  
  
 Параметр **\/DELAYSIGN** оказывает влияние на компиляцию только в том случае, если он используется одновременно с параметром [\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) или [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест \(метаданные сборки\) и подписывает хэш закрытым ключом.  Итоговая цифровая подпись хранится в файле, содержащем манифест.  При использовании отложенной подписи компоновщик не вычисляет и не сохраняет подпись, а резервирует место в файле для дальнейшего добавления подписи в сборку.  
  
 Например, чтобы поместить сборку в глобальный кэш для тестирования, используйте параметр **\/DELAYSIGN**.  После тестирования можно полностью подписать сборку, поместив в нее закрытый ключ.  
  
 Дополнительные сведения о подписи сборки см. в раздел [Сборки со строгими именами \(подписывание сборок\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) и [Отложенная подпись сборки](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
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