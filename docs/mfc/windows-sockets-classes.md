---
title: Классы сокетов Windows
ms.date: 11/04/2016
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 3f1b7b2b6674b4a5f8c8f7bff6c5fa239715f459
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445980"
---
# <a name="windows-sockets-classes"></a>Классы сокетов Windows

Сокеты Windows обеспечивают независимый от сетевого протокола способ связи между двумя компьютерами. Эти сокеты могут быть синхронными (программа ожидает, пока связь не будет выполнена) или асинхронной (программа продолжит выполнение во время обмена данными).

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)<br/>
Инкапсулирует API сокетов Windows в тонкой оболочке.

[CSocket](../mfc/reference/csocket-class.md)<br/>
Абстракция более высокого уровня, производная от `CAsyncSocket`. Он работает синхронно.

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Предоставляет интерфейс `CFile` для сокета Windows.

## <a name="see-also"></a>См. также раздел

[Обзор класса](../mfc/class-library-overview.md)
