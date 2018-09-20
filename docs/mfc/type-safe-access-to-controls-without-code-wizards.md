---
title: Типобезопасный доступ к элементам управления без мастеров кода | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2685c946b9ee1c738ee83f9413b7fd955857febb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438344"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Типобезопасный доступ к элементам управления без мастеров кода

Первый подход к созданию типобезопасный доступ к элементам управления используется встроенная функция-член для приведения тип возвращаемого значения класса `CWnd`в `GetDlgItem` функция-член к соответствующему типу элемента управления C++, как в следующем примере:

[!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]

Затем эта функция-член можно использовать для доступа к элементу управления в строго типизированным образом с кодом, аналогичную следующей:

[!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]

## <a name="see-also"></a>См. также

[Типобезопасный доступ к элементам управления в диалоговом окне](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)<br/>
[Типобезопасный доступ к элементам управления с использованием мастеров кода](../mfc/type-safe-access-to-controls-with-code-wizards.md)

