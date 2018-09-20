---
title: Типобезопасный доступ к элементам управления в диалоговом окне | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- common controls [MFC], in dialog boxes
- Windows common controls [MFC], in dialog boxes
- safe access to dialog box controls
- dialog boxes [MFC], type-safe access to controls
- controls [MFC], accessing in dialog boxes
- type-safe access to dialog box controls
- MFC dialog boxes [MFC], type-safe access to controls
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ed8a374c34eacc48e1d877e704fdc60a20f33d9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422718"
---
# <a name="type-safe-access-to-controls-in-a-dialog-box"></a>Типобезопасный доступ к элементам управления в диалоговом окне

Элементы в диалоговом окне могут использовать интерфейсы классов элементов управления MFC, таких как `CListBox` и `CEdit`. Можно создать объект элемента управления и присоединить его к элементу управления диалогового окна. После этого можно обращаться к элементу управления через интерфейс его класса, вызывая функции-члены для выполнения операций над элементом управления. Описанные здесь методы предназначены для того, чтобы обеспечить типобезопасный доступ к элементу управления. Это особенно полезно в случае таких элементов управления, как поля ввода и списки.

Существует два подхода к созданию соединения между элементом управления в диалоговом окне и переменной-членом элемента управления C++ в классе, производном от `CDialog`:

- [Без мастеров кода](../mfc/type-safe-access-to-controls-without-code-wizards.md)

- [С помощью мастеров кода](../mfc/type-safe-access-to-controls-with-code-wizards.md)

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)

