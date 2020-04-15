---
title: Отношение к API языка C
ms.date: 11/04/2016
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: 1fbd4d332f5ade1cb9415448b138ac5bc838307d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372830"
---
# <a name="relationship-to-the-c-language-api"></a>Отношение к API языка C

Единственной характеристикой, которая отличает библиотеку Microsoft Foundation Class (MFC) от других библиотек классов для Windows, является очень близкое отображение к API Windows, написанному на языке C. Кроме того, обычно можно свободно смешивать вызовы в библиотеку классов с прямыми вызовами на API Windows. Однако этот прямой доступ не означает, что классы являются полной заменой этого API. Разработчики должны иногда совершать прямые вызовы на некоторые функции Windows, такие как [SetCursor](/windows/win32/api/winuser/nf-winuser-setcursor) и [GetSystemMetrics,](/windows/win32/api/winuser/nf-winuser-getsystemmetrics)например. Функция Windows обернута функцией члена класса только тогда, когда есть явное преимущество для этого.

Поскольку иногда требуется сделать нативные вызовы функций Windows, вы должны иметь доступ к документации C-language Windows API. Эта документация включена в комплект microsoft Visual C.

> [!NOTE]
> Для обзора того, как работает платформа Библиотеки MFC, можно [ознакомиться с помощью классов для записи приложений для Windows.](../mfc/using-the-classes-to-write-applications-for-windows.md)

## <a name="see-also"></a>См. также раздел

[Философия дизайна общего класса](../mfc/general-class-design-philosophy.md)
