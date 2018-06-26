---
title: 'Управление памятью: Выделение кучи | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC], detecting leaks
- delete operator [MFC], using with debug MFC
- heap allocation [MFC], described
- memory allocation [MFC], heap memory
- memory leaks [MFC], detecting
- new operator [MFC], using with debug MFC
- heap allocation [MFC]
- detecting memory leaks [MFC]
ms.assetid: a5d949c6-1b79-476e-9c66-513a558203d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7ef166201103b1544d0a36d82452b485af75418
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928613"
---
# <a name="memory-management-heap-allocation"></a>Управление памятью. Выделение кучи
Куча зарезервирован для выделения памяти, необходимой программы. Он представляет собой область, отдельно от кода программы и стека. Обычно программы C используют функции **malloc** и **свободного** выделять и освобождать память в куче. Отладочная версия MFC предоставляет измененные версии встроенных операторов C++ **новый** и **удалить** выделять и освобождать объекты в памяти в куче.  
  
 При использовании **новый** и **удаление** вместо **malloc** и **свободного**, можно воспользоваться преимуществами библиотеки классов Управление памятью улучшения отладки, которые могут быть полезны при обнаружении утечки памяти. При построении программы с версией MFC, стандартные версии **новый** и **удалить** операторы предоставляют эффективный способ выделения и освобождения памяти (в версии MFC не поддерживает измененные версии этих операторов).  
  
 Обратите внимание, что общий размер объектов в куче ограничивается только доступной виртуальной памяти системы.  
  
## <a name="see-also"></a>См. также  
 [Управление памятью](../mfc/memory-management.md)

