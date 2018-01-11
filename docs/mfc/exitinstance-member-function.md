---
title: "Функция-член ExitInstance | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: 
dev_langs: C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99898a5e80c3f487c7f53fe81d13d3d1eb55ebd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="exitinstance-member-function"></a>Функция-член ExitInstance
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) функции-члена класса [CWinApp](../mfc/reference/cwinapp-class.md) вызывается всякий раз, копия приложения завершается, обычно в результате пользователю выход из приложения.  
  
 Переопределить `ExitInstance` необходимости обработки специальные операции очистки, например освобождение графических устройств (интерфейс) ресурсов или освобождением памяти, используемый во время выполнения программы. Тем не менее, очистку стандартных элементов, таких как документы и представления, предоставляется платформой, с другими переопределяемые функции для выполнения специальные операции очистки для этих объектов.  
  
## <a name="see-also"></a>См. также  
 [CWinApp: класс приложений](../mfc/cwinapp-the-application-class.md)
