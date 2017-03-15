---
title: "/MANIFESTUAC (встраивает в манифест сведений об UAC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UACUIAccess"
  - "VC.Project.VCLinkerTool.UACExecutionLevel"
  - "VC.Project.VCLinkerTool.EnableUAC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTUAC - параметр компоновщика"
  - "MANIFESTUAC - параметр компоновщика"
  - "-MANIFESTUAC - параметр компоновщика"
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /MANIFESTUAC (встраивает в манифест сведений об UAC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Указывает, следует ли внедрять в манифест программы сведения о контроле учетных записей.  
  
## Синтаксис  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### Параметры  
 `fragment`  
 Строка, содержащая значения `level` и `uiAccess`.  Дополнительные сведения см. в подразделе "Заметки" далее в этом разделе.  
  
 `_level`  
 Может иметь следующие значения: *asInvoker*, *highestAvailable* или *requireAdministrator*.  По умолчанию используется значение asInvoker.  Дополнительные сведения см. в подразделе "Заметки" далее в этом разделе.  
  
 `_uiAccess`  
 `true` при необходимости приложение обойти уровни защиты интерфейса пользователя и администрирования входных данных для окна с наивысшим разрешения на рабочем столе; в противном случае `false`.  По умолчанию используется значение `false`.  Значение `true` для этого свойства следует использовать только в приложениях, обеспечивающих специальные возможности пользовательского интерфейса.  
  
## Заметки  
 Если в командной строке указано несколько параметров \/MANIFESTUAC, приоритет имеет последний из них.  
  
 Возможные значения параметра \/MANIFESTUAC:level:  
  
-   `asInvoker` — приложение будет запущено с теми же разрешениями, что и запустивший его процесс.  Можно повысить уровень разрешений приложения, выбрав **Запуск от имени администратора**.  
  
-   highestAvailable — приложение будет запущено с наивысшим возможным уровнем разрешений.  Если пользователь, который запускает приложение, входит в группу "Администраторы", то этот параметр действует аналогично requireAdministrator.  Если наивысший возможный уровень разрешений превышает уровень открывающего процесса, система попросит ввести учетные данные.  
  
-   requireAdministrator — приложение будет запущено с разрешениями администратора.  Пользователь, запускающий приложение, должен входить в группу "Администраторы".  Если открывающий процесс не выполняется с разрешениями администратора, система попросит ввести учетные данные.  
  
 Можно указать значения level и uiAccess за один шаг с помощью параметра \/MANIFESTUAC:fragment.  Атрибут fragment должен иметь следующий формат:  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### Установка данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта.  Дополнительные сведения см. в разделе [Открытие свойств страниц проекта](../../misc/how-to-open-project-property-pages.md).  
  
2.  Разверните узел **Свойства конфигурации**.  
  
3.  Разверните узел **Компоновщик**.  
  
4.  Выберите страницу свойств **Файл манифеста**.  
  
5.  Измените свойства **Включить контроль учетных записей пользователей \(UAC\)**, **Уровень выполнения UAC**, и **Обход защиты пользовательского интерфейса UAC**.  
  
### Установка данного параметра компоновщика программным способом  
  
1.  См. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.  
  
## См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)