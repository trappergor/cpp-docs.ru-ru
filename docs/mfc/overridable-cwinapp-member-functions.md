---
title: Функции-члены CWinApp переопределяемый | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CWinApp
dev_langs:
- C++
helpviewer_keywords:
- overriding [MFC], overridable functions in CWinApp
- application class [MFC]
- CWinApp class [MFC], overridables
ms.assetid: 07183d5e-734b-45d9-a8b6-9dde4adac0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ced9d7d5f7f49df50e028a299f83ddebdc9fc2d1
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395138"
---
# <a name="overridable-cwinapp-member-functions"></a>Переопределяемые функции-члены CWinApp

[CWinApp](../mfc/reference/cwinapp-class.md) предоставляет несколько ключевых функций является переопределяемым элементом (`CWinApp` переопределяет эти члены из класса [CWinThread](../mfc/reference/cwinthread-class.md), из которого `CWinApp` производный):

- [InitInstance](../mfc/initinstance-member-function.md)

- [Выполнить](../mfc/run-member-function.md)

- [ExitInstance](../mfc/exitinstance-member-function.md)

- [OnIdle](../mfc/onidle-member-function.md)

Единственным `CWinApp` функцию-член, необходимо переопределить `InitInstance`.

## <a name="see-also"></a>См. также

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
