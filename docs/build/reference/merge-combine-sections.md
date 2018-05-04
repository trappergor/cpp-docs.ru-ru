---
title: -MERGE (Слияние разделов) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /merge
- VC.Project.VCLinkerTool.MergeSections
dev_langs:
- C++
helpviewer_keywords:
- sections, combining
- /MERGE linker option
- sections, naming
- sections
- -MERGE linker option
- MERGE linker option
ms.assetid: 10fb20c2-0b3f-4c8d-98a8-f69aedf03d52
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ece36de793b17b8cc064ec3837ea481a1ce870a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="merge-combine-sections"></a>/MERGE (Слияние разделов)
```  
/MERGE:from=to  
```  
  
## <a name="remarks"></a>Примечания  
 Параметр/Merge объединяет первую секцию (*из*) с помощью второго раздела (*для*), в результате раздел именования *для*. Например, `/merge:.rdata=.text`.  
  
 Если второй раздел не существует, связь переименовывает разделе *из* как *для*.  
  
 Параметр/Merge является полезным для создания vxd и замены имена разделов, созданных компилятором.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **Слияние разделов** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergeSections%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)