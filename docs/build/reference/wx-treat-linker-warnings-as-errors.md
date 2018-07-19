---
title: -WX (обрабатывать предупреждения компоновщика как ошибки) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /WX
dev_langs:
- C++
helpviewer_keywords:
- /WX linker option
- -WX linker option
- WX linker option
ms.assetid: e4ba97c7-93f7-43ae-a4bb-d866790926c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 686b17a3db00175340e3490241c6c2e9f9325225
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377291"
---
# <a name="wx-treat-linker-warnings-as-errors"></a>/WX (Обрабатывать предупреждения компоновщика как ошибки)
```  
/WX[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 /WX запрещает создание выходного файла, если компоновщик создает предупреждение.  
  
 Это похоже на **/WX** компилятором (см. [/w, помощью/W0, /W1, /W2, /W3, / W4, /w1, /w2, /w3, / W4, / Wall, /wd, и мы /wo, / wv, / WX (порог предупреждений)](../../build/reference/compiler-option-warning-level.md) для получения дополнительной информации). Однако указание **/WX** для компиляции не означает, что **/WX** также будет действовать на этапе компоновки; необходимо явно указать **/WX** для каждого средства.  
  
 По умолчанию **/WX** не действует. Обрабатывать предупреждения компоновщика как ошибки, укажите **/WX**. **/WX:no** совпадает со значением не указывая **/WX**.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр в **Дополнительные параметры** поле.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)