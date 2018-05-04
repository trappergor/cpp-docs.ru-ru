---
title: Поддержка элементов управления DHTML в ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f57fc841ba2eb3473ccb866df7333ebd24583d40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
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

