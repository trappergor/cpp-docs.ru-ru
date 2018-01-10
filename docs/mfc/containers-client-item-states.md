---
title: "Контейнеры: Состояния элементов клиентов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6bcc43d4e8b32a8766eef7c50e45bece569ef5c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="containers-client-item-states"></a>Контейнеры. Состояния элементов клиентов
В этой статье описываются различные состояния, которые передает клиентский элемент времени существования.  
  
 Клиентский элемент проходит через несколько состояний, как она создается, активирован, изменены и сохранены. Изменения состояния элемента, вызывается при каждом запуске [COleClientItem::OnChange](../mfc/reference/coleclientitem-class.md#onchange) с `OLE_CHANGED_STATE` уведомления. Второй параметр представляет собой значение от **COleClientItem::ItemState** перечисления. Он может принимать одно из следующих:  
  
-   **COleClientItem::emptyState**  
  
-   **COleClientItem::loadedState**  
  
-   **COleClientItem::openState**  
  
-   **COleClientItem::activeState**  
  
-   **COleClientItem::activeUIState**  
  
 В пустое состояние клиентский элемент еще не полностью элемент. Выделена память для него, но он еще не был инициализирован с данными элемента OLE. Это состояние, клиентский элемент находится в, если он будет создан путем вызова **новый** , но еще не подвергся второй шаг создания обычной двухэтапный.  
  
 На втором шаге, выполняются с помощью вызова `COleClientItem::CreateFromFile` или другой **CreateFrom***xxxx* функция, элемент полностью создан. Данные OLE (из файла или другого источника, например буфера обмена) было связано с `COleClientItem`-производного объекта. Теперь элемент находится в состоянии загрузки.  
  
 Если элемент был открыт в окне сервера, а не открыт на месте в документе-контейнере, он находится в состоянии открыть (или полностью открыть). В этом состоянии между штриховку обычно рисуется через представление элемента в окне контейнера, чтобы указать, что элемент является активной в другом месте.  
  
 При активации элемента на месте он передает, обычно только в двух словах, через активное состояние. Затем он переходит в активное состояние пользовательского интерфейса, в котором сервер было выполнено слияние меню, панелей инструментов и другие компоненты пользовательского интерфейса с этими контейнера. Наличие этих компонентов пользовательского интерфейса, являющийся отличительным признаком активное состояние пользовательского интерфейса из активного состояния. В противном случае в активном состоянии напоминает активное состояние пользовательского интерфейса. Если сервер поддерживает отмены, сервер является обязательным для сохранения состояния отмены сведения объекта OLE, до достижения состояния загружен или открыть.  
  
## <a name="see-also"></a>См. также  
 [Контейнеры](../mfc/containers.md)   
 [Активация](../mfc/activation-cpp.md)   
 [Контейнеры: Уведомления элементов клиентов](../mfc/containers-client-item-notifications.md)   
 [Средства отслеживания](../mfc/trackers.md)   
 [Класс CRectTracker](../mfc/reference/crecttracker-class.md)
