---
title: Классы сокетов Windows | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.net
dev_langs:
- C++
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 893fa525b04376cde0e96f280c95e6bfd1243946
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439982"
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

