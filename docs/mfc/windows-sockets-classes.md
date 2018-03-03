---
title: "Классы сокетов Windows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.net
dev_langs:
- C++
helpviewer_keywords:
- sockets classes [MFC]
- Windows Sockets [MFC], classes
ms.assetid: 58b9ab8d-9e44-4db3-8265-e04e713d2e9a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cea7690c9d1f754006a38c793fcd9608747c13b7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

