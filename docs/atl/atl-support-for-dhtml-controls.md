---
title: "Поддержка элементов управления DHTML в ATL | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ab796752cef10c48036966c2947d711a0e385032
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-support-for-dhtml-controls"></a>Поддержка элементов управления DHTML в ATL
С использованием ATL, можно создать элемент управления с возможностью динамического HTML (DHTML). Элемент управления ATL DHTML:  
  
-   Размещает элемент управления WebBrowser.  
  
-   Указывает, что с помощью HTML, пользовательский интерфейс (UI) элемента управления DHTML.  
  
-   Обращается к веб-браузер объекта и его методы через его интерфейс [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx).  
  
-   Управляет связью между кодом C++ и HTML.  
  
 Элемент управления DHTML похож других управления ATL, за исключением управления DHTML включает интерфейс диспетчеризации дополнительные. См. рисунок в [определения элементов проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) иллюстрация интерфейсов, предоставляемых в проекте по умолчанию DHTML.  
  
 Элемент управления ATL DHTML можно просмотреть в веб-браузер или другой контейнер, например тестовый контейнер элемента управления ActiveX.  
  
## <a name="in-this-section"></a>В этом разделе  
 [Определение элементов для проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 Описывает элементы проекта элемента управления DHTML.  
  
 [Вызов кода на языке C++ из DHTML](../atl/calling-cpp-code-from-dhtml.md)  
 Пример вызова кода C++ из элемента управления DHTML.  
  
 [Создание элемента управления DHTML в ATL](../atl/creating-an-atl-dhtml-control.md)  
 Приводятся инструкции по созданию элемента управления DHTML.  
  
 [Тестирование элемента управления DHTML в ATL](../atl/testing-the-atl-dhtml-control.md)  
 Показано, как сборка и тестирование начального проекта элемента управления DHTML.  
  
 [Изменение элемента управления DHTML в ATL](../atl/modifying-the-atl-dhtml-control.md)  
 Показано, как добавить некоторые функциональные возможности элемента управления.  
  
 [Тестирование измененный элемент управления ATL DHTML](../atl/testing-the-modified-atl-dhtml-control.md)  
 Показано, как сборка и тестирование добавлены функциональные возможности элемента управления.  
  
## <a name="related-sections"></a>Связанные разделы  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Ссылки на разделы о программировании с использованием библиотеки ATL.

