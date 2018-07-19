---
title: Типобезопасный доступ к элементам управления без мастеров кода | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes [MFC], accessing controls
- dialog box controls [MFC], accessing
ms.assetid: 325b4927-d49b-42b4-8e0b-fc84f31fb059
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb861995c16411bb58e3051c5ffc78f75931ae8f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385769"
---
# <a name="type-safe-access-to-controls-without-code-wizards"></a>Типобезопасный доступ к элементам управления без мастеров кода
Первый подход к созданию типобезопасный доступ к элементам управления используется встроенная функция-член для приведения тип возврата класса `CWnd` `GetDlgItem` функции-члена для соответствующего типа элемента управления C++, как показано в примере:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#50](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_1.cpp)]  
  
 Затем можно использовать эту функцию-член для доступа к элементу управления в строго типизированным образом с код, аналогичный приведенному ниже:  
  
 [!code-cpp[NVC_MFCControlLadenDialog#51](../mfc/codesnippet/cpp/type-safe-access-to-controls-without-code-wizards_2.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Типобезопасный доступ к элементам управления в диалоговое окно](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Типобезопасный доступ к элементам управления с использованием мастеров кода](../mfc/type-safe-access-to-controls-with-code-wizards.md)

