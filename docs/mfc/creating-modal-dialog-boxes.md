---
title: Создание модальных диалоговых | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- modal dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
- MFC dialog boxes [MFC], modal
ms.assetid: 26c7a68c-79f6-4862-a5a8-6024984644d2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3fcc449a376091c07a7fb26b81fe19752bc3bcd6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376648"
---
# <a name="creating-modal-dialog-boxes"></a>Создание модальных диалоговых окон

Для создания модального диалогового окна, вызовите один из двух открытых конструкторов, объявленных в [CDialog](../mfc/reference/cdialog-class.md). Затем вызовите объекта диалогового окна [DoModal](../mfc/reference/cdialog-class.md#domodal) функция-член отобразить диалоговое окно управления взаимодействием с его, пока пользователь не решит OK и Отмена. Это управление, `DoModal` это и делает модальное диалоговое окно. Для модальные диалоговые окна `DoModal` загружает ресурс диалогового окна.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

