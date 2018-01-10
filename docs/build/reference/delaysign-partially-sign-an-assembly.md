---
title: "-DELAYSIGN (частичное подписание сборки) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
dev_langs: C++
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f67e4da2d85d94854ec0802450b41333d6577175
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (частичное подписание сборки)
```  
/DELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 где  
  
 НЕТ  
 Указывает, что сборка должна не быть подписана частично.  
  
## <a name="remarks"></a>Примечания  
 Используйте **/delaysign** Если необходимо только поместить открытый ключ в сборку. Значение по умолчанию — **/delaysign: no**.  
  
 **/Delaysign** параметр действует только при использовании [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) или [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  
  
 При запросе полностью подписанной сборки компилятор хэширует файл, содержащий манифест (метаданные сборки), и подписывает хэш закрытым ключом. Итоговая цифровая подпись хранится в файле, содержащем манифест. При отложенной подписи сборки компоновщик вычислений и не сохраняет подпись, а резервирует место в файле для последующего добавления подписи.  
  
 Например, с помощью **/delaysign** допускает, чтобы поместить сборку в глобальный кэш для тестирования. После тестирования можно полностью подписать сборку, поместив закрытый ключ в сборку.  
  
 В разделе [строгое имя сборки (подписывание сборки) (C + +/ CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) и [отложенная подпись сборки](/dotnet/framework/app-domains/delay-sign-assembly) Дополнительные сведения о подписи сборки.  
  
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