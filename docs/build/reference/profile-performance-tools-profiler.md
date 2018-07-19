---
title: -ПРОФИЛЬ (профилировщик средств обеспечения производительности) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Profile
dev_langs:
- C++
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15379914b4c4852e3065d1abc03c2ce1b17fb044
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377122"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (профилировщик средств обеспечения производительности)
Создает выходной файл, который может быть использован для профилировщика производительности инструментов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/PROFILE  
```  
  
## <a name="remarks"></a>Примечания  
 / PROFILE подразумевает следующие параметры компоновщика:  
  
-   [/ OPT: REF](../../build/reference/opt-optimizations.md)  
  
-   / OPT: NOICF  
  
-   [/ INCREMENTAL: NO](../../build/reference/incremental-link-incrementally.md)  
  
-   [/ FIXED: NO](../../build/reference/fixed-fixed-base-address.md)  
  
 Или профиль указывает компоновщику создает раздел переадресации в образе программы.  Он позволяет профилировщику преобразовать образ программы, чтобы получить данные профилирования.  
  
 **/ ПРОФИЛЯ** доступна только в версиях Enterprise (командной разработки).  Дополнительные сведения о PREfast см. в разделе [анализа кода C/C++ Обзор](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **Дополнительно** страницу свойств.  
  
5.  Изменить **профиль** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)