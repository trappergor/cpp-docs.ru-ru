---
title: Создание модальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: ed0fe3b7ef8aeddea01f573bfe8e1c01a6b5b443
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685682"
---
# <a name="creating-modal-dialog-boxes"></a>Создание модальных диалоговых окон

Чтобы создать модальное диалоговое окно, вызовите один из двух открытых конструкторов, объявленных в [CDialog](../mfc/reference/cdialog-class.md). Затем вызовите функцию члена [DoModal](../mfc/reference/cdialog-class.md#domodal) объекта Dialog, чтобы отобразить диалоговое окно и управлять взаимодействием с ним до тех пор, пока пользователь не нажмет кнопку ОК или Отмена. Это управление с `DoModal` — это то, что делает диалоговое окно модальным. Для модальных диалоговых окон `DoModal` загружает ресурс диалогового окна.

## <a name="see-also"></a>См. также

[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)
