---
title: "-ALLOWBIND (запретить привязку DLL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
dev_langs: C++
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dc5d5827da555cc11a7fbc1417a9a0e26f953cea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (запретить привязку DLL)
```  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр /ALLOWBIND:NO устанавливает в заголовке библиотеки DLL бит, который указывает программе Bind.exe на то, что привязка образа не допускается. Если DLL имеет цифровую подпись, привязывать ее не следует (при привязке цифровая подпись становится недействительной).  
  
 Можно изменить существующую библиотеку DLL для /ALLOWBIND функциональных возможностей с помощью [/ALLOWBIND](../../build/reference/allowbind.md) параметр программы EDITBIN.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации**, **компоновщика**и выберите **командной строки**.  
  
3.  Введите `/ALLOWBIND:NO` в **Дополнительные параметры**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Функция BindImage](http://msdn.microsoft.com/library/windows/desktop/ms679278.aspx)   
 [Функция BindImageEx](http://msdn.microsoft.com/library/windows/desktop/ms679279.aspx)