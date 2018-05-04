---
title: -DYNAMICBASE (использование адреса места случайный выбор макета) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
dev_langs:
- C++
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 85af66c4ce05057eff63292061b66202aeebe160
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (использование технологии Address Space Layout Randomization (ASRL))
Указывает, следует ли создавать исполняемый образ, который может быть случайным образом перемещен во время загрузки с помощью функции randomization (ASLR) макет пространства адресов из [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/DYNAMICBASE[:NO]  
```  
  
## <a name="remarks"></a>Примечания  
 По умолчанию/DYNAMICBASE включен.  
  
 Этот параметр изменяет заголовок исполняемого файла, чтобы указать, требуется ли случайным образом переместить изменения из одной ветви в другую для приложения во время загрузки.  
  
 Поддерживается случайный выбор макета пространства адресов на [!INCLUDE[windowsver](../../build/reference/includes/windowsver_md.md)].  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Настройка этого параметра компоновщика в Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **Дополнительно** страницу свойств.  
  
5.  Изменить **случайное базовый адрес** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)