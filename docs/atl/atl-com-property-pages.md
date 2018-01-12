---
title: "Страницы свойств ATL COM | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- property pages, COM
- ATL COM objects
- COM property pages
- property pages, ATL
- COM objects, ATL
- ATL property pages
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 08b1c31aeaba25f4eadad5225dd2f5607cf7053c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-com-property-pages"></a>Страницы свойств COM в ATL
Страницы свойств COM предоставляют пользовательский интерфейс для настройки свойств (или вызова методов) одного или нескольких COM-объектов. Страницы свойств широко используются элементами управления ActiveX для предоставления полнофункциональных пользовательские интерфейсы, которые позволяют задать во время разработки свойства элемента управления.  
  
 Страницы свойств являются COM-объекты, реализующие [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) или [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) интерфейса. Эти интерфейсы обеспечивают методы, позволяющие страницы должны быть связаны с `site` (объект COM, представляющий контейнер страницы) и ряд *объектов* (COM-объекты, методы которого будут вызываться в ответ на изменения внесенные пользователем страницы свойств). Контейнер страниц свойств отвечает за вызов методов в интерфейсе страницы свойств сообщить страницы, чтобы показать или скрыть его пользовательский интерфейс и когда следует применить изменения, сделанные пользователем базовых объектов.  
  
 Каждая страница свойств можно построить полностью независимо от объектов, свойства которого можно задать. Все, что страницы свойств — требуется для понимания определенный интерфейс (или набор интерфейсов) и предоставить пользовательский интерфейс для вызова методов в этом интерфейсе.  
  
 Дополнительные сведения см. в разделе [вкладки свойств и страницы свойств](http://msdn.microsoft.com/library/windows/desktop/ms686577) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## <a name="in-this-section"></a>В этом разделе  
 [Указание страниц свойств](../atl/specifying-property-pages.md)  
 Перечень шагов для указания страницы свойств для элемента управления можно и показан пример класса.  
  
 [Реализация страниц свойств](../atl/implementing-property-pages.md)  
 Приводятся инструкции по реализации страницы свойств, включая методы для переопределения. Описывается на основе образца программы ATLPages полный пример.  
  
## <a name="related-sections"></a>Связанные разделы  
 [Пример ATLPages](../visual-cpp-samples.md)  
 Пример абстрактного образец ATLPages, который реализует страницу свойств с использованием `IPropertyPageImpl`.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)

