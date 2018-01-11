---
title: "Общие принципы разработки классов | Документы Microsoft"
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
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c174b06b27e78ca61d2608b8e04205068ac436e9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="general-class-design-philosophy"></a>Общие принципы разработки классов
Microsoft Windows был разработан задолго до стала популярной языка C++. Тысячи приложений используют интерфейс (API) Windows на языке C, в обозримом будущем будет поддерживать этот интерфейс. Любой интерфейс Windows на C++ таким образом должен быть построена на базе процедурных API языка C. Это гарантирует, что приложения C++ будет возможность сосуществовать с приложениями C.  
  
 Библиотеки классов Microsoft Foundation является объектно ориентированного интерфейса для Windows, который соответствует следующие цели:  
  
-   Значительное снижение трудозатраты, необходимые для создания приложений для Windows.  
  
-   Аналогично API языка C скорость выполнения.  
  
-   Затраты на размер минимальное кода.  
  
-   Возможность непосредственно вызвать любую функцию Windows C.  
  
-   Упрощает перенос существующих приложений C в C++.  
  
-   Возможность использовать от существующего базового программирования возможности языка C Windows.  
  
-   Упростить работу API Windows с C++, чем с C.  
  
-   Упрощает использование еще мощные абстракции сложным функции, такие как элементы управления ActiveX, поддержка баз данных, печать, панели инструментов и строки состояния.  
  
-   Значение true, API Windows для C++, который использует возможности языка C++.  
  
 Дополнительные сведения о библиотеки MFC см.:  
  
-   [Платформа приложения](../mfc/application-framework.md)  
  
-   [Отношение к API языка C](../mfc/relationship-to-the-c-language-api.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

