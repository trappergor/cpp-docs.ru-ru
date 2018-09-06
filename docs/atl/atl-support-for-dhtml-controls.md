---
title: Поддержка элементов управления DHTML в ATL | Документация Майкрософт
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
ms.openlocfilehash: 5144a11f0b035822e6f729692569e5e861c44dcc
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43758314"
---
# <a name="atl-support-for-dhtml-controls"></a>Поддержка элементов управления DHTML в ATL

С помощью ATL, можно создать элемент управления с возможностью динамического HTML (DHTML). Элемент управления DHTML в ATL:

- Размещает элемент управления WebBrowser.

- Указывает, что с помощью HTML, пользовательский интерфейс (UI) элемента управления DHTML.

- Обращается к WebBrowser объекта и его методы через его интерфейс [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx).

- Управляет связью между кодом C++ и HTML.

Элемент управления DHTML аналогична другим управления ATL, за исключением того, элемент управления DHTML включает интерфейс диспетчеризации дополнительные. См. рисунок в [определение элементов для проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) иллюстрация интерфейсов, предоставляемых в проекте DHTML по умолчанию.

Элемент управления DHTML в ATL можно просмотреть в веб-браузере или другом контейнере, такие как тестовый контейнер элементов управления ActiveX.

## <a name="in-this-section"></a>В этом разделе

[Определение элементов для проекта элемента управления DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
Описывает элементы проекта элемента управления DHTML.

[Вызов кода на языке C++ из DHTML](../atl/calling-cpp-code-from-dhtml.md)  
Пример вызова кода C++ из элемента управления DHTML.

[Создание элемента управления DHTML в ATL](../atl/creating-an-atl-dhtml-control.md)  
Приводятся инструкции по созданию элемента управления DHTML.

[Тестирование элемента управления DHTML в ATL](../atl/testing-the-atl-dhtml-control.md)  
Показано, как построение и тестирование исходного проекта элемента управления DHTML.

[Изменение элемента управления DHTML в ATL](../atl/modifying-the-atl-dhtml-control.md)  
Показано, как добавить некоторые функции в элементе управления.

[Тестирование элемента управления измененным DHTML в ATL](../atl/testing-the-modified-atl-dhtml-control.md)  
Показано, как создавать и тестировать дополнительные возможности элемента управления.

## <a name="related-sections"></a>Связанные разделы

[ATL](../atl/active-template-library-atl-concepts.md)  
Ссылки на разделы о программировании с использованием библиотеки ATL.

