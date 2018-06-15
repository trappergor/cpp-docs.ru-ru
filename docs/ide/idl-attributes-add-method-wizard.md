---
title: Атрибуты IDL, мастер добавления метода | Документы Майкрософт
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
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337773"
---
# <a name="idl-attributes-add-method-wizard"></a>Атрибуты IDL, мастер добавления метода
Используйте эту страницу мастера добавления метода, чтобы указать все параметры IDL для этого метода.  
  
 **id**  
 Задает числовой идентификатор, который определяет этот метод. См. описание [id](http://msdn.microsoft.com/library/windows/desktop/aa367040) в *справочнике по MIDL*.  
  
 Это поле недоступно для настраиваемых интерфейсов и disp-интерфейсов MFC.  
  
 **call_as**  
 Указывает имя удаленного метода, с которым можно сопоставить этот локальный метод. См. описание [call_as](http://msdn.microsoft.com/library/windows/desktop/aa366748) в *справочнике по MIDL*.  
  
 Недоступно для disp-интерфейсов MFC.  
  
 **helpcontext**  
 Задает идентификатор контекста, позволяющий пользователю просматривать в файле справки информацию об этом методе. См. описание [helpcontext](http://msdn.microsoft.com/library/windows/desktop/aa366851) в *справочнике по MIDL*.  
  
 Недоступно для disp-интерфейсов MFC.  
  
 **helpstring**  
 Определяет строку символов, используемую для описания элемента, к которому оно применяется. По умолчанию имеет значение "method *имя метода*." См. описание [helpstring](http://msdn.microsoft.com/library/windows/desktop/aa366856) в *справочнике по MIDL*.  
  
 Недоступно для disp-интерфейсов MFC.  
  
 **Дополнительные атрибуты**  
 Недоступно для disp-интерфейсов MFC.  
  
|Атрибут|Описание:|  
|---------------|-----------------|  
|**hidden**|Указывает, что метод существует, но не должен отображаться в пользовательском браузере. См. описание [hidden](http://msdn.microsoft.com/library/windows/desktop/aa366861) в *справочнике по MIDL*.|  
|**source**|Указывает, что член метода является источником событий. См. описание [source](http://msdn.microsoft.com/library/windows/desktop/aa367166) в *справочнике по MIDL*.|  
|`local`|Указывает компилятору MIDL, что метод не является удаленным. См. описание [local](http://msdn.microsoft.com/library/windows/desktop/aa367071) в *справочнике по MIDL*.|  
|**restricted**|Указывает, что метод не может вызываться произвольным образом. См. описание [restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) в *справочнике по MIDL*.|  
|**vararg**|Указывает, что метод принимает переменное число аргументов. В этом случае последний аргумент должен быть безопасным массивом типа **VARIANT**, содержащим все остальные аргументы. См. описание [vararg](http://msdn.microsoft.com/library/windows/desktop/aa367304) в *справочнике по MIDL*.|  
  
## <a name="see-also"></a>См. также  
 [Добавление метода](../ide/adding-a-method-visual-cpp.md)   
 [Мастер добавления метода](../ide/add-method-wizard.md)