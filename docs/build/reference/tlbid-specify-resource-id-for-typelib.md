---
title: -TLBID (указать идентификатор ресурса для TypeLib) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tlbid
- VC.Project.VCLinkerTool.TypeLibraryResourceID
dev_langs:
- C++
helpviewer_keywords:
- tlb files, specifying resource ID
- -TLBID linker option
- .tlb files, specifying resource ID
- /TLBID linker option
- TLBID linker option
- type libraries, specifying resource ID
ms.assetid: 434b28a2-4656-4d52-ac82-8b18bf486fb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: acea8de3f656da54a0697dc5b980dd4913054a00
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32375169"
---
# <a name="tlbid-specify-resource-id-for-typelib"></a>/TLBID (указать идентификатор ресурса для TypeLib)
```  
/TLBID:id  
```  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
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