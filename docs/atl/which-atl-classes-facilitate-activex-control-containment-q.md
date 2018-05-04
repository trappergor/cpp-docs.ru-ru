---
title: ATL-классы упрощают вложения элемента управления ActiveX? | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- hosting controls using ATL
- ActiveX control containers [C++], ATL control hosting
ms.assetid: 803a4605-7f4c-4139-8638-49d8783d31b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f024e9929e916e15b110bfc32bc704c4aef755a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="which-atl-classes-facilitate-activex-control-containment"></a>ATL-классы упрощают вложения элемента управления ActiveX?
Код, размещение элементов управления ATL не требуется использовать все классы ATL; позволяет создать **«AtlAxWin80»** окна и использование API размещение элементов управления, при необходимости (Дополнительные сведения см. в разделе **возможности API размещения элемента управления ATL**. Тем не менее следующие классы упростить вложенность функций для использования.  
  
|Класс|Описание|  
|-----------|-----------------|  
|[CAxWindow](../atl/reference/caxwindow-class.md)|Создает оболочку для **«AtlAxWin80»** окна, предоставлять методы для создания окна, создание элемента управления и/или присоединение элемента управления в окно и получения указателей интерфейса для объекта узла.|  
|[CAxWindow2T](../atl/reference/caxwindow2t-class.md)|Создает оболочку для **«AtlAxWinLic80»** окна, предоставлять методы для создания окна, создание элемента управления и/или присоединение лицензированный элемент управления в окно и получения указателей интерфейса для объекта узла.|  
|[CComCompositeControl](../atl/reference/ccomcompositecontrol-class.md)|Действует как базовый класс для классов элементов управления ActiveX, на основе ресурса диалогового окна. Такие элементы управления могут содержать другие элементы управления ActiveX.|  
|[CAxDialogImpl](../atl/reference/caxdialogimpl-class.md)|Действует как базовый класс для классов диалоговых окон, на основе ресурса диалогового окна. Такие диалоговые окна может содержать элементы управления ActiveX.|  
|[CWindow](../atl/reference/cwindow-class.md)|Предоставляет метод, [GetDlgControl](../atl/reference/cwindow-class.md#getdlgcontrol), возвращает указатель интерфейса на элемент управления, заданный идентификатор окна ее размещения. Кроме того, программы-оболочки Windows API, предоставляемые `CWindow` обычно упростить управление окнами.|  
  
## <a name="see-also"></a>См. также  
 [Часто задаваемые вопросы о вложении элементов управления](../atl/atl-control-containment-faq.md)

