---
title: "Атрибуты IDL, мастер добавления метода | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.method.idlattrib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "мастер добавления метода [C++]"
  - "Атрибуты IDL, мастер добавления метода"
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Атрибуты IDL, мастер добавления метода
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта страница мастера добавления метода используется для задания для метода параметров языка определения интерфейса \(IDL\).  
  
 **id**  
 Устанавливает числовой идентификатор, который идентифицирует метод.  См. [Id](http://msdn.microsoft.com/library/windows/desktop/aa367040) в *справочнике по MIDL*.  
  
 Это поле недоступно для пользовательских интерфейсов и для диспетчерских интерфейсов MFC.  
  
 **call\_as**  
 Указывает имя удаленного метода, которому может быть сопоставлен этот локальный метод.  См. [call\_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) в *справочнике по MIDL*.  
  
 Для диспетчерских интерфейсов MFC аргумент недоступен.  
  
 **helpcontext**  
 Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом методе в файле справки.  См. [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) в *справочнике по MIDL*.  
  
 Для диспетчерских интерфейсов MFC аргумент недоступен.  
  
 **helpstring**  
 Задает символьную строку, используемую для описания элемента, к которому она применяется.  По умолчанию установлена в "метод *имя метода*". См. [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) в *Справочнике по MIDL*.  
  
 Для диспетчерских интерфейсов MFC аргумент недоступен.  
  
 **Дополнительные атрибуты**  
 Для диспетчерских интерфейсов MFC аргумент недоступен.  
  
|Атрибут|Описание|  
|-------------|--------------|  
|**hidden**|Указывает, что метод существует, но не должен отображаться в браузере, ориентированном на пользователя.  См. раздел [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) в *справочнике по MIDL*.|  
|**source**|Указывает, что член метода является источником событий.  См. [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) в *справочнике по MIDL*.|  
|`local`|Указывает компилятору MIDL, что метод не удаленный.  См. [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) в *справочнике по MIDL*.|  
|**restricted**|Указывает, что метод не может вызываться произвольным образом.  См. [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) в *справочнике по MIDL*.|  
|**vararg**|Указывает, что метод принимает переменное число аргументов.  Для этого последний аргумент должен быть безопасным массивом типа **VARIANT**, который содержит все остальные аргументы.  См. [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) в *справочнике по MIDL*.|  
  
## См. также  
 [Добавление метода](../ide/adding-a-method-visual-cpp.md)   
 [Мастер добавления метода](../ide/add-method-wizard.md)