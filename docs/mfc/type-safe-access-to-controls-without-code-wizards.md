---
title: Типобезопасный доступ к элементам управления без мастеров кода
ms.date: 11/04/2016
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
ms.openlocfilehash: 2b337aa28d5fdf061d1db4b5cf66303688ef5bf3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501716"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Типобезопасный доступ к элементам управления без мастеров кода

Первый подход к созданию типобезопасный доступ к элементам управления используется встроенная функция-член для приведения тип возвращаемого значения класса `CWnd`в `GetDlgItem` функция-член к соответствующему типу элемента управления C++, как в следующем примере:

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

Затем эта функция-член можно использовать для доступа к элементу управления в строго типизированным образом с кодом, аналогичную следующей:

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>См. также

[Типобезопасный доступ к элементам управления в диалоговом окне](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Типобезопасный доступ к элементам управления с использованием мастеров кода](../mfc/type-safe-access-to-controls-with-code-wizards.md)

