---
title: -KEYCONTAINER (задание контейнера ключей для подписи сборки) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.KeyContainer
- /keycontainer
dev_langs:
- C++
helpviewer_keywords:
- KEYCONTAINER linker option
- /KEYCONTAINER linker option
- -KEYCONTAINER linker option
ms.assetid: 94882d12-b77a-49c7-96d0-18a31aee001e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f0e1f31e85c23b32bee1b8b968bbec65ee82beb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="keycontainer-specify-a-key-container-to-sign-an-assembly"></a>/KEYCONTAINER (задание контейнера ключей для подписи сборки)
```  
/KEYCONTAINER:name  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 *name*  
 Контейнер, содержащий ключ. Заключать строку в двойные кавычки (» «), если он содержит пробелы.  
  
## <a name="remarks"></a>Примечания  
 Компоновщик создает подписанную сборку путем вставки открытого ключа в манифест сборки и подписывая окончательную сборку закрытым ключом. Чтобы создать файл ключа, введите [sn -k](/dotnet/framework/tools/sn-exe-strong-name-tool) *filename* из командной строки. **sn -i** устанавливает пару ключей в контейнер.  
  
 Если компиляция выполняется с [/LN](../../build/reference/ln-create-msil-module.md), имя файла ключа сохраняется в модуле и включается в сборку, созданная при компиляции сборки, включающей явную ссылку на модуль через [#using](../../preprocessor/hash-using-directive-cpp.md), либо при компоновке с [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md).  
  
 Можно также передать сведения о шифровании компилятору с [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md). Используйте [/delaysign](../../build/reference/delaysign-partially-sign-an-assembly.md) Если необходимо использовать частично подписанную сборку. В разделе [строгое имя сборки (подписывание сборки) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) Дополнительные сведения о подписи сборки.  
  
 Доступны следующие параметры компоновщика, влияющие на создание сборки.  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
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