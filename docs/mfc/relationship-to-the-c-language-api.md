---
title: "Отношение к API языка C | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.classes.mfc
dev_langs: C++
helpviewer_keywords:
- books [MFC], about MFC and Windows SDK
- books [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- Windows API [MFC], and MFC
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 26458242ab6afcf69d6e70065ba70e31f0adbe74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="relationship-to-the-c-language-api"></a>Отношение к API языка C
Отдельная характеристика, который задает библиотеку Microsoft Foundation Class (MFC) отдельно от других библиотек классов для Windows является очень близкие сопоставление с API Windows, написанных на языке C. Кроме того можно обычно смешивать вызовы библиотеки классов свободно с прямые вызовы Windows API. Прямой доступ, однако означает, что классы не полная замена для этого API-интерфейса. Разработчики должны периодически убедиться, прямые вызовы некоторых функций Windows, таких как [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) и [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385), например. Функции Windows заключается только в том случае, если есть свои преимущества для этого функции-члена класса.  
  
 Поскольку иногда нужно сделать собственный вызовы функций Windows, должны иметь доступ к документации по Windows API языка C. В этой документации входит в состав Microsoft Visual C++.  
  
> [!NOTE]
>  Обзор работой framework библиотеки MFC см. в разделе [использование классов для написания приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>См. также  
 [Общие принципы разработки классов](../mfc/general-class-design-philosophy.md)
