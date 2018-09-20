---
title: Общие принципы разработки классов | Документация Майкрософт
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
ms.openlocfilehash: 8fe64ee4d9e6fc678d97c3e9fe37a85e53807541
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416647"
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

