---
title: Классы сокетов Windows
ms.date: 11/04/2016
f1_keywords:
- vc.classes.net
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 18537c0de09185c8cd219e3d17ef8bb297e1d711
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50433609"
---
# <a name="windows-sockets-classes"></a>Классы сокетов Windows

Сокеты Windows позволяют сети зависит от протоколов для обмена данными между двумя компьютерами. Эти сокеты может быть синхронным (программа ожидает, пока выполняется обмен данными) или асинхронным (программа продолжает выполнение, пока происходит обмен данными).

[CAsyncSocket](../mfc/reference/casyncsocket-class.md)<br/>
Инкапсулирует API сокетов Windows в случае тонкой оболочки.

[CSocket](../mfc/reference/csocket-class.md)<br/>
Высокий уровень абстракции производным от `CAsyncSocket`. Он работает синхронно.

[CSocketFile](../mfc/reference/csocketfile-class.md)<br/>
Предоставляет `CFile` интерфейс сокетов Windows.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

