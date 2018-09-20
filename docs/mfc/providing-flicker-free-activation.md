---
title: Предоставление активации без мерцания | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9f780472b8256f6d8332ecbde08138d85c8ebd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378331"
---
# <a name="providing-flicker-free-activation"></a>Предоставление активации без мерцания

Если элемент управления рисует себя идентично в штатах неактивными, (и не использует активации без окна), то можно исключить операций рисования и обычно возникают во время перехода между неактивного им мерцание и активные состояния. Чтобы сделать это, включите **noFlickerActivate** флаг в набор флагов, возвращенный [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Пример:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

Код, включив этот флаг создается автоматически при выборе **активации без мерцания** параметр [параметры управления](../mfc/reference/control-settings-mfc-activex-control-wizard.md) странице при создании элемента управления с помощью мастера элементов управления ActiveX MFC.

Если вы используете активации без окна, эта оптимизация не оказывает влияния.

## <a name="see-also"></a>См. также

[Элементы ActiveX в MFC. Оптимизация](../mfc/mfc-activex-controls-optimization.md)

