---
title: Создание модальных диалоговых окон
ms.date: 11/04/2016
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
ms.openlocfilehash: 5de6eeb616f32c7b8829d827988a972e41658530
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174098"
---
# <a name="creating-modal-dialog-boxes"></a>Создание модальных диалоговых окон

Для создания модального диалогового окна, вызовите один из двух открытых конструкторов, объявленных в [CDialog](../mfc/reference/cdialog-class.md). Затем вызовите объекта диалогового окна [DoModal](../mfc/reference/cdialog-class.md#domodal) функция-член отобразить диалоговое окно управления взаимодействием с его, пока пользователь не решит OK и Отмена. Это управление, `DoModal` это и делает модальное диалоговое окно. Для модальные диалоговые окна `DoModal` загружает ресурс диалогового окна.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)
