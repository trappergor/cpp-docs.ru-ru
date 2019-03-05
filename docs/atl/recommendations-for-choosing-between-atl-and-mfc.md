---
title: Рекомендации по выбору между ATL и MFC
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, ATL support
- ATL, vs. MFC
ms.assetid: 269325bb-11a8-4330-ad2b-a14a2458679e
ms.openlocfilehash: e4e51f81bbdc54ff09980acfba22037df77abac9
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259780"
---
# <a name="recommendations-for-choosing-between-atl-and-mfc"></a>Рекомендации по выбору между ATL и MFC

При разработке компонентов и приложений, можно выбрать между двумя подходами, ATL и MFC (библиотека классов Microsoft Foundation).

## <a name="using-atl"></a>С помощью ATL

ATL — удобный способ поддерживать компактную и создание COM-компонента на языке C++. Используйте библиотеку ATL для создания элемента управления, если вам не требуется, все встроенные функции, предоставляемой библиотекой MFC автоматически.

## <a name="using-mfc"></a>Использование MFC

MFC позволяет создавать полные приложения, элементы управления ActiveX и активные документы. Если вы уже создали элемент управления с MFC, можно продолжить разработку в MFC. При создании нового элемента управления, рассмотрите возможность использования ATL, если все встроенные функции MFC не требуется.

## <a name="using-atl-in-an-mfc-project"></a>Использование ATL в проект MFC

Можно добавить поддержку для использования библиотеки ATL в существующем проекте MFC с помощью мастера. Дополнительные сведения см. в разделе [Добавление поддержки ATL в проект MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md).

## <a name="see-also"></a>См. также

[Введение в ATL](../atl/introduction-to-atl.md)
