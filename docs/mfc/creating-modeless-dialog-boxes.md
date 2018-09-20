---
title: Создание немодальных диалоговых | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC dialog boxes [MFC], modeless
- modeless dialog boxes [MFC], creating
- MFC dialog boxes [MFC], creating
ms.assetid: 70d78c7f-3d40-477b-9f78-0f33c359f88b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77b80f66f2956e71b90e4d939a0fb74aef28edb1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407040"
---
# <a name="creating-modeless-dialog-boxes"></a>Создание немодальных диалоговых окон

Для немодального диалогового окна необходимо предоставить собственный открытый конструктор в класс диалогового окна. Чтобы создать немодального диалогового окна, вызовите ваш открытый конструктор, а затем вызовите объекта диалогового окна [создать](../mfc/reference/cdialog-class.md#create) функция-член для загрузки ресурса диалогового окна. Можно вызвать **создать** во время или после вызова этого конструктора. Если ресурс диалогового окна со свойством **WS_VISIBLE**, немедленно появится диалоговое окно. Если нет, следует вызвать его [ShowWindow](../mfc/reference/cwnd-class.md#showwindow) функция-член.

## <a name="see-also"></a>См. также

[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)

