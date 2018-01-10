---
title: "-MANIFESTUAC (встраивает UAC сведения в манифесте) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.UACUIAccess
- VC.Project.VCLinkerTool.UACExecutionLevel
- VC.Project.VCLinkerTool.EnableUAC
dev_langs: C++
helpviewer_keywords:
- /MANIFESTUAC linker option
- MANIFESTUAC linker option
- -MANIFESTUAC linker option
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 564c17336936866750d05137a7bcd101b3a6534d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="manifestuac-embeds-uac-information-in-manifest"></a>/MANIFESTUAC (встраивает в манифест сведений об UAC)
Указывает, следует ли внедрять в манифест программы сведения о контроле учетных записей.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### <a name="parameters"></a>Параметры  
 `fragment`  
 Строка, содержащая `level` и `uiAccess` значения. Дополнительные сведения см. в разделе "Примечания" этого раздела.  
  
 `_level`  
 Один из *asInvoker*, *highestAvailable*, или *requireAdministrator*. По умолчанию asInvoker. Дополнительные сведения см. в разделе "Примечания" этого раздела.  
  
 `_uiAccess`  
 `true`Если требуется приложение обходить уровни защиты пользовательского интерфейса и направляют входные данные для windows с более высоким уровнем разрешений на рабочем столе; в противном случае `false`. По умолчанию — `false`. Значение `true` только для приложений со специальными возможностями интерфейса пользователя.  
  
## <a name="remarks"></a>Примечания  
 Если указать несколько параметров/MANIFESTUAC, в командной строке, приоритет имеет последний из них.  
  
 Доступны следующие варианты для /MANIFESTUAC:level:  
  
-   `asInvoker`: Приложение будет работать с теми же разрешениями, что и запустивший его процесс. Приложение может повысить уровень разрешений, выбрав **Запуск от имени администратора**.  
  
-   highestAvailable: приложение будет работать с самым высоким уровнем разрешений, как. Если пользователь, запускающий приложение является членом группы «Администраторы», этот параметр является аналогично requireAdministrator. Если наивысший возможный уровень разрешений превышает уровень открывающего процесса, система предложит ввести учетные данные.  
  
-   requireAdministrator: приложение будет выполняться с разрешениями администратора. Пользователь, запускающий приложения должен быть членом группы «Администраторы». Если время открытия не запущена с правами администратора, система предложит ввести учетные данные.  
  
 С помощью параметра /MANIFESTUAC:fragment можно указать значения уровня и uiAccess за один шаг. Фрагмент должен иметь следующий вид:  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации** узла.  
  
3.  Разверните **компоновщика** узла.  
  
4.  Выберите **файл манифеста** страницу свойств.  
  
5.  Изменить **включить (Учетных записей)**, **уровень выполнения UAC**, и **обход защиты пользовательского интерфейса UAC** свойства.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)