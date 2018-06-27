---
title: Использование диалоговой панели с элементом управления главной панели | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- WM_EX_TRANSPARENT
dev_langs:
- C++
helpviewer_keywords:
- WS_EX_TRANSPARENT style
- rebar controls [MFC], dialog bars
- dialog bars [MFC], using with rebar bands
ms.assetid: e528cea0-6b81-4bdf-9643-7c03b6176590
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fa2628df5f446105e6b7881709a0c72c19fe230e
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36950494"
---
# <a name="using-a-dialog-bar-with-a-rebar-control"></a>Использование диалоговой панели с элементом управления главной панели
Как упоминалось в [главной панели элементов управления и зоны](../mfc/rebar-controls-and-bands.md), каждый диапазон может содержать только один дочернего окна (или элемента управления). Это может быть ограничением, если вы хотите иметь более одного дочернего окна на аппаратного контроллера управления. Удобное решение — Создание ресурса панели диалогового окна с несколькими элементами управления, а затем добавьте элемент управления главной панели аппаратного контроллера управления главной панели (содержащий диалоговой панели).  
  
 Как правило требуется внешнего панели диалогового окна с прозрачным, необходимо установить WS_EX_TRANSPARENT расширенный стиль для объекта панели диалогового окна. Тем не менее поскольку WS_EX_TRANSPARENT имеет некоторые проблемы с правильно закраски фона элемента диалоговой панели, необходимо будет выполнить дополнительную работу для достижения желаемого эффекта.  
  
 Следующей процедуре подробно описываются действия, необходимые для достижения прозрачности без использования WS_EX_TRANSPARENT расширенный стиль.  
  
### <a name="to-implement-a-transparent-dialog-bar-in-a-rebar-band"></a>Чтобы реализовать прозрачной диалоговой панели в области главной панели  
  
1.  С помощью [диалоговое окно "Добавление класса"](../mfc/reference/adding-an-mfc-class.md), добавьте новый класс (например, `CMyDlgBar`), реализующий объект панели диалогового окна.  
  
2.  Добавьте обработчик для сообщения WM_ERASEBKGND.  
  
3.  В обработчике новый измените существующий код в соответствии со следующим примером:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#29](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_1.cpp)]  
  
4.  Добавьте обработчик для сообщения WM_MOVE.  
  
5.  В обработчике новый измените существующий код в соответствии со следующим примером:  
  
     [!code-cpp[NVC_MFCControlLadenDialog#30](../mfc/codesnippet/cpp/using-a-dialog-bar-with-a-rebar-control_2.cpp)]  
  
 Новые обработчики имитации прозрачности диалоговой панели путем принудительного repaint каждый раз при перемещении объекта панели диалогового окна и перенаправления сообщений WM_ERASEBKGND родительского окна.  
  
## <a name="see-also"></a>См. также  
 [Использование CReBarCtrl](../mfc/using-crebarctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)

