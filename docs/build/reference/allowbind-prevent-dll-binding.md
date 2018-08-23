---
title: -ALLOWBIND (запрет привязки DLL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.PreventDLLBinding
- /allowbind
dev_langs:
- C++
helpviewer_keywords:
- /ALLOWBIND linker option
- binding DLLs
- preventing DLL binding
- ALLOWBIND linker option
- -ALLOWBIND linker option
- DLLs [C++], preventing binding
ms.assetid: 30e37e24-12e4-407e-988a-39d357403598
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a0bff9ec6502aab5787c492a15e008bc29926163
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/16/2018
ms.locfileid: "42573384"
---
# <a name="allowbind-prevent-dll-binding"></a>/ALLOWBIND (запретить привязку DLL)
```  
/ALLOWBIND[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр /ALLOWBIND:NO устанавливает в заголовке библиотеки DLL бит, который указывает программе Bind.exe на то, что привязка образа не допускается. Если DLL имеет цифровую подпись, привязывать ее не следует (при привязке цифровая подпись становится недействительной).  
  
 Можно изменить существующую библиотеку DLL для функциональности параметра/ALLOWBIND с [параметра/ALLOWBIND](../../build/reference/allowbind.md) параметр программы EDITBIN.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации**, **компоновщика**и выберите **командной строки**.  
  
3.  Введите `/ALLOWBIND:NO` в **Дополнительные параметры**.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)   
 [Функция BindImage](/windows/desktop/api/imagehlp/nf-imagehlp-bindimage)   
 [Функция BindImageEx](/windows/desktop/api/imagehlp/nf-imagehlp-bindimageex)