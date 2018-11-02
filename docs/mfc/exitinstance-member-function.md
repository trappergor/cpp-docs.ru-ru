---
title: Функция-член ExitInstance
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: b1c5b3a20f25f909188023ab1650bc41316d7a9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637740"
---
# <a name="exitinstance-member-function"></a>Функция-член ExitInstance

[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) функция-член класса [CWinApp](../mfc/reference/cwinapp-class.md) вызывается каждый раз, копия приложения завершается, обычно из-за выхода из приложения пользователя.

Переопределить `ExitInstance` необходимости обработки специальные операции очистки, например освобождение графических устройств (интерфейс) ресурсов или освобождение памяти, используемый во время выполнения программы. Тем не менее, очистки стандартных элементов, таких как документы и представления, предоставляется платформой, с помощью других переопределяемые функции для выполнения специальных операций очистки для этих объектов.

## <a name="see-also"></a>См. также

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
