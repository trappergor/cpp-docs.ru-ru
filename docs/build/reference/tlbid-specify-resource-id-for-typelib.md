---
title: "-TLBID (указать идентификатор ресурса для TypeLib) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs: C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9a260882b7e4623149e9e82a3a635f7230b6985a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (указать идентификатор ресурса для TypeLib)
```  
/TLBID:id  
```  
  
## <a name="remarks"></a>Примечания  
 где:  
  
 `id`  
 Определяемый пользователем значение для библиотеки типов, созданной компоновщиком. Он переопределяет идентификатор ресурса по умолчанию 1.  
  
## <a name="remarks"></a>Примечания  
 При компиляции программы, использующей атрибуты, компоновщик создаст библиотеку типов. Компоновщик назначит идентификатор ресурса 1 библиотеке типов.  
  
 Если этот идентификатор ресурса конфликтует с одним из существующих ресурсов, можно указать другой идентификатор с помощью/TLBID. Диапазон значений, которые можно передать `id` — от 1 до 65535.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Нажмите кнопку **компоновщика** папки.  
  
3.  Нажмите кнопку **внедренный IDL** страницу свойств.  
  
4.  Изменить **идентификатор ресурса TypeLib** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryResourceID%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)