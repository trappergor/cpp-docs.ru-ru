---
title: -LARGEADDRESSAWARE (обрабатывать большие адреса) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
dev_langs:
- C++
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f81424c49c5d67713cf478f69701c52504cfa8c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372130"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (Обрабатывать большие адреса)
```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/LARGEADDRESSAWARE сообщает компоновщику, приложение может обрабатывать адреса размером более 2 ГБ. В 64-разрядные компиляторы этот параметр включен по умолчанию. В 32-разрядные компиляторы: No включен, если параметр/LARGEADDRESSAWARE не задан в строке компоновщика.  
  
 Если приложение было скомпоновано с параметр/LARGEADDRESSAWARE, DUMPBIN [/Headers](../../build/reference/headers.md) будут отображаться сведения об ошибке.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **системы** страницу свойств.  
  
4.  Изменить **включить большие адреса** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)