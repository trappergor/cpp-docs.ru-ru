---
title: Общие принципы разработки классов | Документы Microsoft
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
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b2d0915c4b2940e93b781e7a56e2640c64a7f20
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344367"
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

