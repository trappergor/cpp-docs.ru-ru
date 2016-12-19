---
title: "Файлы шаблона | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "пользовательские мастера, файлы шаблона"
  - "файлы [C++], созданные мастером пользователя"
  - "шаблоны [C++], для мастеров"
ms.assetid: 48fae3d8-3a53-4f62-8010-144c5ffe334e
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Файлы шаблона
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Шаблоны, настраивающие мастер, являются коллекцией текстовых файлов, содержащих несколько [простых директив](../ide/template-directives.md). Синтаксический анализ шаблона и его обработка осуществляется в соответствии с указаниями пользователя. Затем шаблон добавляется в проект.  Сведения для разбора шаблонов берутся непосредственно из таблицы символов элемента управления мастера.  
  
 В следующем примере показан очень простой файл шаблона для мастера, в котором пользователю необходимо выбрать "А" или "В".  
  
## Пример  
  
```  
This file has been created by My Custom wizard.  
You selected:  
[!if TYPE_A]  
Type A  
[!else]  
Type B  
[!endif]  
The name of this project is [!output PROJECT_NAME].root.cpp:  
```  
  
 Если пользователь выберет тип "В", шаблон будет обработан как показано ниже:  
  
  **Этот файл был создан моим специальным мастером.  Выбрано следующее:**  
**Тип Б**  
**Имя данного проекта — MyApp8.**    
## Output  
  
```  
This file has been created by My Custom wizard.  
You selected:  
Type B  
The name of this project is MyApp8.  
```  
  
 **Примечание** Синтаксис, представленный выше, относится к новой версии Visual C\+\+ .NET.  Синтаксис предыдущих версий Visual C\+\+ не поддерживается в Visual C\+\+ .NET.  
  
## См. также  
 [Файлы, создаваемые для мастера](../ide/files-created-for-your-wizard.md)   
 [Специальный мастер](../ide/custom-wizard.md)   
 [Создание пользовательского мастера](../ide/creating-a-custom-wizard.md)   
 [Разработка мастера](../ide/designing-a-wizard.md)   
 [Файл Templates.inf](../Topic/Templates.inf%20File.md)