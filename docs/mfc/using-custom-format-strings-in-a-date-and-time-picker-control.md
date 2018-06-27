---
title: Использование строк пользовательского формата даты и времени выбора элемента управления | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CDateTimeCtrl class [MFC], display styles
- DateTimePicker control [MFC], display styles
- DateTimePicker control [MFC]
ms.assetid: 7d577f03-6ca0-4597-9093-50b78f304719
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9aeb6c02041a4ba90f9721f23a1397e17a4cdf81
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36955762"
---
# <a name="using-custom-format-strings-in-a-date-and-time-picker-control"></a>Использование строк пользовательского формата в элементе выбора даты и времени
По умолчанию элементы управления для даты и времени предоставляют три формате типов (каждый формат, соответствующий уникальный стиль) для отображения текущей даты или времени.  
  
-   **DTS_LONGDATEFORMAT** отображает дату в длинном формате вывода, такие как «Среда, 2 января 2000».  
  
-   **DTS_SHORTDATEFORMAT** отображает дату в кратком формате, создавать выходные данные, такие как «1/3/00».  
  
-   **DTS_TIMEFORMAT** отображает время в длинном формате вывода, такие как «17:31:42: 00».  
  
 Тем не менее используя строку настраиваемого формата можно настроить внешний вид даты или времени. Это пользовательская строка состоит из существующих символов формата, nonformat символов или их сочетание. После построения пользовательской строки вызвать [CDateTimeCtrl::SetFormat](../mfc/reference/cdatetimectrl-class.md#setformat) передав Настраиваемая строка. Элемент управления выбора даты и времени, будет выведено текущее значение, с помощью строки настраиваемого формата.  
  
 В следующем примере кода (где *m_dtPicker* — `CDateTimeCtrl` объекта) демонстрирует один из возможных решений:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#7](../mfc/codesnippet/cpp/using-custom-format-strings-in-a-date-and-time-picker-control_1.cpp)]  
  
 Помимо строк настраиваемого формата, элемент выбора даты и времени также управляет поддержкой [поля обратного вызова](../mfc/using-callback-fields-in-a-date-and-time-picker-control.md).  
  
## <a name="see-also"></a>См. также  
 [Использование CDateTimeCtrl](../mfc/using-cdatetimectrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

