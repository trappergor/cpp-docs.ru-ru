---
title: -ASSEMBLYDEBUG (Добавление атрибута DebuggableAttribute) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.AssemblyDebug
- /ASSEMBLYDEBUG
dev_langs:
- C++
helpviewer_keywords:
- /ASSEMBLYDEBUG linker option
- -ASSEMBLYDEBUG linker option
- ASSEMBLYDEBUG linker option
ms.assetid: 94443af3-470c-41d7-83a0-7434563d7982
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1a6060059609488eb902cbaba4f825663d3475b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372474"
---
# <a name="assemblydebug-add-debuggableattribute"></a>/ASSEMBLYDEBUG (добавление атрибута DebuggableAttribute)
```  
/ASSEMBLYDEBUG[:DISABLE]  
```  
  
 / ASSEMBLYDEBUG выдает **DebuggableAttribute** атрибута с отладочной информации отслеживания и выключает оптимизацию JIT. Это то же самое, что и при указании следующий атрибут в источнике:  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
 Добавляет выдает **DebuggableAttribute** атрибута, но отключает отслеживание отладочной информации и включает оптимизацию JIT-компилятора. Это то же самое, что и при указании следующий атрибут в источнике:  
  
```  
[assembly:Debuggable(false, false)];   // same as /ASSEMBLYDEBUG:DISABLE  
```  
  
 Значение по умолчанию — не создавал **DebuggableAttribute** атрибута.  
  
 DebuggableAttribute можно также добавить в сборку непосредственно в исходном коде. Например, примененная к объекту директива  
  
```  
[assembly:Debuggable(true, true)];   // same as /ASSEMBLYDEBUG  
```  
  
## <a name="remarks"></a>Примечания  
 Бывает необходимо явно указать, что управляемый образ отлаживаемых. С помощью [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) отдельно не достаточно.  
  
 Доступны следующие параметры компоновщика, влияющие на создание сборки.  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/DELAYSIGN](../../build/reference/delaysign-partially-sign-an-assembly.md)  
  
-   [/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md)  
  
-   [/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **отладки** страницу свойств.  
  
4.  Изменить **отлаживаемая сборка** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AssemblyDebug%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)