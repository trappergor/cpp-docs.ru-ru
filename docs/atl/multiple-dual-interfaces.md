---
title: "Multiple Dual Interfaces | Microsoft Docs"
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
  - "COM_INTERFACE_ENTRY_IID macro"
  - "COM_INTERFACE_ENTRY2 macro"
  - "сдвоенные интерфейсы, exposing multiple"
  - "IDispatchImpl - класс, multiple dual interfaces"
  - "multiple dual interfaces"
  - "multiple dual interfaces, exposing with ATL"
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multiple Dual Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно сочетать преимущества повторяющегося интерфейса \(то есть гибкости в таблице vtable и позднее связывание, таким образом, делая доступными класса в скриптовым языкам, а также C\+\+\) с методами множественного наследования.  
  
 Хотя можно предоставить несколько сдвоенные интерфейсы для одного com\-объекта, не рекомендуется.  Если несколько сдвоенные интерфейсы, он должен содержать только один `IDispatch` предоставленный интерфейс.  Доступные методы убедиться, что этот случай содержат потерь, как потеря функции или повышением сложности кода.  Разработчик должен тщательно проверить этот подход весить преимущества и недостатки.  
  
## Предоставить отдельный интерфейс IDispatch  
 Можно предоставить несколько сдвоенные интерфейсы для одного объекта путем наследования из двух или более `IDispatchImpl` специализаций.  Однако если разрешить клиентам запросу для интерфейса `IDispatch`, потребуется использовать макрос [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) \(или [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)\) для определения того, какой базовый класс, используемый для реализации `IDispatch`.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/CPP/multiple-dual-interfaces_1.h)]  
  
 Поскольку только один интерфейс `IDispatch` предоставлять клиенты, которые могут только получать доступ к объектам через интерфейс `IDispatch` не смогут получить доступ методы или свойства в любом другом взаимодействие.  
  
## Объединение нескольких сдвоенных интерфейсов в одну реализацию интерфейса IDispatch  
 Библиотеки ATL не обеспечивает никакой поддержки для объединения нескольких сдвоенных интерфейсов в одну реализацию `IDispatch`.  Однако существует несколько способов объединения вручную известных интерфейсов, как создать шаблонный класс, содержащий объединение отдельных интерфейсов `IDispatch`, создать новый объект для выполнения функции `QueryInterface` или помощью typeinfo\- на основе реализации вложенных объектов, чтобы создать интерфейс `IDispatch`.  
  
 Эти подходы имеют проблемы с потенциальными конфликтами пространства имен, а также кодируют сложность и удобство сопровождения созданного.  Не рекомендуется создать несколько сдвоенные интерфейсы.  
  
## См. также  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)