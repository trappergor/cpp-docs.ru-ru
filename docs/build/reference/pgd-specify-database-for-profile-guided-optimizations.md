---
title: "-PGD (Указание базы данных для профильной оптимизации) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs: C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb61395d9f3b8c98e17e3683a7c3897b9315d78b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (указание базы данных для профильной оптимизации)
/ PGD:`filename`  
  
## <a name="remarks"></a>Примечания  
 Здесь:  
  
 `filename`  
 Указывает имя PGD-файла, который будет использоваться для хранения сведений о выполняемой программы.  
  
## <a name="remarks"></a>Примечания  
 При использовании [/LTCG: PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md), используйте/PGD, чтобы указать нестандартным именем или расположением PGD-файла. Если/PGD не указан, имя файла .pgd будет иметь такое же, как имя выходного файла (.exe или .dll) и будет создан в том же каталоге, из которого был вызван по ссылке.  
  
 При использовании/LTCG: PGOPTIMIZE, используйте/PGD, чтобы указать имя PGD-файл, используемый для создания оптимизированного образа.  
  
 Дополнительные сведения см. в разделе [профильной оптимизации](../../build/reference/profile-guided-optimizations.md).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **оптимизации** страницу свойств.  
  
5.  Изменить **база данных профиля** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)