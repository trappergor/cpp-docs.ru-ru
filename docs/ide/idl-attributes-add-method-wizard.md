---
title: Атрибуты IDL, мастер добавления метода | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.method.idlattrib
dev_langs:
- C++
helpviewer_keywords:
- Add Method Wizard [C++]
- IDL attributes, Add Method Wizard
ms.assetid: f80c3bc1-b515-4d6c-83ee-98c2c21ba902
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4a7a1e8fe89f64ad5909e7c1415545e3b3d80196
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="idl-attributes-add-method-wizard"></a>Атрибуты IDL, мастер добавления метода
Эта страница мастера добавления метода для указания любого интерфейса (IDL) параметры IDL для метода.  
  
 **id**  
 Задает числовой идентификатор, который идентифицирует метод. В разделе [идентификатор](http://msdn.microsoft.com/library/windows/desktop/aa367040) в *MIDL ссылка*.  
  
 Это поле недоступно для пользовательских интерфейсов и не доступен для диспетчера интерфейсов MFC.  
  
 **call_as**  
 Указывает имя удаленного метода, с которым сопоставлен этот локальный метод. В разделе [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) в *MIDL ссылка*.  
  
 Недоступно для диспетчера интерфейсов MFC.  
  
 **helpcontext**  
 Указывает идентификатор контекста, который позволяет пользователю просматривать сведения об этом методе в файле справки. В разделе [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) в *MIDL ссылка*.  
  
 Недоступно для диспетчера интерфейсов MFC.  
  
 **helpstring**  
 Определяет строку символов, используемый для описания элемента, к которому он применяется. По умолчанию он имеет значение «метод *имя метода*.» В разделе [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) в *MIDL ссылка*.  
  
 Недоступно для диспетчера интерфейсов MFC.  
  
 **Дополнительные атрибуты**  
 Недоступно для диспетчера интерфейсов MFC.  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|**hidden**|Указывает, что метод существует, но не должен отображаться в пользовательском браузере. В разделе [скрытые](http://msdn.microsoft.com/library/windows/desktop/aa366861) в *MIDL ссылка*.|  
|**Источник**|Указывает, что член метода является источником событий. В разделе [источника](http://msdn.microsoft.com/library/windows/desktop/aa367166) в *MIDL ссылка*.|  
|`local`|Указывает компилятору MIDL, что метод не является удаленной. В разделе [локального](http://msdn.microsoft.com/library/windows/desktop/aa367071) в *MIDL ссылка*.|  
|**restricted**|Указывает, что метод не может вызываться произвольным образом. В разделе [ограниченных](http://msdn.microsoft.com/library/windows/desktop/aa367157) в *MIDL ссылка*.|  
|**vararg**|Указывает, что метод принимает переменное число аргументов. Для этого последний аргумент должен быть безопасный массив **VARIANT** тип, содержащий все остальные аргументы. В разделе [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) в *MIDL ссылка*.|  
  
## <a name="see-also"></a>См. также  
 [Добавление метода](../ide/adding-a-method-visual-cpp.md)   
 [Мастер добавления метода](../ide/add-method-wizard.md)