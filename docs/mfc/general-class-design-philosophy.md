---
title: Общие принципы разработки классов
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- designing classes [MFC]
- MFC, Windows API
- Visual C, Windows API calls
- classes [MFC], MFC class design
- Windows API [MFC], and MFC
ms.assetid: e6861ae0-1581-4d9c-9ddf-63f9afcdb913
ms.openlocfilehash: f032a4e3dd1dbb5ebed0197e2ee613b948d0b94b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618235"
---
# <a name="general-class-design-philosophy"></a>Общие принципы разработки классов

Microsoft Windows был разработан задолго до языка C++ стало популярным. Поскольку тысячи приложений используется интерфейс прикладного программирования (API) Windows на языке C, будет поддерживать этот интерфейс в обозримом будущем. Любой интерфейс Windows C++ таким образом должны быть построены на основе процедурного языка C API. Это гарантирует, что приложений C++ будет иметь возможность сосуществовать с приложениями C.

Библиотеки Microsoft Foundation Class является объектно ориентированный интерфейс для Windows, который соответствует следующими целями проектирования:

- Значительное сокращение усилий для написания приложений для Windows.

- Скорость выполнения, сравнимой с API языка C производительностью.

- Затраты на размер минимум кода.

- Возможность вызвать любую функцию Windows C напрямую.

- Упрощает перенос существующих приложений C C++.

- Возможность использования от существующей базы Windows на языке C, опыт программирования.

- Упрощенное использование API Windows с C++, чем с C.

- Проще использовать, но эффективные абстракции усложняется функции, такие как элементы управления ActiveX, поддержка баз данных, печать, панелей инструментов и строки состояния.

- Значение true, API Windows для C++, который эффективно использует возможности языка C++.

Дополнительные сведения о библиотеки MFC см. в разделе:

- [Платформа приложений](../mfc/application-framework.md)

- [Отношение к API языка C](../mfc/relationship-to-the-c-language-api.md)

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

