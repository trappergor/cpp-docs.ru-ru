---
title: Классы сокетов Windows | Документы Microsoft
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
ms.openlocfilehash: 4e370c8a5f9cb2fb42c3199dbc0d56b69d93dc35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="windows-sockets-classes"></a>Классы сокетов Windows
Сокеты Windows позволяют сети зависит от протоколов для обмена данными между двумя компьютерами. Эти сокеты могут быть синхронными (программа ожидает, пока выполняется обмен данными) или асинхронные (программа продолжает выполнение, пока происходит обмен данными).  
  
 [CAsyncSocket](../mfc/reference/casyncsocket-class.md)  
 Инкапсулирует API Windows Sockets в тонкую оболочку.  
  
 [CSocket](../mfc/reference/csocket-class.md)  
 Высокий уровень абстракции производным от `CAsyncSocket`. Он работает синхронно.  
  
 [CSocketFile](../mfc/reference/csocketfile-class.md)  
 Предоставляет `CFile` интерфейс Windows Socket.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

