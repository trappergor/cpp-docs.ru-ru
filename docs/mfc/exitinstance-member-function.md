---
title: Функция-член ExitInstance | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 954d2248061ec571d9d2ba8804c1f7c97275cbfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exitinstance-member-function"></a>Функция-член ExitInstance
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) функции-члена класса [CWinApp](../mfc/reference/cwinapp-class.md) вызывается всякий раз, копия приложения завершается, обычно в результате пользователю выход из приложения.  
  
 Переопределить `ExitInstance` необходимости обработки специальные операции очистки, например освобождение графических устройств (интерфейс) ресурсов или освобождением памяти, используемый во время выполнения программы. Тем не менее, очистку стандартных элементов, таких как документы и представления, предоставляется платформой, с другими переопределяемые функции для выполнения специальные операции очистки для этих объектов.  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
