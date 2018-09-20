---
title: 'Управление памятью: Выделение кучи | Документация Майкрософт'
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
ms.openlocfilehash: cc158ceda21bfb04053bbc490a3333a76e2d7afe
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383822"
---
# <a name="memory-management-heap-allocation"></a>Управление памятью. Выделение кучи

Кучи зарезервирован для выделения объем памяти, необходимый программе. Он представляет собой область, помимо программный код и стека. Типичный программ на языке C используются функции **malloc** и **бесплатный** выделять и освобождать память в куче. Отладочная версия MFC предоставляет модифицированная версия встроенных операторов C++ **новый** и **удалить** выделять и освобождать объекты в памяти в куче.

При использовании **новый** и **удалить** вместо **malloc** и **бесплатный**, вы сможете воспользоваться преимуществами библиотеки классов Управление памятью усовершенствования отладки, которые могут быть полезен при обнаружении утечки памяти. При построении программы в финальной версии MFC, стандартные версии **новый** и **удалить** операторы предоставляют эффективный способ выделения и освобождения памяти (финальной версии MFC не поддерживает измененные версии этих операторов).

Обратите внимание на то, что общий размер объектов, выделенных в куче ограничивается только доступной виртуальной памяти системы.

## <a name="see-also"></a>См. также

[Управление памятью](../mfc/memory-management.md)

