---
title: "Предоставление активации без мерцания | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f98cc77ecc11f2b3ea07352e48c1e6a096125300
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="providing-flicker-free-activation"></a>Предоставление активации без мерцания
Если элемент управления рисовании одинаково в активным и неактивным состоянием (и не использует активации без окна), можно исключить операции рисования и сопутствующее видимое мерцание, которое обычно случается при переходе между неактивные и активные состояния. Чтобы сделать это, включите **noFlickerActivate** флаг в набор флагов, возвращенных [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Пример:  
  
 [!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]  
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]  
  
 Код, чтобы включить этот флаг создается автоматически при выборе **активации без мерцания** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) страницы при создании элемента управления с помощью мастера элементов управления ActiveX MFC.  
  
 При использовании активации без окна Данная оптимизация не оказывает влияния.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

