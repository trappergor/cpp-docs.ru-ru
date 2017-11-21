---
title: "Создание элемента управления \"Главная панель\" | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rebar controls [MFC], creating
- CReBarCtrl class [MFC], creating
ms.assetid: 0a012e08-772b-4f6a-af86-7cb651d11d3e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d0f1cc709bf09d03f211f3123bd47c82bb590348
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="creating-a-rebar-control"></a>Создание элемента управления главной панели
[CReBarCtrl](../mfc/reference/crebarctrl-class.md) объектов необходимо создать перед родительский объект является видимым. Это сводит к минимуму возможные проблемы отрисовки.  
  
 Например элементы управления главной панели (используется в объекты окон фрейма) обычно используются как родительские окна для элементов управления панели инструментов. Таким образом родительский элемент управления главной панели — объект окна фрейма. Поскольку объект окна фрейма является родительским, `OnCreate` функцию-член (родительский) самое подходящее место для создания элемента управления главной панели.  
  
 Для использования `CReBarCtrl` объекта, обычно выполняются следующие действия:  
  
### <a name="to-use-a-crebarctrl-object"></a>Использование CReBarCtrl объекта  
  
1.  Создать [CReBarCtrl](../mfc/reference/crebarctrl-class.md) объекта.  
  
2.  Вызовите [создать](../mfc/reference/crebarctrl-class.md#create) для создания стандартного элемента управления главной панели Windows и присоединить его к `CReBarCtrl` объекта, указав любой требуемой стили.  
  
3.  Загрузить точечный рисунок, с помощью вызова [CBitmap::LoadBitmap](../mfc/reference/cbitmap-class.md#loadbitmap), для использования в качестве фона объекта элемента управления главной панели.  
  
4.  Создайте и инициализируйте все дочерние объекты окон (панели инструментов, элементы управления диалогового окна и т. д.), будут содержаться в объекте элемента управления главной панели.  
  
5.  Инициализация **REBARBANDINFO** структуру с информацию, необходимую для аппаратного контроллера управления будет вставлен.  
  
6.  Вызовите [InsertBand](../mfc/reference/crebarctrl-class.md#insertband) для вставки существующих дочерних окон (такие как `m_wndReToolBar`) в новый элемент управления главной панели. Дополнительные сведения о вставке полосами в существующий элемент управления главной панели см. в разделе [главной панели элементов управления и зоны](../mfc/rebar-controls-and-bands.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

