---
title: "Атрибуты IDL, мастер добавления свойства | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.prop.idlattributes
dev_langs:
- C++
ms.assetid: 356ed666-79d0-4bd9-a5e7-cda679cbadbd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ec158c117161c5a5c2ffd23cef0d5c79c312ae7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="idl-attributes-add-property-wizard"></a>Атрибуты IDL, мастер добавления свойства
Эта страница мастера добавления свойства для указания любого интерфейса (IDL) параметры IDL для свойства.  
  
 **id**  
 Задает числовой идентификатор, который определяет свойство. Этот параметр недоступен для свойств настраиваемых интерфейсов. В разделе [идентификатор](http://msdn.microsoft.com/library/windows/desktop/aa367040) в *MIDL ссылка*.  
  
 **helpcontext**  
 Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом свойстве в файле справки. В разделе [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) в *MIDL ссылка*.  
  
 **helpstring**  
 Определяет строку символов, используемый для описания элемента, к которому он применяется. По умолчанию он имеет значение «свойство *имя свойства*.» В разделе [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) в *MIDL ссылка*.  
  
## <a name="other-options"></a>Другие параметры  
 Не все параметры, доступные для всех типов свойств.  
  
|Параметр|Описание:|  
|------------|-----------------|  
|**bindable**|Указывает, что свойство поддерживает привязку данных. В разделе [привязываемых](http://msdn.microsoft.com/library/windows/desktop/aa366738) в *MIDL ссылка*. Для базовой реализации свойства этот параметр имеет значение по умолчанию и является неизменяемым.|  
|**defaultbind**|Указывает, что это свойство одиночное, связываемое наиболее представляет объект. В разделе [defaultbind](http://msdn.microsoft.com/library/windows/desktop/aa366790) в *MIDL ссылка*.|  
|**displaybind**|Указывает, что это свойство должно отображаться пользователю как связываемое. В разделе [displaybind](http://msdn.microsoft.com/library/windows/desktop/aa366804) в *MIDL ссылка*.|  
|**immediatebind**|Указывает, будут немедленно уведомлены базы данных всех изменений для этого свойства объекта с привязкой к данным. В разделе [immediatebind](http://msdn.microsoft.com/library/windows/desktop/aa367045) в *MIDL ссылка*.|  
|**defaultcollelem**|Указывает, что свойство является функция доступа к элементу коллекции по умолчанию. В разделе [defaultcollelem](http://msdn.microsoft.com/library/windows/desktop/aa366792) в *MIDL ссылка*.|  
|**nonbrowsable**|Теги член интерфейса или disp-интерфейс, который не должен отображаться в обозревателе свойств. В разделе [nonbrowsable](http://msdn.microsoft.com/library/windows/desktop/aa367117) в *MIDL ссылка*.|  
|**requestedit**|Указывает, что свойство поддерживает **OnRequestEdit** уведомления см. в разделе [requestedit](http://msdn.microsoft.com/library/windows/desktop/aa367155) в *MIDL ссылка*. Для базовой реализации свойства этот параметр имеет значение по умолчанию и является неизменяемым.|  
|**источник**|Указывает, что член свойства является источником событий. В разделе [источника](http://msdn.microsoft.com/library/windows/desktop/aa367166) в *MIDL ссылка*.|  
|**hidden**|Указывает, что свойство существует, но не должен отображаться в пользовательском браузере. В разделе [скрытые](http://msdn.microsoft.com/library/windows/desktop/aa366861) в *MIDL ссылка*.|  
|**restricted**|Указывает, что свойство не может вызываться произвольным образом. В разделе [ограниченных](http://msdn.microsoft.com/library/windows/desktop/aa367157) в *MIDL ссылка*.|  
|`local`|Указывает компилятору MIDL, что свойство не является удаленной. В разделе [локального](http://msdn.microsoft.com/library/windows/desktop/aa367071) в *MIDL ссылка*.|  
  
## <a name="see-also"></a>См. также  
 [Добавление свойства](../ide/adding-a-property-visual-cpp.md)   
 [Имена, мастер добавления свойства](../ide/names-add-property-wizard.md)   
 [Реализация интерфейса](../ide/implementing-an-interface-visual-cpp.md)   
 [Свойства хранения](../ide/stock-properties.md)