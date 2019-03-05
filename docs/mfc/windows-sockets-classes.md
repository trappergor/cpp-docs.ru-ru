---
title: Классы сокетов Windows
ms.date: 11/04/2016
f1_keywords:
- vc.classes.net
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
ms.openlocfilehash: 4abdd8f8fbfc115b5014ffd0b3a37df357852b16
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303824"
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
