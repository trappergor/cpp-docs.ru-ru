---
title: SDI и MDI | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- frame windows [MFC], SDI applications
- frame windows [MFC], MDI applications
- MFC, windows
- single document interface (SDI) [MFC], applications
- MDI [MFC], vs. SDI
ms.assetid: bb7239d9-4759-4f63-bfff-44a04b48c067
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8189af7939bfca0fd206fa72892098e373444879
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46401450"
---
# <a name="sdi-and-mdi"></a>SDI и MDI

MFC упрощает работу с однооконным интерфейсом (SDI) и приложений многодокументного интерфейса (MDI).

Приложения SDI разрешить только одно окно фрейма открытый документ за раз. Приложения MDI разрешает несколько документов, окон фрейма, необходимо открыть на том же экземпляре приложения. MDI-приложения с периодом в какие MDI несколько дочерних окон, которые являются окна фрейма, сами, можно открыть, каждая из которых содержит отдельный документ. В некоторых приложениях в дочерние окна может быть разных типов, таких как диаграммы и таблицы окна. В этом случае в строке меню можно изменить как активируются дочерние окна MDI различных типов.

> [!NOTE]
>  В Windows 95 и более поздних версиях приложений обычно представляют собой SDI так, как операционная система была внедрена представления «документ по центру».

Дополнительные сведения см. в разделе [документы, представления и платформа](../mfc/documents-views-and-the-framework.md).

## <a name="see-also"></a>См. также

[Использование классов для создания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
