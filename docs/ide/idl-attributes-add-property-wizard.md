---
title: "Атрибуты IDL, мастер добавления свойства | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.prop.idlattributes"
dev_langs: 
  - "C++"
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Атрибуты IDL, мастер добавления свойства
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта страница мастера добавления метода используется при задании параметров языка определения интерфейса \(IDL\) для указанного свойства.  
  
 **id**  
 Устанавливает числовой идентификатор, который идентифицирует свойство.  Данный параметр недоступен для свойств настраиваемых интерфейсов.  См. [Id](http://msdn.microsoft.com/library/windows/desktop/aa367040) в *справочнике по MIDL*.  
  
 **helpcontext**  
 Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом свойстве в файле справки.  См. [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) в *справочнике по MIDL*.  
  
 **helpstring**  
 Задает символьную строку, используемую для описания элемента, к которому она применяется.  По умолчанию строка задана в "свойство *имя свойства*". См. [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) в *Справочнике по MIDL*.  
  
## Другие параметры  
 Для типов свойств доступны не все параметры.  
  
|Параметр|Описание|  
|--------------|--------------|  
|**bindable**|Указывает, что свойство поддерживает привязку данных.  См. [bindable](http://msdn.microsoft.com/library/windows/desktop/aa366738) в *Справочнике по MIDL*.  Для базовой реализации свойства параметр задан по умолчанию и является неизменяемым.|  
|**defaultbind**|Указывает, что данное одиночное, связываемое свойство представляет объект наилучшим образом.  См. [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) в *Справочнике по MIDL*.|  
|**displaybind**|Указывает, что данное свойство должно отображаться для пользователя как связываемое.  См. [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) в *Справочнике по MIDL*.|  
|**immediatebind**|Указывает, что база данных будет немедленно уведомляться обо всех изменениях свойства объекта с привязкой к данным.  См. [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) в *Справочнике по MIDL*.|  
|**defaultcollelem**|Указывает, что свойство является функцией доступа к элементу коллекции, заданной по умолчанию.  См. [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) в *Справочнике по MIDL*.|  
|**nonbrowsable**|Отмечает члены интерфейса или диспетчера интерфейсов, которые не отображаются в обозревателе свойств.  См. [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) в *Справочнике по MIDL*.|  
|**requestedit**|Указывает, что свойство поддерживает уведомление **OnRequestEdit** см. [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) в *Справочнике по MIDL*.  Для базовой реализации свойства параметр задан по умолчанию и является неизменяемым.|  
|**source**|Указывает, что член свойства является источником событий.  См. [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) в *справочнике по MIDL*.|  
|**hidden**|Указывает, что свойство существует, но не должно отображаться в браузере, ориентированном на пользователя.  См. раздел [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) в *справочнике по MIDL*.|  
|**restricted**|Указывает, что свойство не может вызываться произвольным образом.  См. [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) в *справочнике по MIDL*.|  
|`local`|Указывает компилятору MIDL, что свойство не является удаленным.  См. [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) в *справочнике по MIDL*.|  
  
## См. также  
 [Добавление свойства](../Topic/Adding%20a%20Property%20\(Visual%20C++\).md)   
 [Мастер добавления свойств, страница "Имена"](../ide/names-add-property-wizard.md)   
 [Реализация интерфейса](../ide/implementing-an-interface-visual-cpp.md)   
 [Свойства хранения](../ide/stock-properties.md)