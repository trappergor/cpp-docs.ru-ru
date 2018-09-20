---
title: Функция-член ExitInstance | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: da411fbecdea0a1e7b8976ca119057204693a9bd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387865"
---
# <a name="exitinstance-member-function"></a>Функция-член ExitInstance

[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) функция-член класса [CWinApp](../mfc/reference/cwinapp-class.md) вызывается каждый раз, копия приложения завершается, обычно из-за выхода из приложения пользователя.

Переопределить `ExitInstance` необходимости обработки специальные операции очистки, например освобождение графических устройств (интерфейс) ресурсов или освобождение памяти, используемый во время выполнения программы. Тем не менее, очистки стандартных элементов, таких как документы и представления, предоставляется платформой, с помощью других переопределяемые функции для выполнения специальных операций очистки для этих объектов.

## <a name="see-also"></a>См. также

[CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
