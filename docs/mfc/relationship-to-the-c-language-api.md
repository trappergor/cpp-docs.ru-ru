---
title: Отношение к API языка C | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.mfc
dev_langs:
- C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5d06c4adfa5493929a24c233fa923451c7bf0f95
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33379233"
---
# <a name="relationship-to-the-c-language-api"></a>Отношение к API языка C
Отдельная характеристика, который задает библиотеку Microsoft Foundation Class (MFC) отдельно от других библиотек классов для Windows является очень близкие сопоставление с API Windows, написанных на языке C. Кроме того можно обычно смешивать вызовы библиотеки классов свободно с прямые вызовы Windows API. Прямой доступ, однако означает, что классы не полная замена для этого API-интерфейса. Разработчики должны периодически убедиться, прямые вызовы некоторых функций Windows, таких как [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) и [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), например. Функции Windows заключается только в том случае, если есть свои преимущества для этого функции-члена класса.  
  
 Поскольку иногда нужно сделать собственный вызовы функций Windows, должны иметь доступ к документации по Windows API языка C. В этой документации входит в состав Microsoft Visual C++.  
  
> [!NOTE]
>  Обзор работой framework библиотеки MFC см. в разделе [использование классов для написания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>См. также  
 [Общие принципы разработки классов](../mfc/general-class-design-philosophy.md)
