---
title: Отношение к API языка C
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
ms.openlocfilehash: 8601dd034dbd73ac035084ad57c51f62e333fd32
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511864"
---
# <a name="relationship-to-the-c-language-api"></a>Отношение к API языка C

Единственной характеристикой, устанавливающей библиотеку Microsoft Foundation Class (MFC), помимо других библиотек классов для Windows, является очень близкое сопоставление с API Windows, написанным на языке C. Кроме того, можно свободно смешивать вызовы библиотеки классов с прямыми вызовами Windows API. Однако такой прямой доступ не подразумевает, что классы являются полной заменой для этого API. Разработчики по-прежнему должны иногда выполнять прямые вызовы некоторых функций Windows, например [сеткурсор](/windows/win32/api/winuser/nf-winuser-setcursor) и [жетсистемметрикс](/windows/win32/api/winuser/nf-winuser-getsystemmetrics). Функция Windows упаковывается функцией-членом класса только в том случае, если это неясное преимущество.

Поскольку иногда требуется выполнять вызовы функций машинного кода Windows, у вас должен быть доступ к документации по API Windows на языке C. Эта документация входит в состав Microsoft Visual C++.

> [!NOTE]
>  Общие сведения о работе платформы библиотеки MFC см. в разделе [Использование классов для написания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).

## <a name="see-also"></a>См. также

[Общие принципы разработки классов](../mfc/general-class-design-philosophy.md)
