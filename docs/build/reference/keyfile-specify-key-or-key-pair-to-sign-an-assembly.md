---
title: "/KEYFILE (задание ключа или пары ключей для подписи сборки) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/keyfile"
  - "VC.Project.VCLinkerTool.KeyFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/KEYFILE - параметр компоновщика"
  - "KEYFILE - параметр компоновщика"
  - "-KEYFILE - параметр компоновщика"
ms.assetid: 9b71f8c0-541c-4fe5-a0c7-9364f42ecb06
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /KEYFILE (задание ключа или пары ключей для подписи сборки)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/KEYFILE:filename  
```  
  
## Заметки  
 Здесь:  
  
 *filename*  
 Имя файла, содержащего ключ.  Если эта строка содержит пробел, следует заключать ее в двойные кавычки \(""""\).  
  
## Заметки  
 Компоновщик вставляет открытый ключ в манифест сборки, после чего подписывает финальную сборку закрытым ключом.  Чтобы создать файл ключа, введите в командной строке [sn \-k](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) `file`.  Подписанная сборка — это сборка, имеющая строгое имя.  
  
 При компиляции с параметром [\/LN](../../build/reference/ln-create-msil-module.md) имя файла ключа хранится в модуле и внедряется в создаваемую сборку либо при компиляции сборки, включающей явную ссылку на этот модуль посредством директивы [\#using](../../preprocessor/hash-using-directive-cpp.md), либо при компоновке с параметром [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Сведения о шифровании можно также передать в компоновщик с помощью параметра [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  Если требуется частично подписанная сборка, следует использовать параметр [\/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md).  Дополнительные сведения о подписи сборки см. в разделе [Сборки со строгими именами \(подписывание сборок\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md).  
  
 Если параметры **\/KEYFILE** и **\/KEYCONTAINER** заданы вместе \(в командной строке или с помощью пользовательских атрибутов\), то сначала компоновщик будет пытаться использовать контейнер ключей.  В случае успеха сборка подписывается данными контейнера ключей.  Если компоновщик не обнаружит контейнер ключей, то он будет пытаться использовать файл, заданный параметром \/KEYFILE.  В случае успеха сборка подписывается данными из файла ключей, и эти данные о ключах будут установлены в контейнер ключей \(аналогично команде sn \-i\); таким образом, при следующей компиляции контейнер ключей будет действителен.  
  
 Обратите внимание, что файл ключей может содержать только открытый ключ.  
  
 Дополнительные сведения о подписи сборок см. в разделе [Создание и использование сборок со строгим именем](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md).  
  
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