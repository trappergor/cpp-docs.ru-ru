---
title: Переопределяемые функции-члены CWinApp
ms.date: 11/04/2016
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
ms.openlocfilehash: 28ba243bd755e25db5f2cb03d08013f082fbc918
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447263"
---
# <a name="overridable-cwinapp-member-functions"></a>Переопределяемые функции-члены CWinApp

[CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько ключевых функций-членов, допускающих переопределение (`CWinApp` переопределяет эти члены из класса [CWinThread](../mfc/reference/cwinthread-class.md), от которого `CWinApp` наследуется):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Выполнить](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [Обработчик](../mfc/onidle-member-function.md)

Единственной `CWinApp`ой функцией-членом, которую необходимо переопределить, является `InitInstance`.

## <a name="see-also"></a>См. также раздел

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
