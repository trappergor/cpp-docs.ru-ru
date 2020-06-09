---
title: Создание модальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: ed7cc94982a46e542a5174d4d46b8013cc84ffa4
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622978"
---
# <a name="creating-modal-dialog-boxes"></a>Создание модальных диалоговых окон

Чтобы создать модальное диалоговое окно, вызовите один из двух открытых конструкторов, объявленных в [CDialog](reference/cdialog-class.md). Затем вызовите функцию члена [DoModal](reference/cdialog-class.md#domodal) объекта Dialog, чтобы отобразить диалоговое окно и управлять взаимодействием с ним до тех пор, пока пользователь не нажмет кнопку ОК или Отмена. Это управление, которое `DoModal` делает диалоговое окно модальным. Для модальных диалоговых окон `DoModal` загружает ресурс диалогового окна.

## <a name="see-also"></a>См. также раздел

[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)
