---
title: "Несколько сдвоенные интерфейсы | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 426109958cf9b34829c23ac0bfd59743f1681e72
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="multiple-dual-interfaces"></a>Несколько сдвоенные интерфейсы
Вы можете сочетать преимущества сдвоенный интерфейс (то есть, гибкость vtable и позднее связывание, таким образом сделать класс доступным для языков скриптов, а также язык C++) с помощью метода множественное наследование.  
  
 Несмотря на то, что возможность предоставлять доступ к нескольким сдвоенные интерфейсы с одним объектом COM, не рекомендуется. При наличии нескольких сдвоенные интерфейсы, должен содержать только один `IDispatch` интерфейс доступный. Методы, чтобы гарантировать, что это так несут ответственность, например потере функции или код повышения сложности. Разработчик, учитывая этот подход следует тщательно взвесить преимущества и недостатки.  
  
## <a name="exposing-a-single-idispatch-interface"></a>Предоставление единого интерфейса IDispatch  
 Можно предоставить несколько сдвоенные интерфейсы с одним объектом путем наследования от двух или более специализации `IDispatchImpl`. Тем не менее если вы позволяете клиентам запрашивать `IDispatch` интерфейса, необходимо будет использовать [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) макрос (или [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) для указания, какой базовый класс для использования Реализация `IDispatch`.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]  
  
 Поскольку только один `IDispatch` интерфейс предоставляется, клиенты, которые доступны только объектов с помощью `IDispatch` интерфейса не смогут получить доступ к методу или свойству в любом другом интерфейсе.  
  
## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Объединение нескольких сдвоенные интерфейсы в одной реализации интерфейса IDispatch  
 ATL не предоставляет поддержку объединения нескольких сдвоенные интерфейсы в одной реализации `IDispatch`. Тем не менее, существует несколько подходов, известные для вручную объединение интерфейсов, таких как создание шаблонного класса, который содержит объединение отдельных `IDispatch` интерфейсы, создавая новый объект для выполнения `QueryInterface` , или с помощью Реализация вложенных объектов для создания на основе typeInfo `IDispatch` интерфейса.  
  
 Эти подходы имеют проблемы с потенциальные конфликты имен, а также код сложности и удобства. Не рекомендуется создавать несколько сдвоенных интерфейсов.  
  
## <a name="see-also"></a>См. также  
 [Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)

