---
title: Создание модальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: eb9aab7e8579fbbbfdf5d0f2dca9b6e6abea0066
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657353"
---
# <a name="creating-modal-dialog-boxes"></a>Создание модальных диалоговых окон

Для создания модального диалогового окна, вызовите один из двух открытых конструкторов, объявленных в [CDialog](../mfc/reference/cdialog-class.md). Затем вызовите объекта диалогового окна [DoModal](../mfc/reference/cdialog-class.md#domodal) функция-член отобразить диалоговое окно управления взаимодействием с его, пока пользователь не решит OK и Отмена. Это управление, `DoModal` это и делает модальное диалоговое окно. Для модальные диалоговые окна `DoModal` загружает ресурс диалогового окна.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

