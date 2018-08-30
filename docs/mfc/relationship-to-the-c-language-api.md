---
title: Отношение к API языка C | Документация Майкрософт
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
ms.openlocfilehash: 8d0bb7aa4f647ceeb61c20cccd626d9da999b241
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200116"
---
# <a name="relationship-to-the-c-language-api"></a>Отношение к API языка C
Отдельная характеристика, которая устанавливает библиотеки Microsoft Foundation Class (MFC) помимо других библиотек классов для Windows — это сопоставление очень близки к API Windows, написанных на языке C. Кроме того вы можете обычно объединять вызовы к библиотеке классов свободно с прямыми вызовами в API Windows. Этот непосредственный доступ, однако означает, что классы, полная замена для этого API. Необходимо по-прежнему периодически разработчиками прямые вызовы некоторых функций Windows, таких как [SetCursor](/windows/desktop/api/winuser/nf-winuser-setcursor) и [GetSystemMetrics](https://msdn.microsoft.com/library/windows/desktop/ms724385), например. Функции Windows заключается только в том случае, если есть явное преимущество для этого функции-члена класса.  
  
 Поскольку иногда вам нужно сделать собственные вызовы функции Windows, следует имеется доступ к документации по API языка C Windows. Эта документация входит в состав Microsoft Visual C++.  
  
> [!NOTE]
>  Обзор принципов работы платформы библиотеки MFC, см. в разделе [использование классов для записи приложений для Windows](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## <a name="see-also"></a>См. также  
 [Общие принципы разработки классов](../mfc/general-class-design-philosophy.md)
